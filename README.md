# Timeworn — Design & Production Hub

Design docs, production tracking, devlog scripts, and tooling for **Timeworn**. Game source and Unreal assets live in the separate Unreal project **Timeworn** (not this folder). **Engine baseline:** project is **rebased on Epic’s Lyra** starter — see `05_production/tech_baseline.md`.

**Game overview (2–3 page GDD):** `GAME_DESIGN_DOCUMENT.md` — **action sandbox** pitch (strategy + gunplay; **extract** as a run mechanic); unifies **creative premise** (`arizona_game_concept.md`) with **macro loop** (`01_vision/game_loop.md`) and **session steps / slice** (`01_vision/core_extraction_loop.md`), and points to all numbered folders for depth.

## Layout

| Area | Path | Focus |
|------|------|--------|
| Meta & conventions | `00_meta/` | How we write docs, assistant notes |
| Vision | `01_vision/` | Premise, pillars, tone (source of truth) |
| Narrative | `02_narrative/` | Story, characters, factions |
| World & levels | `03_world_levels/` | Level flow, beats, layout intent |
| Systems | `04_systems/` | Combat, progression, UI, audio… |
| Production | `05_production/` | Milestones, TODO, decisions, risks |
| Business | `06_business/` | Pitch, investment, budget |
| Reference | `07_reference/` | Research, mood, links |
| Devlog | `08_devlog/` | Video series — outlines & scripts |
| Tools | `tools/` | Python / editor automation |

**Working concept (current):** `arizona_game_concept.md` at repo root — migrate sections into the numbered folders as they stabilize.

## Working agreement

- One major topic per file where possible.
- Design canon lives under `01_`–`07_`; rolling AI/session notes live in `00_meta/assistant/`.
