# Scale & unresolved session model

**Explicit TBDs** that affect **level design**, **networking**, **pacing**, and **base vs raid** investment. **Decide deliberately**—these are not “details later”; they steer everything.

## Map scale

- **How big** are **raid** maps (km feel, POI count, traversal time)?
- **Open world** vs **directed districts** vs **mixed**?
- **Extraction train** — linear corridor to exit vs open-world “get to station”?

*Status:* **Unresolved.**

## Base vs extraction (time & content)

- **Rough target:** What % of a player’s session or week is **in raid** vs **in base / social**?
- Does **base** compete with **raid** for art/engine bandwidth in early milestones?
- **Hosting:** **Cloud/realm** vs **locally hosted base** (listen/P2P) vs **hybrid** — see `../04_systems/player_server_cardinality.md` § *Locally hosted base*.

*Status:* **Unresolved.**

## Server & player cardinality

- **Players per raid instance** — duo/trio **teams**; **how many teams** per map (e.g. 12–24+ players)? **Solo queue** behavior?
- **Server topology** — dedicated servers, listen, hybrid; **who hosts** for slice vs ship?
- **Persistence** — what survives between raids for **inventory**, **base**, **quests**?
- **Character ↔ realm** — “**One character per server**” vs **global account**; **friends** (same realm, party queue) vs **solo** (matchmaking) — **working patterns** in **`../04_systems/player_server_cardinality.md`**.
- **Neighborhood shards** — e.g. many hubs **~100 players** each, **raids cross-instance**; **underload** → **portable base / migration** vs merge — see **pattern 4** in that doc.

*Status:* **Unresolved** at numeric level. *(Slice: **2P** + one dev realm; does not lock production scale.)*

## Lore hooks tied to scale

- **Why MUST you extract** (timer pressure) — narrative spec lives with `core_extraction_loop.md` until broken out to `../02_narrative/`.

---

*When you lock numbers, add a row to `../05_production/decisions.md` and trim this file.*
