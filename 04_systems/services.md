# External services (backend) *(stub)*

**Purpose:** Backend infrastructure that game systems talk to over the network. These are **not** in-engine gameplay systems — they're the persistent, authoritative layer that lives outside any single raid instance.

---

## User Profile

Account identity, settings, entitlements. Source of truth for "who is this player."

- **Data:** Unique ID, display name, platform links (Steam, Epic, console), settings sync, owned DLC / cosmetic unlocks.
- **Consumers:** Friends, Stats, Stash, [Session Flow](session_flow.md) (identity in party + queue).
- **Open:** Provider (EOS, Steam, PlayFab, custom); cross-platform linking; guest/anonymous play.

## Friends

Social graph — friend lists, invites, presence (online / in-raid / in-base).

- **Data:** Add/remove/block, platform friends import, online status.
- **Consumers:** [Session Flow](session_flow.md) (party invite), [Player ↔ Server Cardinality](player_server_cardinality.md) (same-realm recommendation).
- **Open:** Provider; block/mute persistence and interaction with [Voice Chat](voice_chat.md); recent players list.

## Matchmaking

Server-side match placement — receives queue requests and assigns parties to raid instances.

- **Data:** Queue management, region/skill grouping, instance allocation.
- **Consumers:** [Session Flow](session_flow.md) (client sends queue, receives connection info), [Multiplayer](multiplayer.md) (connects to allocated instance), [Gameplay Manager](gameplay_manager.md) (session starts once placed).
- **Open:** Provider (EOS, Agones, custom); skill brackets; instance lifecycle (pre-warmed pool vs on-demand).

## Stats

Persistent player statistics — lifetime and seasonal.

- **Data:** Raids completed, extractions, deaths, enemies killed, loot extracted, buildings placed, Exodus completions. Seasonal slice resets on boundary ([Resets & World Events](../01_vision/resets_and_world_events.md)).
- **Consumers:** [Gameplay Manager](gameplay_manager.md) (pushes round results), User Profile (stats attached to account), client UI (profile, [Round Review](round_review.md)).
- **Open:** Provider; anti-cheat validation before writes; public vs private stats.

## Stash

Server-authoritative persistent storage for the **bank vault**.

- **Data:** Vault contents that survive across raids and weekly hub resets ([Vault & Loadout](vault_and_loadout.md)).
- **Read:** Serve vault to [Stash Service Client](stash_service_client.md) on login / pre-raid.
- **Write:** Accept extracted loot after successful [Extraction](extraction.md); reject invalid mutations (anti-dupe).
- **Validation:** Authoritative source for what the player owns; raid servers check loadout legitimacy before deploy.
- **Open:** Storage backend; transaction model; backup/rollback; vault capacity limits.

---

*All services are **TBD on provider** until engineering scope is locked. Slice v1 can stub most of these with local persistence or a simple backend.*
