# Core session loop — raid flow (incl. extract beats)

**Canonical session flow (steps).** The **full macro picture** — three tiers (survive / build / extract), loot bands, **three extract trains + final extract**, stash ↔ loadout, and the **craft → town → build → defenses → Exodus** spine — lives in **`game_loop.md`**. This file stays the **step list** and **vertical-slice alignment** so engineering and production have one short page for “what happens each raid.”

## Full loop (target experience)

1. **Party** — Choose **solo** or **party** (**duo** or **trio**).
2. **Loadout** — Configure what you bring into the raid (subset of your gear; **bank vault** holds the rest — `../04_systems/vault_and_loadout.md`). Framed in **`game_loop.md`** as leaving **stash & social** into the run.
3. **Join server** — Enter a **match / instance** (server model TBD — see `scale_and_unresolved.md`).
4. **Raid pressure** — **Timer** (or equivalent pressure) to **hit extract beats or fail the run**. **Lore justification** for why that pressure exists is **TBD** (must support tension without undermining fantasy — track in narrative when split out).
5. **Mid-raid play** — **Loot** and/or **fight**; **PvPvE always**, **no safe zones** (see `design_goals.md`). Over a full product run this play **ramps through tiers** (survive → build → extract climax) per **`game_loop.md`**; slice v1 focuses on proving **tier 1** feel plus **one** strong extract train moment.
6. **Extract** — Primary v1 exit: **train extraction** (tiered **Extract Train 1–3** + **final extract** after **Exodus** in target design — see **`game_loop.md`**). Other exits (e.g. **mine**) later.
7. **Round review** — Post-raid summary (rewards, stats, downtime hook into meta — scope TBD).

## Vertical slice alignment

The **nine-strip** playable slice (`../05_production/playable_slice_strip_order.md`) is the **minimum spine** of this loop in-engine—not a disconnected tech demo. For **macro loop** context, the slice targets **tier 1 (survive / low loot)** fidelity first; **town, tech buildings, defenses, Exodus** ship after the spine is playable unless production reprioritizes in writing.

| Loop phase | What the slice must prove |
|------------|---------------------------|
| **Party / join** | **#9** — **two players** in the same instance (duo path stub); solo still valid. Full **matchmaking UI** out of scope for slice. |
| **Loadout** | **#7** — **minimal inventory / equip** (enough to feel “I brought this in”). Deep loadout meta **later**. |
| **Deploy into raid** | **#2** env subset + **#3** menu flow into level. |
| **Pressure + PvPvE + loot + combat** | **#4–#6** — musket, **damage**, **HUD**; loot rules **as simple as needed** to not fake the fantasy. |
| **Extract** | **#8** — **train** moment is the **contract** with the full loop (**Extract Train 1** tier in target macro design). |
| **Round review** | **Not in slice v1** — document when adding **#10+** or post-slice milestone; don’t let slice avoid **thinking** about what review must show later. |

**Rule of thumb:** If a slice task **doesn’t** connect to a step above, **question whether it belongs** in the slice—or flag it as **tooling** / **devlog** only.

## Related

- **Macro loop & tiers:** `game_loop.md`
- Meta between raids: `meta_loop_intent.md`
- **Vault & loadout** (vault survives **weekly** hub wipe): `../04_systems/vault_and_loadout.md`
- **Vendors / crafting / skills:** `../04_systems/vendors.md`, `../04_systems/crafting.md`, `../04_systems/skills.md`
- **Who plays where** (realm vs instance, friends/solo): `../04_systems/player_server_cardinality.md`
- Open numbers (maps, time split, player counts): `scale_and_unresolved.md`
- Combat tone: `design_goals.md`
