# Service — Stats *(stub)*

**Type:** External / backend service

**Purpose:** Persistent **player statistics** — lifetime and seasonal. Tracks performance, progression milestones, and leaderboard data.

## Responsibilities

- **Lifetime stats:** Raids completed, extractions, deaths, enemies killed, loot extracted, buildings placed, Exodus completions.
- **Seasonal stats:** Per-season slice of the above; reset on season boundary ([Resets & World Events](../01_vision/resets_and_world_events.md)).
- **Leaderboards:** Regional / global rankings if competitive seasons are added.
- **Feeds:** Round review screen (post-raid summary), profile display, achievement triggers.

## Consumers

- [Gameplay Manager](gameplay_manager.md) — pushes round results after extract / fail.
- [User Profile Service](service_user_profile.md) — stats attached to account.
- Client UI — profile screen, post-raid summary.

## Open

- [ ] Provider (PlayFab, EOS Stats, custom).
- [ ] Anti-cheat validation before stat writes.
- [ ] Which stats are public vs private.
