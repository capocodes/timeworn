# Multiplayer *(stub)*

**Purpose:** Networking, replication, and session management for **PvPvE** raids. Slice v1 strip **#9** proves **2-player** stability ([Playable Slice](../05_production/playable_slice_strip_order.md)).

## Intent

- **Topology:** Dedicated server for raids (authoritative PvPvE); base/social hosting model TBD ([Player ↔ Server Cardinality](player_server_cardinality.md)).
- **Replication:** Player state, enemy AI, building placement, loot — all must replicate cleanly.
- **Party sizes:** Solo / duo / trio; how many parties per raid instance is a [Scale & Unresolved](../01_vision/scale_and_unresolved.md) question.
- **Lyra baseline:** Built on Lyra's multiplayer scaffolding ([Tech Baseline](../05_production/tech_baseline.md)).

## Open

- [ ] Player count per instance (teams × players).
- [ ] Replication priorities (what's always replicated vs relevancy-culled).
- [ ] Disconnect / reconnect handling.
- [ ] How [Voice Chat](voice_chat.md) integrates (proximity, party-only, both).
