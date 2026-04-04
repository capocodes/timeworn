# Looting *(stub)*

**Purpose:** The **act of picking up loot** — from enemy drops, world containers, player bodies, and resource nodes. Feeds [Player Inventory](player_inventory.md).

## Intent

- **Sources:** [Pawn Loot](pawn_loot.md) drops (enemies, players), world containers (crates, stashes), [Mining Behaviors](mining_behaviors.md) output, crafting station output.
- **UX:** Proximity prompt vs dedicated loot screen vs auto-pickup by tier — TBD.
- **Tension:** Looting should cost **time and attention** (you're vulnerable while looting in PvPvE) — align with [Design Goals](../01_vision/design_goals.md) (deliberate pace, no safe zones).
- **Loot tiers** affect visual / audio feedback on pickup ([Weapons & Loot Tiers](weapons_loot_tiers.md)).

## Open

- [ ] Loot interaction model (hold-to-loot, quick-grab, loot menu).
- [ ] Contested loot rules (first-touch, proximity priority, free-for-all).
- [ ] World container placement and respawn cadence.
