# 04 — Gameplay & Systems

One primary system per file where practical. **Game systems** run in-engine; **services** are backend / external infrastructure.

---

## Core systems

These are the **load-bearing pillars** — if any one breaks or is missing, the game loop doesn't function. Every other system either feeds into or reads from these.

| Core system | Why it's core | Key doc |
|-------------|---------------|---------|
| **Gameplay Manager** | Owns the session: clock, tier transitions, win/loss, extract triggers. Nothing happens without it. | [Gameplay Manager](gameplay_manager.md) |
| **Inventory & Equipment** | In-session carry state plus active gear. Every loot, craft, equip, and extract action reads or writes here. | [Inventory & Equipment](inventory_and_equipment.md) |
| **Building (in-raid)** | The strategy spine — town, tech, defenses, Exodus. Defines the mid/late game. | [Building](building.md) |
| **Extraction** | The mechanic that closes runs and gives loot meaning. No extract = no stakes. | [Extraction](extraction.md) |
| **Health & Damage** | Combat math layer — every weapon, enemy, and hazard feeds into it. | [Health & Damage](health_and_damage.md) |
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
                        Spawning  Building Extraction  ─► Round Review
                         ▲  │      ▲          ▲               │
            tier scaling │  │drops │materials  │boarding       │stats
                         │  ▼      │          │               ▼
                       Enemies ────┘    ┌─────┘          Services
                         │              │              (Stats, Stash,
                  salvage│         board│               Profile, etc.)
                         ▼              │
     Loot & Gathering ─────────────────┤
     (drops · pickup · mining)         │
                         │              │
                   into  ▼              │
                   Inventory &         │
                   Equipment ──────────┤
                         │    ▲        │
                  stats  │    │craft   │
                         ▼    │output  │
  Health &         ◄── Crafting        │
  Damage ◄── Weapons    ▲             │
    ▲         & Tiers    │recipes      │
    │            │       │             │
    │            ▼    Skills           │
    │        Attachments  ▲            │
    │        Catalog      │unlock      │
    │                     │            │
    │                  Vendors          │
    │                                  │
    │  World                           │
    │  Hazards ─► env damage           │
    │                                  │
    ├── HUD (reads health, ammo,       │
    │        extraction timer, tier)   │
    │                                  │
   ┌┘──────────────────────────────────┘
   │
   ▼
Vault & Loadout ◄──► Stash Service Client ◄──► Services (Stash)
   │
   │loadout
   ▼
Session Flow ──────────────────────────► Services (Matchmaking)
(lobby · matchmaking)                         │
   ▲                                          │instance
   │party                                     ▼
Services (Friends) ◄── Services        Multiplayer ◄──► Voice Chat
                       (User Profile)       │
                                            │replicates all
                                            ▼
                                       [all game systems]
```

### Reading the map

- **Gameplay Manager** is the root authority — it drives the session clock, triggers spawning waves, gates tier transitions for building, fires extract trains, and pushes round results to Stats.
- **Inventory & Equipment** is the central data bus for in-raid state — loot flows in (from Loot & Gathering), gear equips out (to Health & Damage as stat modifiers), materials flow out (to Crafting / Building), and surviving contents flow to the Vault on extract.
- **Health & Damage** is the combat math layer — weapons, enemies, and world hazards all feed damage in; equipment feeds damage reduction; the output is HP state rendered by HUD and consumed by Death & Respawn.
- **Building** consumes crafted materials and loot; its progression (defenses complete → [Exodus](exodus.md) unlocked) feeds back to the Gameplay Manager for tier gating.
- **Extraction** is triggered by the Gameplay Manager (train schedule) and reads from Inventory (what you're taking out); on success it writes to Vault via Stash Service Client.
- **Multiplayer** sits underneath everything — every system's state changes must replicate through it.
- **Interaction System** (not shown to keep the map readable) is the universal input router — it sits between the player and Loot & Gathering, Building, Crafting, Extraction boarding, and Vendors.

---

## All game systems

### Combat & survival
- [Health & Damage](health_and_damage.md) *(stub)* — HP, armor, damage calc, TTK target, healing.
- [Death & Respawn](death_and_respawn.md) *(stub)* — What happens at 0 HP; loot penalties, respawn rules.
- [Single-Shot Musket](weapon_single_shot_musket.md) — Slice v1 weapon; **Ferro / Arc Raiders** handling inspiration; mid engagement default.
- [Weapons & Loot Tiers](weapons_loot_tiers.md) — Grey→green→blue→pink→**yellow**; **1850–70** majority; **yellow** = only fully future guns.
- [Attachments Catalog](attachments_catalog.md) — Mods: buffs/nerfs/compat/tier; mostly future; cross-tier mix allowed.
- [Enemies — Future Robots](enemies_future_robots.md) — PvE AI = future robots; tension pattern + salvage → futuristic craft.
- [Spawning](spawning.md) *(stub)* — Player deploy + enemy spawn rules per tier.
- [World Hazards](world_hazards.md) *(stub)* — Storms, environmental threats, zone danger scaling.

### Loot & inventory
- [Loot & Gathering](loot_and_gathering.md) *(stub)* — Pawn drops, pickup UX, resource node mining — all in one.
- [Inventory & Equipment](inventory_and_equipment.md) *(stub)* — In-session carry state + active weapon/gear slots.
- [Vault & Loadout](vault_and_loadout.md) — Vault persists through weekly hub wipe; loadout = raid carry.

### Building & crafting
- [Building (in-raid)](building.md) *(stub)* — Town claiming, defenses, tech buildings — the RTS-flavored spine.
- [Base Building (between-raid)](base_building.md) — Hub/homestead; *Dune*-inspired; weekly wipe context.
- [Crafting](crafting.md) — Turn loot + parts into items, modules, quest turn-ins.
- [Exodus](exodus.md) *(stub)* — The endgame craftable objective; completion triggers the Final Extract.
- [Vendors](vendors.md) — Buy/sell economy between raids.
- [Skills](skills.md) — Progression beyond raw loot power.

### Session & multiplayer
- [Gameplay Manager](gameplay_manager.md) *(stub)* — Session orchestration: clock, tiers, win/loss, extract triggers.
- [Extraction](extraction.md) *(stub)* — Timed train exits; the high-stakes beat that closes runs.
- [Session Flow](session_flow.md) *(stub)* — Lobby + matchmaking: party → loadout → queue → instance.
- [Multiplayer](multiplayer.md) *(stub)* — Networking, replication, session management (Lyra baseline).
- [Voice Chat](voice_chat.md) *(stub)* — Party and proximity voice channels.
- [Player ↔ Server Cardinality](player_server_cardinality.md) — Realm model, friends/solo, neighborhood shards.
- [Round Review](round_review.md) *(stub)* — Post-raid summary: loot, stats, vault transfer, return to menu.

### Interaction & UI
- [Interaction System](interaction.md) *(stub)* — Generic "press E" framework; routes to loot, build, craft, mine, board, etc.
- [HUD & UI](hud.md) *(stub)* — In-raid information layer: health, ammo, timers, prompts (Lyra CommonUI).
- [Stash Service Client](stash_service_client.md) *(stub)* — Client-side interface to the backend stash service.

---

## External services (backend)

All five services consolidated into one doc — provider decisions are TBD until engineering scope is locked.

- [External Services](services.md) *(stub)* — User Profile, Friends, Matchmaking, Stats, Stash.
