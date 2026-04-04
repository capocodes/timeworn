# Pawn loot *(stub)*

**Purpose:** Manages what loot a **pawn** (player or enemy) is carrying / drops on death. Distinct from [Player Inventory](player_inventory.md) (persistent session carry) and the [Vault](vault_and_loadout.md) (between-raid storage).

## Intent

- On **enemy death:** generate a loot drop from that enemy's table (robot salvage feeds [Crafting](crafting.md) and future-tech progression — [Enemies](enemies_future_robots.md)).
- On **player death:** rules for what stays on the body vs what's lost — TBD (ties to risk/reward per the [Game Loop](../01_vision/game_loop.md)).
- **Loot quality** scales with tier (low → high) per macro loop.

## Open

- [ ] Drop table structure (flat list, weighted, contextual by tier/zone).
- [ ] Player death loot rules (full drop, partial, insured slots).
- [ ] Interaction with [Looting](looting.md) system (pickup UX, proximity, timing).
