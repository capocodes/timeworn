# Observations & working memory

*Dated notes from working sessions. Promote anything final into the numbered design folders.*

---

## 2025-03-24 — Scaffold

- Repo structure seeded; `arizona_game_concept.md` remains at root until we split/migrate by section.

## 2025-03-24 — Priority sync (4-week win)

- **User intent:** (1) **2** new devlogs, each aiming for **~100 views**; (2) **10** “interested” people on a spectrum from casual following → willing to collaborate for free; Steam wishlist nice-to-have, smaller proof OK.
- **Direction:** Views = lagging; lock **2 ship dates** and a **single funnel** for counting interest. Clarify whether this month is **collect leads only** vs **onboarding collaborators**.
- **Canon:** `05_production/milestone_next_4_weeks.md`

## 2025-03-24 — Funnel

- **Primary funnel:** **Google Form**; graduate to something richer later.
- **Counting:** one submission = one interested person; dedupe duplicates.
- **This month:** **collect-first** (no mandatory collaborator onboarding) — recorded in milestone file.

## 2025-03-24 — Form live

- **Public form:** “Timeworn Community Interest Form” — `https://docs.google.com/forms/d/e/1FAIpQLScAIMBnubumIOWQhU-J33KBrn9FmCZeTe87-0_OIu0NZ6YRyg/viewform`
- Captures involvement + funding/publisher interest per shipped questionnaire.

## 2025-03-24 — CTA

- **Done:** form linked from devlog description + end card; terse **pinned-comment** CTA pattern in use.

## 2026-03-24 — Publish cadence

- **Sunday** releases; **weekend** as crunch window.
- **Next two ships (locked in milestone):** **2026-03-29**, **2026-04-05** — assumes **weekly** Sundays; user may correct to **fortnightly** (second → **2026-04-12**).

## 2026-03-24 — Devlog topics

- **2026-03-29:** Example **character**, **movement**, and **weapon** animations (in-engine). Script: `08_devlog/episodes/ep_2026-03-29_character_movement_weapons.md`.
- **2026-04-05:** **Provisional** — **first enemy** encounter; aligns with **vertical slice** = **few systems, high quality per system** (not shallow placeholders across many features). Script: `08_devlog/episodes/ep_2026-04-05_enemy_system_first_enemy.md`.

## 2026-03-24 — Slice strip order

- **Order (9 strips):** player → env → **basic menu** → one gun → damage → **HUD** → inventory → extraction (train) → **2P** multiplayer. **Canon:** `05_production/playable_slice_strip_order.md`.

## 2026-03-25 — Extraction loop + meta

- **Session loop** (party/loadout/join → timer → PvPvE/loot/build → train extract → round review): `01_vision/core_extraction_loop.md` + slice alignment table. **Pitch:** action sandbox (`GAME_DESIGN_DOCUMENT.md`), not extraction-shooter-as-genre.
- **Meta intent:** co-op vs solo quests, **PvE-only base/social** with loot sink, seasons, horses?, factions Apache / Cowboys / machines (**name TBD**).
- **Unresolved scale:** map size, base vs raid time %, server/player cardinality — `01_vision/scale_and_unresolved.md`.

## 2026-03-25 — Vendors / crafting / skills

- Split to `04_systems/vendors.md`, `crafting.md`, `skills.md`. **Player↔server / friends vs solo:** `04_systems/player_server_cardinality.md` (realm-bound char + instanced raids as default recommendation).
- **Local base host** considered: doc section on hybrid (authoritative raids/loadout vs local/P2P social), host-online + shared-base + anti-dupe risks.
- **Neighborhood shards:** ~100 hubs × ~100 cap, social local to hub, **raids cross-pool**; sunset problem → **portable base** / migration / drain-merge options in `player_server_cardinality.md`.
- **Weekly hub reset** considered: rebalance boundary + **rebuild loop**; persistence split TBD; noted in `meta_loop_intent.md` + cardinality doc.
- **Multi-timeline:** `01_vision/resets_and_world_events.md` — weekly (Dune-inspired) + seasonal + world events + stack rules.
- **Vault vs loadout:** weekly wipe **base** only; **bank vault** persists (`04_systems/vault_and_loadout.md`).
- **Enemies:** PvE = **future robots**; humanoids de-emphasized for tension; salvage feeds **futuristic** craft — `04_systems/enemies_future_robots.md`.
- **Weapons:** grey→green→blue→pink→**yellow**; **yellow** only **fully future** gun; **1850–70** pool baseline; **attachments** catalog seeded — `weapons_loot_tiers.md`, `attachments_catalog.md`.
- **Attachments:** **cross-tier** mixing allowed (compat rules only). **Base building** stub — *Dune* / *Awakening* inspiration — `base_building.md`.

## 2026-03-29 — Tech baseline

- **Unreal:** **Timeworn** **rebased on Lyra** (Epic starter). **Canon:** `05_production/tech_baseline.md`, `decisions.md`.

## 2026-03-29 — Lyra prototype milestone

- **Done:** prototype **level**, **character**, **weapon(s)** + **custom reload** anim (rough). **Learning exercise** complete.
- **Next:** polish **reload**, **placeholder sounds**, **placeholder UI**. Lyra default = **futuristic but polished** — manage **framing** for devlogs until art/UI diverges from sample.

## 2026-03-24 — Engagement + first gun

- **Slice engagement default:** **Mid** (show a useful range in first build).
- **First gun to flesh out:** **single-shot musket**, handling inspiration **Ferro** (*Arc Raiders*). **Canon:** `01_vision/design_goals.md`, `04_systems/weapon_single_shot_musket.md`.
