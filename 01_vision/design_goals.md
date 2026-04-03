# High-level design goals

*Directional targets — not final tuning numbers. Refine as you playtest.*

**Session truth:** Macro structure (**tiers, trains, craft/town/build/exodus**) — **`game_loop.md`**. Raid steps and **nine-strip** mapping — **`core_extraction_loop.md`**. The **vertical slice** is the **tier-1 spine** of that loop (see `../05_production/playable_slice_strip_order.md`). **Meta** between raids: **`meta_loop_intent.md`**. **Scale / counts TBD:** **`scale_and_unresolved.md`**.

## Scope philosophy (breadth vs depth)

- **Few systems, each strong:** The vertical slice **limits how many** systems ship (see `../05_production/playable_slice_strip_order.md`) so scope stays bounded — but **each included system should feel fleshed out and excellent**, not “greybox until later.”
- **What we avoid:** **Feature creep** *inside* a system before the **full loop** works (e.g. second gun, enemy roster, full settings menu). **Depth** means **this musket / this HUD / this extraction** reads **great**, not **more** systems.
- Narrow **count** + high **bar** = the game reads as **intentional** in devlogs and playtests, not a tech demo glued together.

## Combat pace & TTK

- **Intent:** **Slow, methodical shooter** — deliberate gunplay over twitch.
- **TTK band (verbal anchor):** **Longer** than *Counter-Strike*–style **fast deletes**; **faster** than *Dune: Awakening*–style **long spongy** encounters. Exact curves (armor, HS multipliers, healing) TBD in systems docs later.

## Engagement distances

- **Vertical slice default:** **Mid** — primary band so the first build can **show a useful range** (not purely CQB or purely optic lanes) while staying readable to playtest.
- **Still TBD:** How far **long** pushes before it’s non-viable for slice v1; how **close** quarters compress TTK; level metrics (sightlines, cover spacing) — tune after first pocket env + musket pass.

## Social / session integrity

- **Anti-grief** — design for **reducing bad-faith disruption** without killing tension (specific mechanics: TBD under systems/production).

## World structure (PvPvE)

- **Mode:** **PvPvE always** — players, hostile **AI**, and **environmental** pressure in the same contested space. **AI combatants** are **future robots** (see `../04_systems/enemies_future_robots.md`); **human** tension is **players / factions**, not “extra bandit mobs.”
- **No safe zones** — nowhere is a **completely** risk-free hub **in raid spaces**; any “relative safety” is **temporary or earned**. **Exception (intent):** **base / social** layer may be **PvE-only** — see `meta_loop_intent.md`; marketing and this pillar must **not contradict** each other once base is public.

---

*Related:* `../arizona_game_concept.md` (premise/tone), `game_loop.md`, `core_extraction_loop.md`, `meta_loop_intent.md`, `../04_systems/vendors.md`, `../04_systems/crafting.md`, `../04_systems/skills.md`, `../04_systems/player_server_cardinality.md`, `scale_and_unresolved.md`, `../05_production/playable_slice_strip_order.md` (nine strips + quality bar per strip).
