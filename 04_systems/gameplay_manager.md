# Gameplay manager *(stub)*

**Purpose:** Session orchestration — the **authority** that runs a raid from spawn to extract/fail. Owns the clock, tier transitions, win/loss conditions, and round flow.

## Intent

- **Session lifecycle:** Lobby → spawn → raid (tiers 1–3) → extract or fail → round review.
- **Timer / pressure:** Manages the session clock or equivalent pressure mechanic that forces extract decisions ([Core Session Loop](../01_vision/core_extraction_loop.md)).
- **Tier progression:** Tracks which tier the session is in; gates access to higher-tier content, trains, and Exodus ([Game Loop](../01_vision/game_loop.md)).
- **Extract trains:** Triggers train arrivals/departures per tier; manages boarding, countdown, and departure.
- **Win / loss:** Determines session outcome — extracted (with what), died, timed out.

## Open

- [ ] Authority model (dedicated server state vs replicated).
- [ ] How tier transitions are signaled to players (UI, world events, audio cues).
- [ ] Round review data — what the manager passes to post-raid summary.
- [ ] Interaction with [Spawning](spawning.md) (player respawn rules, enemy wave cadence).
