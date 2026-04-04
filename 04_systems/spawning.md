# Spawning *(stub)*

**Purpose:** Rules for **where and when** players and enemies appear in a raid instance.

## Intent

### Player spawning
- **Initial deploy:** Party spawns together at session start; spawn location per map / tier.
- **Respawn (TBD):** Do players respawn after death in-raid, or is death = run over? Critical to session stakes.

### Enemy spawning
- **Tier-scaled:** Easy bots (tier 1), medium (tier 2), hard (tier 3) — [Game Loop](../01_vision/game_loop.md).
- **Spawn triggers:** Static placements, proximity triggers, wave events, [Gameplay Manager](gameplay_manager.md) scripted moments.
- **Density:** Ties to [Scale & Unresolved](../01_vision/scale_and_unresolved.md) (map size, player count).

## Open

- [ ] Player respawn rules (permadeath per raid, limited lives, squad revive).
- [ ] Enemy respawn cadence (one-shot spawns vs repopulating zones).
- [ ] Boss / elite spawn conditions.
- [ ] Spawn protection (brief invulnerability on deploy).
