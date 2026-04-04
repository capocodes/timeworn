# Service — Stash *(stub)*

**Type:** External / backend service

**Purpose:** **Server-authoritative** persistent storage for the **bank vault** — the inventory that survives across raids and weekly hub resets ([Vault & Loadout](vault_and_loadout.md)).

## Responsibilities

- **Read:** Serve vault contents to the [Stash Service Client](stash_service_client.md) on login and pre-raid.
- **Write:** Accept extracted loot after successful [Extraction](extraction.md); reject invalid mutations (anti-dupe).
- **Weekly reset:** Vault **persists** through hub wipe; only base state resets ([Resets & World Events](../01_vision/resets_and_world_events.md)).
- **Seasonal rules:** May apply vault taxes or soft-resets on season boundary — TBD.
- **Validation:** Authoritative source for **what the player actually owns**; raid servers check loadout legitimacy against this before deploy.

## Consumers

- [Stash Service Client](stash_service_client.md) — game-side read/write interface.
- [Lobby](lobby.md) — loadout selection pulls from vault.
- [Gameplay Manager](gameplay_manager.md) — post-raid loot deposit.
- Raid server — loadout validation on join.

## Open

- [ ] Storage backend (database, cloud save, provider).
- [ ] Transaction model (optimistic, pessimistic locking).
- [ ] Backup / rollback for exploits or data loss.
- [ ] Capacity limits on vault size.
