# Stash service client *(stub)*

**Purpose:** Client-side interface to the backend [Stash Service](services.md). Reads/writes **vault** contents, validates loadout selection, and syncs inventory state across sessions.

## Intent

- **Pre-raid:** Pull vault contents → present in [Session Flow](session_flow.md) for loadout selection.
- **Post-raid:** Push extracted loot into vault after [Extraction](extraction.md) / round review.
- **Validation:** Server-authoritative — client requests changes, backend confirms to prevent duping ([Player ↔ Server Cardinality](player_server_cardinality.md) § economy ↔ raids).
- **Weekly reset:** Respects hub wipe schedule ([Resets & World Events](../01_vision/resets_and_world_events.md)); vault persists, base state does not.

## Open

- [ ] Caching strategy (local cache + server diff on login).
- [ ] Conflict resolution (simultaneous edits from different sessions).
- [ ] Offline mode behavior (if any).
