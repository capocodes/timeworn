# 04 — Gameplay & Systems

One primary system per file where practical. **Game systems** run in-engine; **services** are backend / external infrastructure.

---

## Core systems

These are the **load-bearing pillars** — if any one breaks or is missing, the game loop doesn't function. Every other system either feeds into or reads from these.

| Core system | Why it's core | Key doc |
|-------------|---------------|---------|
| **Gameplay Manager** | Owns the session: clock, tier transitions, win/loss, extract triggers. Nothing happens without it. | [Gameplay Manager](gameplay_manager.md) |
| **Player Inventory** | In-session carry state. Every loot, craft, equip, and extract action reads or writes inventory. | [Player Inventory](player_inventory.md) |
| **Equipment** | What's actively equipped drives combat stats, HUD, and animation state. | [Equipment](equipment.md) |
| **Building (in-raid)** | The strategy spine — town, tech, defenses, Exodus. Defines the mid/late game. | [Building](building.md) |
| **Extraction** | The mechanic that closes runs and gives loot meaning. No extract = no stakes. | [Extraction](extraction.md) |
| **Multiplayer** | Replication layer — everything above must work across the network. | [Multiplayer](multiplayer.md) |

---

## System dependency map

How systems connect. **→** means "feeds into / is consumed by." Read left to right: the source produces something the target needs.

```
                         ┌─────────────────────────────────────────────┐
                         │           GAMEPLAY MANAGER                  │
                         │  session clock · tier gates · win/loss      │
                         └──┬──────┬──────┬───────┬──────────┬────────┘
                            │      │      │       │          │
                    triggers│      │gates │       │results   │triggers
                            ▼      ▼      ▼       ▼          ▼
                        Spawning  Building Extraction    Stats Service
                         ▲  │      ▲          ▲
            tier scaling │  │drops │materials  │boarding
                         │  ▼      │          │
                       Enemies ────┘    ┌─────┘
                         │              │
                  salvage│         board │
                         ▼              │
   Mining ──────► Pawn Loot ──► Looting ┤
   Behaviors       (drops)    (pickup)  │
                                │       │
                          into  ▼       │
                       Player Inventory─┤
                         │    ▲         │
                  equip  │    │craft    │
                         ▼    │output   │
                      Equipment         │
                         │    ▲         │
                  stats  │    │         │
                         ▼    │         │
     Weapons &     ◄── Crafting         │
     Loot Tiers      ▲                  │
        │            │recipes           │
        │            │                  │
        ▼         Skills                │
     Attachments     ▲                  │
     Catalog         │unlock            │
                     │                  │
                  Vendors               │
                                        │
   ┌────────────────────────────────────┘
   │
   ▼
Vault & Loadout ◄──► Stash Service Client ◄──► Stash Service (backend)
   │
   │loadout
   ▼
 Lobby ──► Matchmaking ──► Matchmaking Service (backend)
   ▲                              │
   │party                         │instance
   │                              ▼
Friends Service ◄── User Profile   Multiplayer ◄──► Voice Chat
                    Service            │
                        ▲              │replicates all
                        │              ▼
                    Stats Service   [all game systems]
```

### Reading the map

- **Gameplay Manager** is the root authority — it drives the session clock, triggers spawning waves, gates tier transitions for building, fires extract trains, and pushes round results to the Stats Service.
- **Player Inventory** is the central data bus for in-raid state — loot flows in (from Looting), gear flows out (to Equipment), materials flow out (to Crafting / Building), and surviving contents flow to the Vault on extract.
- **Building** consumes crafted materials and loot; its progression (defenses complete → Exodus unlocked) feeds back to the Gameplay Manager for tier gating.
- **Extraction** is triggered by the Gameplay Manager (train schedule) and reads from Player Inventory (what you're taking out); on success it writes to Vault via Stash Service Client.
- **Multiplayer** sits underneath everything — every system's state changes must replicate through it.
- **Interaction System** (not shown to keep the map readable) is the universal input router — it sits between the player and Looting, Mining, Building, Crafting, Extraction boarding, and Vendors.

---

## All game systems

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
