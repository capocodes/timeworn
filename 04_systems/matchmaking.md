# Matchmaking — game system *(stub)*

**Purpose:** Client-side and gameplay logic for **finding and joining** raid instances. Works with the backend [Matchmaking Service](service_matchmaking.md) and the [Lobby](lobby.md).

## Intent

- **Queue types:** Solo queue, party queue (duo/trio pre-formed).
- **Placement:** Match parties into raid instances based on region, skill (TBD), and population.
- **Cross-neighborhood:** If using neighborhood shards ([Player ↔ Server Cardinality](player_server_cardinality.md)), raids draw from a regional pool, not just your home hub.

## Open

- [ ] Skill-based matchmaking or open pool.
- [ ] Queue UI / estimated wait.
- [ ] Backfill rules (join in-progress raid or fresh only).
- [ ] How this system talks to the [Matchmaking Service](service_matchmaking.md).
