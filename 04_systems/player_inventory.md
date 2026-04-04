# Player inventory *(stub)*

**Purpose:** In-session **carry state** — what the player has on them during a raid. Separate from [Vault & Loadout](vault_and_loadout.md) (between-raid persistence) and [Equipment](equipment.md) (what's actively equipped).

## Intent

- **Capacity:** Finite slots / weight — defines how much you can bring out of a run.
- **Sources:** Loadout (pre-raid), [Looting](looting.md) mid-raid, [Crafting](crafting.md) output if in-raid craft exists.
- **Drains:** Using consumables, dropping items, death/fail (rules TBD in [Pawn Loot](pawn_loot.md)).
- **Slice v1:** Strip **#7** ([Playable Slice](../05_production/playable_slice_strip_order.md)) proves **minimal** carry/equip — enough to feel "I brought this in."

## Open

- [ ] Slot model (grid, list, weight-based, hybrid).
- [ ] Stacking / sorting rules.
- [ ] Quick-transfer to vault post-extract.
