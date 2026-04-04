# 04 — Gameplay & Systems

One primary system per file where practical. **Game systems** run in-engine; **services** are backend / external infrastructure.

---

## Game systems

### Combat & weapons
- [Single-Shot Musket](weapon_single_shot_musket.md) — Slice v1 weapon; **Ferro / Arc Raiders** handling inspiration; mid engagement default.
- [Weapons & Loot Tiers](weapons_loot_tiers.md) — Grey→green→blue→pink→**yellow**; **1850–70** majority; **yellow** = only fully future guns.
- [Attachments Catalog](attachments_catalog.md) — Mods: buffs/nerfs/compat/tier; mostly future; cross-tier mix allowed.
- [Equipment](equipment.md) *(stub)* — Active weapon/gear slots, attachment bindings, stat modifiers.
- [Enemies — Future Robots](enemies_future_robots.md) — PvE AI = future robots; tension pattern + salvage → futuristic craft.
- [Spawning](spawning.md) *(stub)* — Player deploy + enemy spawn rules per tier.

### Loot & inventory
- [Pawn Loot](pawn_loot.md) *(stub)* — What a pawn carries / drops on death.
- [Looting](looting.md) *(stub)* — The act of picking up loot from drops, containers, nodes.
- [Player Inventory](player_inventory.md) *(stub)* — In-session carry state (finite slots / weight).
- [Vault & Loadout](vault_and_loadout.md) — Vault persists through weekly hub wipe; loadout = raid carry.
- [Mining Behaviors](mining_behaviors.md) *(stub)* — Resource gathering from world nodes.

### Building & crafting
- [Building (in-raid)](building.md) *(stub)* — Town claiming, defenses, tech buildings — the RTS-flavored spine.
- [Base Building (between-raid)](base_building.md) — Hub/homestead; *Dune*-inspired; weekly wipe context.
- [Crafting](crafting.md) — Turn loot + parts into items, modules, quest turn-ins.
- [Vendors](vendors.md) — Buy/sell economy between raids.
- [Skills](skills.md) — Progression beyond raw loot power.

### Session & multiplayer
- [Gameplay Manager](gameplay_manager.md) *(stub)* — Session orchestration: clock, tiers, win/loss, extract triggers.
- [Extraction](extraction.md) *(stub)* — Timed train exits; the high-stakes beat that closes runs.
- [Lobby](lobby.md) *(stub)* — Pre-raid staging: party formation, loadout, queue.
- [Matchmaking](matchmaking.md) *(stub)* — Client-side queue logic; talks to backend matchmaking service.
- [Multiplayer](multiplayer.md) *(stub)* — Networking, replication, session management (Lyra baseline).
- [Voice Chat](voice_chat.md) *(stub)* — Party and proximity voice channels.
- [Player ↔ Server Cardinality](player_server_cardinality.md) — Realm model, friends/solo, neighborhood shards.

### Interaction
- [Interaction System](interaction.md) *(stub)* — Generic "press E" framework; routes to loot, build, craft, mine, board, etc.
- [Stash Service Client](stash_service_client.md) *(stub)* — Client-side interface to the backend stash service.

---

## External services (backend)

- [User Profile](service_user_profile.md) *(stub)* — Account identity, settings, entitlements.
- [Friends](service_friends.md) *(stub)* — Social graph, presence, invites.
- [Matchmaking Service](service_matchmaking.md) *(stub)* — Server-side match placement and instance allocation.
- [Stats](service_stats.md) *(stub)* — Lifetime and seasonal player statistics, leaderboards.
- [Stash Service](service_stash.md) *(stub)* — Server-authoritative vault persistence; anti-dupe source of truth.
