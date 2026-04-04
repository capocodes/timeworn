# Inventory & equipment *(stub)*

**Purpose:** In-session **carry state** and **active gear** — what the player has, what's equipped, and how it affects gameplay. In Unreal/Lyra these will be one system with equipped slots as a subset of inventory.

## Inventory (carry state)

- **Capacity:** Finite slots / weight — defines how much you can bring out of a run.
- **Sources:** Loadout (pre-raid from [Vault & Loadout](vault_and_loadout.md)), [Loot & Gathering](loot_and_gathering.md) mid-raid, [Crafting](crafting.md) output if in-raid craft exists.
- **Drains:** Using consumables, dropping items, death/fail (rules in [Death & Respawn](death_and_respawn.md)).
- **On extract:** Surviving inventory contents transfer to vault via [Stash Service Client](stash_service_client.md).
- **Slice v1:** Strip **#7** ([Playable Slice](../05_production/playable_slice_strip_order.md)) proves **minimal** carry/equip — enough to feel "I brought this in."

## Equipment (active gear)

- **Weapon slots:** Primary, secondary (+ melee?) — slice v1 proves **one** ([Single-Shot Musket](weapon_single_shot_musket.md)).
- **Gear slots:** Armor / utility / consumable quick-slots — scope TBD.
- **Attachments:** Equipped mods per weapon ([Attachments Catalog](attachments_catalog.md)); hot-swap rules TBD.
- **Stats output:** Equipment feeds **damage**, **protection**, **mobility** modifiers consumed by [Health & Damage](health_and_damage.md) and combat systems.
- **HUD binding:** Equipped state drives [HUD](hud.md) display (ammo, weapon icon, gear status).

## Open

- [ ] Slot model (grid, list, weight-based, hybrid).
- [ ] Stacking / sorting rules.
- [ ] Quick-transfer to vault post-extract.
- [ ] Slot layout for equipment (how many, what types).
- [ ] Equip / unequip timing (instant, animation-gated, context-restricted in raid).
- [ ] How equipment interacts with [Loot Tiers](weapons_loot_tiers.md) visually (silhouette reads tier).

---

*Related:* [Vault & Loadout](vault_and_loadout.md), [Loot & Gathering](loot_and_gathering.md), [Crafting](crafting.md), [Health & Damage](health_and_damage.md), [HUD](hud.md).
