# High-level design goals

*Directional targets — not final tuning numbers. Refine as you playtest.*

**Session truth:** Macro structure (**tiers, trains, craft/town/build/exodus**) — [Game Loop](game_loop.md). Raid steps and **nine-strip** mapping — [Core Session Loop](core_extraction_loop.md). The **vertical slice** is the **tier-1 spine** of that loop (see [Playable Slice — Strip Order](../05_production/playable_slice_strip_order.md)). **Meta** between raids: [Meta Loop](meta_loop_intent.md). **Scale / counts TBD:** [Scale & Unresolved](scale_and_unresolved.md).

## Scope philosophy (breadth vs depth)

- **Few systems, each strong:** The vertical slice **limits how many** systems ship (see [Playable Slice — Strip Order](../05_production/playable_slice_strip_order.md)) so scope stays bounded — but **each included system should feel fleshed out and excellent**, not "greybox until later."
- **What we avoid:** **Feature creep** *inside* a system before the **full loop** works (e.g. second gun, enemy roster, full settings menu). **Depth** means **this musket / this HUD / this extract beat** reads **great**, not **more** systems.
- Narrow **count** + high **bar** = the game reads as **intentional** in devlogs and playtests, not a tech demo glued together.

## Combat pace & TTK

- **Intent:** **Slow, methodical shooter** — deliberate gunplay over twitch.
- **TTK band (verbal anchor):** **Longer** than *Counter-Strike*–style **fast deletes**; **faster** than *Dune: Awakening*–style **long spongy** encounters. Exact curves (armor, HS multipliers, healing) TBD in systems docs later.

## Engagement distances

- **Vertical slice default:** **Mid** — primary band so the first build can **show a useful range** (not purely CQB or purely optic lanes) while staying readable to playtest.
- **Still TBD:** How far **long** pushes before it's non-viable for slice v1; how **close** quarters compress TTK; level metrics (sightlines, cover spacing) — tune after first pocket env + musket pass.

## Social / session integrity

- **Anti-grief** — design for **reducing bad-faith disruption** without killing tension (specific mechanics: TBD under systems/production).

## World structure (PvPvE)

- **Mode:** **PvPvE always** — players, hostile **AI**, and **environmental** pressure in the same contested space. **AI combatants** are **future robots** (see [Enemies — Future Robots](../04_systems/enemies_future_robots.md)); **human** tension is **players / factions**, not "extra bandit mobs."
- **No safe zones** — nowhere is a **completely** risk-free hub **in raid spaces**; any "relative safety" is **temporary or earned**. **Exception (intent):** **base / social** layer may be **PvE-only** — see [Meta Loop](meta_loop_intent.md); marketing and this pillar must **not contradict** each other once base is public.

---

*Related:* [Concept](../arizona_game_concept.md) (premise/tone), [Game Loop](game_loop.md), [Core Session Loop](core_extraction_loop.md), [Meta Loop](meta_loop_intent.md), [Vendors](../04_systems/vendors.md), [Crafting](../04_systems/crafting.md), [Skills](../04_systems/skills.md), [Player ↔ Server Cardinality](../04_systems/player_server_cardinality.md), [Scale & Unresolved](scale_and_unresolved.md), [Playable Slice](../05_production/playable_slice_strip_order.md) (nine strips + quality bar per strip).
