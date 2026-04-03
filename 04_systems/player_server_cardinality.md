# Player ↔ server cardinality & playing with friends

**Problem statement:** If progression is **one character per persistent server** (realm / shard), **friends must coordinate** on the same home; **solo** players still need **healthy matchmaking** and **populated raids** without dragging friends online.

**Status:** **Design exploration** — pick a model before hard-coding persistence and party flow. Linked from `../01_vision/scale_and_unresolved.md`.

## What “one character per server” usually implies

- A **named realm** (e.g. `US-West-1`) holds **persistent** stash, base, skills, vendor rep.
- **Switching realms** often means **new character** (or a **paid / rare transfer**).

**Upside:** Strong community, clear economy boundaries, “my server” identity.  
**Downside:** Fragmentation, dead off-peak realms, “wrong server” onboarding pain.

## How friends play together (must satisfy)

| Lever | Idea |
|--------|------|
| **Party before queue** | Form **duo/trio** in **social/base UI**, then **queue raid together** → matchmaking places the **party in the same instance** (standard extraction pattern). |
| **Same home realm** | Characters that share a **persistent realm** see each other in **base** and can **party** reliably. |
| **Invite / join friend** | “Join [Friend]’s session” if in **base** or **pre-raid lobby** — requires **same realm** or a **cross-realm lobby** layer (harder). |
| **Server picker at signup** | Player **chooses realm** once; show **friend’s realm** as recommendation. |

## How solo still works (must satisfy)

| Lever | Idea |
|--------|------|
| **Solo queue** | **Matchmade** into a raid with **random** duo/trios or **other solos** — does **not** require friends. |
| **Population** | Realms need **merge** tools or **regional mega-shards** if concurrency drops. |
| **Optional solo-only instances** | Rare but possible for quests — **not** default if **PvPvE always** is the core raid fantasy. |

## Architectural patterns (choose or hybrid)

1. **Realm-bound character + instanced raids**  
   - **Persistence** (base, stash, skills) = **per realm**.  
   - **Raids** = **ephemeral instances** drawn from a **regional pool** on that realm (or cross-realm pool with care).  
   - **Party** locks **same instance**.  
   - *Best fit for “one char per server” + extraction.*

2. **Global account + only cosmetic “server”**  
   - No per-server character; **region** is latency only. Easiest friends/solo, weak “server community.”

3. **Cross-realm social, realm-bound economy**  
   - Hard mode: **chat/party** across shards, **loot/base** tied to shard — expensive to build.

4. **Neighborhood shards + cross-instance raids** *(under consideration)*  
   - Many **persistent hub servers** (“neighborhoods”), each with a **target cap** (e.g. **~100 concurrent** players in social space — numbers are **tuning**, not law).  
   - **Social / base** stays **neighborhood-local** — you “live” in **Neighborhood #37** and see **that** crowd in hub.  
   - **Raids** use **cross-neighborhood matchmaking** — party queues from hub **A**, instance draws from a **regional (or wider) pool** so **PvPvE** stays populated even if **your** neighborhood is quiet.  
   - **Sunset / merge problem:** if a neighborhood **underloads**, you **cannot** freely **delete** the shard without **orphaning** homesteads and stashes tied to it. **Mitigations to design:**  
     - **Portable base** — player **moves** homestead assignment to another neighborhood (cooldown, fees, or seasonal **relocation** event).  
     - **Account-level stash snapshot** + **re-plop** base template in new hood (what transfers vs what’s left behind — TBD).  
     - **Drain + retire:** stop **new** assignments to dead shards; **incentivize** migration; **force** merge with **long** notice (MMO classic).  
     - **Never delete persistence** — archive + redirect login to merged ID (engineering heavy).
   - **Scheduled weekly hub reset** (`../01_vision/meta_loop_intent.md`) — if the **neighborhood’s buildable space** **wipes every week**, **sunset** becomes less about **orphaned structures** and more about **player assignment** + **what persists off-hub**. Align **merge** windows with **reset** tick when possible.  
   - **Ops win:** **Worst case**, you can **rebalance how many neighborhood servers** you run **on the next weekly boundary** — open new hoods, **merge** pools, or **shift capacity** without promising **infinite** persistence of **hub layout**. Players expect a **fresh build week** anyway; you’re tuning **shard cardinality** between those beats.

