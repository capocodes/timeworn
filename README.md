# Timeworn

**Multiplayer action sandbox** · Arizona frontier, 1858–1862 · Unreal Engine (Lyra)

---

## What is Timeworn?

You drop into a **grounded Western frontier** where Union soldiers, Apache raiders, and **lethal machines from the future** all compete for the same contested ground. It's **PvPvE** — other players are always a threat, but the real wildcard is AI-controlled **future robots** that are fast, deadly, and drop the tech you need to advance.

**Timeworn isn't an extraction shooter.** Extraction is a *mechanic* (timed train exits that close runs), not the identity. The game is closer to a **strategy-meets-gunplay sandbox** — think the "construction matters" feeling of **StarCraft**, but instead of cranking out troops, you're **building defenses** and advancing tech toward an endgame craftable called **Exodus**.

### The session arc

Every run ramps through **three tiers**:

| Tier | Goal | Loot | Threats |
|------|------|------|---------|
| **1 — Survive** | Scavenge, craft at workbenches & blacksmiths, claim a town site | Low | Easy bots, storms |
| **2 — Build** | Grow the town → tech buildings → place defenses | Medium | Medium bots |
| **3 — Extract** | Push toward **Exodus** (the endgame craftable) → **final extract** | High | Hard bots |

Each tier has its own **extract train** (escalating exit option). You can leave early and keep what you have, or push deeper for better rewards and the Exodus objective.

### Between runs

**Stash & social** — your vault persists across sessions (and weekly hub resets). Choose a loadout from your vault, risk it in the next run, and bring back whatever you extract. Base building, crafting stations, vendors, and social play fill the space between raids.

### Combat

**Deliberate, not twitchy.** Slow TTK, mid-range engagement default, period firearms (single-shot musket in the first slice) with future-tech attachments and weapons earned through robot salvage and crafting. Loot tiers run grey → green → blue → pink → **yellow** (legendary / fully future).

### Setting & tone

**Cinematic Western + slow-reveal sci-fi.** Arizona canyons at golden hour, silhouettes on ridgelines, mystery-first storytelling. The massive mechanical presence is the tone anchor — something is deeply wrong, and neither side can explain it. The frontier looks authentic; the future bleeds in through loot, attachments, and enemies.

---

## Documentation

This repo is the **design and production hub**. Game source and Unreal assets live in the separate **Timeworn** Unreal project (rebased on Epic's Lyra — see [Tech Baseline](05_production/tech_baseline.md)).

**Start here →** [Game Design Document](GAME_DESIGN_DOCUMENT.md) — full GDD with pillars, systems overview, and doc map.

### Repo layout

| Area | Path | Focus |
|------|------|--------|
| Vision | [01_vision/](01_vision/_index.md) | [Game Loop](01_vision/game_loop.md), [Core Session Loop](01_vision/core_extraction_loop.md), [Design Goals](01_vision/design_goals.md), [Meta Loop](01_vision/meta_loop_intent.md) |
| Narrative | [02_narrative/](02_narrative/_index.md) | Story, characters, factions |
| World & levels | [03_world_levels/](03_world_levels/_index.md) | Level flow, beats, layout intent |
| Systems | [04_systems/](04_systems/_index.md) | [Weapons & Loot](04_systems/weapons_loot_tiers.md), [Enemies](04_systems/enemies_future_robots.md), [Crafting](04_systems/crafting.md), [Vault](04_systems/vault_and_loadout.md), [Base Building](04_systems/base_building.md), and more |
| Production | [05_production/](05_production/_index.md) | [Playable Slice](05_production/playable_slice_strip_order.md), [Milestone](05_production/milestone_next_4_weeks.md), [Decisions](05_production/decisions.md) |
| Business | `06_business/` | Pitch, investment, budget |
| Reference | `07_reference/` | Research, mood, links |
| Devlog | [08_devlog/](08_devlog/_index.md) | Video series — outlines & scripts |
| Creative concept | [Concept](arizona_game_concept.md) | Setting, teaser, visual identity, tone |
| Tools | [tools/](tools/README.md) | Python / editor automation |
| Meta | [00_meta/](00_meta/_index.md) | Conventions, assistant notes |

### Working agreement

- One major topic per file where possible.
- Design canon lives under `01_`–`07_`; rolling session notes live in `00_meta/assistant/`.
- When vision and concept diverge, update the [GDD](GAME_DESIGN_DOCUMENT.md) first, then align downstream docs.
