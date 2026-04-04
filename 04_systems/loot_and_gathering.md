# Loot & gathering *(stub)*

**Purpose:** Everything about how items **enter the player's hands** during a raid — enemy drops, world containers, player bodies, and resource nodes. Consolidates pawn loot, looting UX, and mining/gathering into one system.

## Pawn loot (drops)

- On **enemy death:** Generate a loot drop from that enemy's table (robot salvage feeds [Crafting](crafting.md) and future-tech progression — [Enemies](enemies_future_robots.md)).
- On **player death:** Rules for what stays on the body vs what's lost — TBD (ties to risk/reward per the [Game Loop](../01_vision/game_loop.md) and [Death & Respawn](death_and_respawn.md)).
- **Loot quality** scales with tier (low → high) per macro loop.
- **Drop tables:** Flat list, weighted, contextual by tier/zone — TBD.

## Pickup (the act of looting)

- **Sources:** Enemy/player drops, world containers (crates, stashes), resource node output, crafting station output.
- **UX:** Proximity prompt vs dedicated loot screen vs auto-pickup by tier — TBD. Uses the [Interaction System](interaction.md).
- **Tension:** Looting costs **time and attention** — you're vulnerable while looting in PvPvE. Align with [Design Goals](../01_vision/design_goals.md) (deliberate pace, no safe zones).
- **Loot tiers** affect visual / audio feedback on pickup ([Weapons & Loot Tiers](weapons_loot_tiers.md)).

## Resource gathering (mining / harvesting)

- **Node types:** Mineral veins, scrap piles, tech debris, flora — tied to tier / zone.
- **Interaction:** Timed hold / tool-based / animation-gated — player is **vulnerable** while gathering.
- **Output:** Raw materials that feed [Crafting](crafting.md) recipes (workbench, blacksmith, tech buildings).
- **Respawn:** Node depletion + respawn cadence per raid session — TBD.

## Open

- [ ] Drop table structure and weights.
- [ ] Player death loot rules (full drop, partial, insured slots).
- [ ] Loot interaction model (hold-to-loot, quick-grab, loot menu).
- [ ] Contested loot rules (first-touch, proximity priority, free-for-all).
- [ ] World container placement and respawn cadence.
- [ ] Tool requirements for gathering (pickaxe, bare hands, tier-gated).
- [ ] Gathering speed modifiers ([Skills](skills.md), equipment).
- [ ] Contested resource nodes (PvP tension at sites).

---

*Related:* [Inventory & Equipment](inventory_and_equipment.md), [Crafting](crafting.md), [Enemies](enemies_future_robots.md), [Building](building.md), [Death & Respawn](death_and_respawn.md).
