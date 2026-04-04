# Service — Matchmaking *(stub)*

**Type:** External / backend service

**Purpose:** Server-side **match placement** — receives queue requests from the game-side [Matchmaking](matchmaking.md) system and assigns parties to raid instances.

## Responsibilities

- **Queue management:** Accept solo / party queue requests; group by region and (optionally) skill bracket.
- **Instance allocation:** Spin up or assign a raid server instance; return connection info to clients.
- **Population rules:** Min / max players per instance; backfill policy.
- **Cross-neighborhood:** If using neighborhood shards ([Player ↔ Server Cardinality](player_server_cardinality.md)), draw from regional pool regardless of home hub.

## Consumers

- [Matchmaking (game system)](matchmaking.md) — client-side queue UI and flow.
- [Multiplayer](multiplayer.md) — receives server address to connect.
- [Gameplay Manager](gameplay_manager.md) — session starts once players are placed.

## Open

- [ ] Provider (EOS matchmaking, Agones, custom).
- [ ] Skill-based vs open brackets.
- [ ] Instance lifecycle (pre-warmed pool vs on-demand).
