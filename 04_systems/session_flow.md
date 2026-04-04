# Session flow — lobby & matchmaking *(stub)*

**Purpose:** The player-facing journey from **stash & social** into a **raid instance** — party formation, loadout confirmation, queue, and match placement. One system in practice; the backend half lives in [Services](services.md).

## Lobby (pre-raid staging)

- **Party formation:** Solo / duo / trio grouping before queue.
- **Loadout confirmation:** Final gear check from [Vault & Loadout](vault_and_loadout.md) before deploying.
- **UI:** Clean session-start flow — slice v1 strip **#3** proves **basic menu** ([Playable Slice](../05_production/playable_slice_strip_order.md)).
- **Location:** Menu screen, physical hub space, or both — TBD.
- **Ready-check / countdown** flow before queue.

## Matchmaking (client-side)

- **Queue types:** Solo queue, party queue (duo/trio pre-formed).
- **Placement:** Match parties into raid instances based on region, skill (TBD), and population.
- **Cross-neighborhood:** If using neighborhood shards ([Player ↔ Server Cardinality](player_server_cardinality.md)), raids draw from a regional pool, not just your home hub.
- **Backend handoff:** Client sends queue request → [Matchmaking Service](services.md) returns instance connection info → [Multiplayer](multiplayer.md) connects.

## Open

- [ ] Lobby location (menu screen, physical hub space, or both).
- [ ] Skill-based matchmaking or open pool.
- [ ] Queue UI / estimated wait time.
- [ ] Backfill rules (join in-progress raid or fresh only).
- [ ] How session flow ties to [Multiplayer](multiplayer.md) session creation.

---

*Related:* [Vault & Loadout](vault_and_loadout.md), [Multiplayer](multiplayer.md), [Services](services.md) (matchmaking backend), [Player ↔ Server Cardinality](player_server_cardinality.md).