## Recommendation (working default)

- If you want **one character per server**, pair it with **instanced raids** and **party-first matchmaking** so **solo** and **friends** both funnel through the **same raid queue**, while **base/progression** stays **realm-local**.

## Locally hosted base (your machine / peer host)

**Idea:** **Raids** run on **dedicated** or **matchmade** servers (fair, authoritative PvPvE), while the **base / social** layer is a **listen server** or **P2P session** running on a **player’s PC** (host) or **console**.

### Upsides

- **Lower ops cost** for idle social spaces — no 24/7 cloud sim for every homestead.
- **Strong “this is my place”** fantasy; works with **solo** hangout when you’re the only one online.
- **Friends visit** by **joining the host’s base session** (invite / Steam friends / EOS, etc.).

### Hard problems (must design through)

| Topic | Risk |
|--------|------|
| **Host online** | Friends can’t hang in **your** shared base while you’re **offline** unless you also **mirror** layout to a cheap cloud “shell” or designate a **co-owner host**. |
| **Shared bases** (`meta_loop_intent.md`) | **Who hosts** the save? **Merge conflicts** if two friends both edit layout offline — need **one writer** or **cloud authoritative** layout. |
| **NAT / connectivity** | P2P base visits need **relays** (Steam, Epic, etc.) or **UPnP** fallbacks. |
| **Economy ↔ raids** | If the **local machine** is authoritative for **items that enter raids**, you invite **duping**. Safer pattern: **backend or raid server** validates **inventory that crosses the boundary**; base can still be **locally simulated** for **placement** if rewards are **server-granted**. |
| **Cheating** | Lower stakes in **PvE-only** base, but anything that **feeds competitive raid loadouts** must be **server-trusted**. |

### Hybrid that often works

- **Dedicated / authoritative** for **raid** + **anything that becomes loadout**.  
- **Locally hosted** (or cheap **player-specific** cloud snapshot) for **base presentation**, **decor**, **non-competitive** social.  
- **Friends:** “**Join [Host]’s homestead**” when host is up; optional **async** visit = **read-only** copy or **different** feature.

### Friends vs solo with local base

- **Solo:** You host your own base — **always** when you’re in that mode.  
- **Friends:** Party joins **one host** for base night; **raid queue** still works as today once you leave base (party travels to **dedicated raid**).  
- **You offline:** Friends use **their** bases or **raid**; they **don’t** persist edits to **your** hosted world unless you adopt **shared cloud save** for that plot.

## Neighborhood model — portable base (why it matters)

If you adopt **pattern 4** (many small hub shards + **cross-shard raids**), **portable or migratable homesteads** are the cleanest way to **retire** underpopulated neighborhoods **without** wiping player work. Define early:

- What **moves** with the player (structure, decor, **stash**, vendor rep tied to hood?).  
- **Cooldown / cost** so relocation isn’t spammed for economy exploit.  
- Whether **friends in the same hood** get **group move** tools or must coordinate manually.

*Overlaps* `../01_vision/meta_loop_intent.md` **shared bases** — co-owners may need **shared migration** rules.

## Next decisions to lock

- [ ] **Per realm:** max concurrent? merge policy?
- [ ] **Neighborhood cap:** ~**100** hubs × ~**100** players — **concurrent** vs **registered** cap? (Clarify before building.)
- [ ] **Raid instance:** max players / teams on map (`scale_and_unresolved.md`)?
- [ ] **Transfers:** free, paid, seasonal only?
- [ ] **Base hosting:** **cloud / realm** vs **local listen** vs **hybrid** (authoritative stash + local presentation)?
- [ ] **Portable base / migration** — required if neighborhood sunset is ever a thing?
- [ ] **Weekly hub reset** — full wipe vs **partial**; what persists (`meta_loop_intent.md`)?
- [ ] **Slice v1:** ignore realm split; use **one dev realm** + **2P party** only.

---

*Related:* `../01_vision/core_extraction_loop.md`, `../01_vision/scale_and_unresolved.md`, `vendors.md`, `skills.md`.
