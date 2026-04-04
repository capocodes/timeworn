# HUD & UI *(stub)*

**Purpose:** On-screen information layer during a raid — health bars, ammo, inventory, objective markers, extraction timers. Built on **Lyra's CommonUI / UMG** foundation ([Tech Baseline](../05_production/tech_baseline.md)).

## In-raid HUD

- **Health state:** HP bar, shield/armor indicator, damage direction — fed by [Health & Damage](health_and_damage.md).
- **Ammo / weapon:** Active weapon icon, ammo count, reload prompt — fed by [Inventory & Equipment](inventory_and_equipment.md).
- **Extraction timer:** Countdown to next train departure and boarding zone markers — fed by [Extraction](extraction.md) and [Gameplay Manager](gameplay_manager.md).
- **Tier indicator:** Current session tier (Survive / Build / Extract) and loot band — fed by [Gameplay Manager](gameplay_manager.md).
- **Interaction prompt:** Context-sensitive "Press E" / hold prompts — fed by [Interaction](interaction.md).
- **Minimap / compass:** Spatial awareness layer — scope TBD.

## Menus & screens

- **Inventory screen:** In-raid carry state view, equip/drop actions — [Inventory & Equipment](inventory_and_equipment.md).
- **Crafting UI:** Recipe list, material check — [Crafting](crafting.md).
- **Map / objective overlay:** TBD scope.

## Slice v1

- Strip **#3** ([Playable Slice](../05_production/playable_slice_strip_order.md)): Basic menu (start, lobby, settings).
- Strip **#7**: Minimal HUD — HP, ammo, extraction timer at minimum.

## Open

- [ ] Art direction for HUD (minimal / immersive vs info-dense).
- [ ] Gamepad vs mouse input considerations (CommonUI should help).
- [ ] Damage numbers: show or hide?
- [ ] Ping / squad communication markers (for duo/trio).
- [ ] Screen-space effects (low-health vignette, storm warning overlay from [World Hazards](world_hazards.md)).

---

*Related:* [Health & Damage](health_and_damage.md), [Inventory & Equipment](inventory_and_equipment.md), [Extraction](extraction.md), [Gameplay Manager](gameplay_manager.md), [Interaction](interaction.md), [Tech Baseline](../05_production/tech_baseline.md).
