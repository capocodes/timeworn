# Timeworn — Design & Production Hub

Design docs, production tracking, devlog scripts, and tooling for **Timeworn**. Game source and Unreal assets live in the separate Unreal project **Timeworn** (not this folder). **Engine baseline:** project is **rebased on Epic's Lyra** starter — see [Tech Baseline](05_production/tech_baseline.md).

**Game overview (2–3 page GDD):** [Game Design Document](GAME_DESIGN_DOCUMENT.md) — **action sandbox** pitch (strategy + gunplay; **extract** as a run mechanic); unifies **creative premise** ([Concept](arizona_game_concept.md)) with **macro loop** ([Game Loop](01_vision/game_loop.md)) and **session steps / slice** ([Core Session Loop](01_vision/core_extraction_loop.md)), and points to all numbered folders for depth.

## Layout

| Area | Path | Focus |
|------|------|--------|
| Meta & conventions | [00_meta/](00_meta/_index.md) | How we write docs, assistant notes |
| Vision | [01_vision/](01_vision/_index.md) | Premise, pillars, tone (source of truth) |
| Narrative | [02_narrative/](02_narrative/_index.md) | Story, characters, factions |
| World & levels | [03_world_levels/](03_world_levels/_index.md) | Level flow, beats, layout intent |
| Systems | [04_systems/](04_systems/_index.md) | Combat, progression, UI, audio… |
| Production | [05_production/](05_production/_index.md) | Milestones, TODO, decisions, risks |
| Business | `06_business/` | Pitch, investment, budget |
| Reference | `07_reference/` | Research, mood, links |
| Devlog | [08_devlog/](08_devlog/_index.md) | Video series — outlines & scripts |
| Tools | [tools/](tools/README.md) | Python / editor automation |

**Working concept (current):** [Concept](arizona_game_concept.md) at repo root — migrate sections into the numbered folders as they stabilize.

## Working agreement

- One major topic per file where possible.
- Design canon lives under `01_`–`07_`; rolling AI/session notes live in `00_meta/assistant/`.
