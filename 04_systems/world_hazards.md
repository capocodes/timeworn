# World hazards *(stub)*

**Purpose:** Environmental threats that exist **outside of direct PvP or PvE combat** — storms, radiation, temperature, terrain traps. These create time pressure and force movement, feeding the "no safe zones" philosophy.

## Intent

- **Storms / dust events:** Periodic map-wide or zone-based hazards that reduce visibility, deal tick damage, or restrict movement. Mentioned in the [Game Loop](../01_vision/game_loop.md) as an environmental pressure layer.
- **Zone danger scaling:** Higher-tier zones have harsher environmental conditions, reinforcing the risk/reward gradient of the loot tiers.
- **Extraction pressure:** Hazards can push players **toward** extraction points or **away** from camping spots, keeping the session dynamic.
- **Damage output:** Feeds into [Health & Damage](health_and_damage.md) as an environmental damage source. Mitigation via gear ([Inventory & Equipment](inventory_and_equipment.md)) possible.
- **Visual / audio warning:** Approaching hazards give advance warning through [HUD](hud.md) and ambient cues.

## Examples (TBD)

| Hazard | Effect | Scope |
|---|---|---|
| Dust storm | Reduced visibility, minor tick damage | Map-wide, periodic |
| Time rift | High damage zone, rare loot near edges | Localized, semi-random |
| Heat wave | Stamina drain, movement slow | Zone-based, tier-scaled |
| Structural collapse | Instant death / heavy damage on triggered areas | Point hazard, static |

## Open

- [ ] How many hazard types for v1 (or skip hazards for slice?).
- [ ] Timer / cadence for storms (fixed schedule, random, tier-triggered).
- [ ] Can players prepare for hazards (gear, shelter, building)?
- [ ] Interaction with [Building](building.md) — do built structures provide shelter?
- [ ] Audio/visual design for hazard warnings.

---

*Related:* [Game Loop](../01_vision/game_loop.md), [Health & Damage](health_and_damage.md), [Building](building.md), [HUD](hud.md), [Gameplay Manager](gameplay_manager.md).
