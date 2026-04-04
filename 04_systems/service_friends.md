# Service — Friends *(stub)*

**Type:** External / backend service

**Purpose:** Social graph — **friend lists, invites, presence** (online / in-raid / in-base). Enables party formation before raids.

## Responsibilities

- **Friend list:** Add / remove / block. Platform friends import (Steam, Epic, console).
- **Presence:** Show friend status (online, in-lobby, in-raid, offline).
- **Invites:** "Join my party" / "Join my base session" — hands off to [Lobby](lobby.md) for party formation.
- **Cross-platform:** Friends across PC / console (if supported).

## Consumers

- [Lobby](lobby.md) (party invite flow).
- [Matchmaking](matchmaking.md) (party-queue requires friend/party state).
- [Player ↔ Server Cardinality](player_server_cardinality.md) (same-realm recommendation for friends).

## Open

- [ ] Provider (EOS, Steam, custom).
- [ ] Block / mute persistence and interaction with [Voice Chat](voice_chat.md).
- [ ] Recent players list (post-raid).
