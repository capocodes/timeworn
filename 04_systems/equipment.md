# Equipment *(stub)*

**Purpose:** What's **actively equipped** on the player — weapon slots, armor/gear slots, attachment bindings. Subset of [Player Inventory](player_inventory.md); feeds into HUD state and combat stats.

## Intent

- **Weapon slots:** Primary, secondary (+ melee?) — slice v1 proves **one** ([Single-Shot Musket](weapon_single_shot_musket.md)).
- **Gear slots:** Armor / utility / consumable quick-slots — scope TBD.
- **Attachments:** Equipped mods per weapon ([Attachments Catalog](attachments_catalog.md)); hot-swap rules TBD.
- **Stats:** Equipment feeds **damage**, **protection**, **mobility** modifiers read by combat systems.

## Open

- [ ] Slot layout (how many, what types).
- [ ] Equip / unequip timing (instant, animation-gated, context-restricted in raid).
- [ ] How equipment interacts with [Loot Tiers](weapons_loot_tiers.md) visually (silhouette reads tier).
