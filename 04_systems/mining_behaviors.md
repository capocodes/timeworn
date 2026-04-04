# Mining behaviors *(stub)*

**Purpose:** Resource-gathering interactions with **world nodes** — ore, salvage deposits, harvestable materials. Feeds [Crafting](crafting.md) and [Player Inventory](player_inventory.md).

## Intent

- **Node types:** Mineral veins, scrap piles, tech debris, flora (if applicable) — tied to tier / zone in the [Game Loop](../01_vision/game_loop.md).
- **Interaction:** Timed hold / tool-based / animation-gated — player is **vulnerable** while mining (PvPvE tension).
- **Output:** Raw materials that feed [Crafting](crafting.md) recipes (workbench, blacksmith, tech buildings).
- **Respawn:** Node depletion + respawn cadence per raid session (or persistent across session? — TBD).

## Open

- [ ] Tool requirements (pickaxe, bare hands, tier-gated tools).
- [ ] Mining speed modifiers ([Skills](skills.md), equipment).
- [ ] Contested nodes (PvP tension at resource sites).
- [ ] Visual / audio feedback (progress bar, particles, sound).
