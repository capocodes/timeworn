# Service — User profile *(stub)*

**Type:** External / backend service

**Purpose:** Persistent **player identity** — account data, display name, linked platforms, settings, and entitlements. Source of truth for "who is this player" across all other services.

## Responsibilities

- **Account record:** Unique ID, display name, platform links (Steam, Epic, console).
- **Settings sync:** Graphics, audio, keybinds, accessibility prefs (persisted server-side so they follow the player across machines).
- **Entitlements:** Owned DLC, battle pass tier, cosmetic unlocks.
- **Privacy / GDPR:** Data export, deletion requests.

## Consumers

- [Friends Service](service_friends.md) (lookup by name / ID).
- [Stats Service](service_stats.md) (attaches stats to account).
- [Stash Service](service_stash.md) (vault ownership).
- [Lobby](lobby.md) / [Matchmaking](matchmaking.md) (identity in party + queue).

## Open

- [ ] Provider (Epic Online Services, Steam, PlayFab, custom).
- [ ] Cross-platform account linking strategy.
- [ ] Guest / anonymous play (if any).
