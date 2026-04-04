# Health & damage *(stub)*

**Purpose:** How players and enemies **take hits, lose health, and die**. This is the combat math layer that every weapon, enemy, and hazard feeds into.

## Player health

- **Health pool:** Flat HP value. Scaling per tier / equipment — TBD.
- **Shields / armor:** Optional damage-reduction layer from [Equipment](inventory_and_equipment.md) gear slots. Reduces incoming damage before HP.
- **Healing:** Consumables (bandages, stimpaks?), passive regen, crafted items — sources TBD.
- **Death threshold:** Reaching 0 HP triggers [Death & Respawn](death_and_respawn.md) rules.

## Enemy health

- **HP scaling:** Tied to enemy type/tier ([Enemies](enemies_future_robots.md)). Higher-tier robots have more HP and potentially resistances.
- **Weak points:** Headshots or component damage modifiers — TBD (ties to "deliberate gunplay" pillar).

## Damage model

- **Sources:** Weapons ([Single-Shot Musket](weapon_single_shot_musket.md), future arsenal), enemy attacks, [World Hazards](world_hazards.md) (storms, environmental), fall damage.
- **Calculation:** `base_damage × modifier - damage_reduction`. Modifiers include distance falloff, weak-point multipliers, [Attachment](attachments_catalog.md) bonuses, [Loot Tier](weapons_loot_tiers.md) scaling.
- **TTK target:** **Slow, deliberate** — not twitch. Mid-range engagement distances. Per [Design Goals](../01_vision/design_goals.md), every shot should matter.
- **Friendly fire:** TBD (duo/trio implications).

## Open

- [ ] Exact HP values for player and enemy archetypes.
- [ ] Armor / shield system details (flat reduction, percentage, breakable).
- [ ] Healing item types and availability.
- [ ] Damage falloff curve (range).
- [ ] Status effects (bleed, burn, slow from hazards).
- [ ] Friendly fire rules.
- [ ] How HUD communicates health state ([HUD](hud.md)).

---

*Related:* [Inventory & Equipment](inventory_and_equipment.md), [Enemies](enemies_future_robots.md), [World Hazards](world_hazards.md), [Death & Respawn](death_and_respawn.md), [HUD](hud.md).
