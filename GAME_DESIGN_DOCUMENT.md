# Game Design Document — Timeworn (overview)

**Status:** living document · **Audience:** team, collaborators, future-you  
**Purpose:** single entry point for **what the game is**, **why it exists**, and **where detail lives** in this repo. Depth stays in `01_`–`07_`; this file answers the standard GDD sections at overview level only.

---

## 1. Elevator pitch

**Timeworn** is a **multiplayer extraction shooter** set in a **grounded 1850s Arizona frontier** where human conflict (Union, Apache, and other tensions) collides with **inexplicable, lethal machine threats**. Raids are **PvPvE**: players, **future-robot PvE**, and environmental pressure share the same contested space. Sessions end in **extraction under pressure** (v1 fantasy: **train departure**) or failure. Between raids, a **meta layer** (vault, eventual base/social, seasons — see vision) carries long-term stakes without diluting the raid fantasy.

---

## 2. High concept & creative north star

From the working concept (`arizona_game_concept.md`): **cinematic Western + slow-reveal sci‑fi intrusion** — mystery-first, high-contrast light, “something is deeply wrong” before full explanation. The **massive mechanical presence** is a **tone and stakes anchor** for marketing and worldbuilding; **in raid**, PvE is expressed first through **readable future robots** (salvage → tech craft) while the **full lore of the mech-scale threat** stays deliberately unresolved in docs until narrative locks it.

**Product shape:** the shipped game experience is **session-based extraction**, not a linear campaign-first title. Cinematic and teaser work **sell the fantasy**; the **loop doc** (`01_vision/core_extraction_loop.md`) is **session truth**.

---

## 3. Genre, platform & reference frame

| Area | Choice |
|------|--------|
| **Genre** | Extraction shooter / session PvPvE survival-leaning combat |
| **Camera / perspective** | FPS (implied by slice: musket, HUD, Lyra baseline) |
| **Engine baseline** | Unreal, **rebased on Epic Lyra** — see `05_production/tech_baseline.md` |
| **Multiplayer** | Party sizes **solo / duo / trio**; slice proves **2P** path |
| **Comparative anchors** | Slow, methodical gunplay; mid engagement default; robot PvE readability (see `01_vision/design_goals.md`, `04_systems/enemies_future_robots.md`) |

---

## 4. Design pillars

1. **Legible extraction pressure** — timer (or equivalent), clear extract fantasy (train v1), stakes on the line every run.  
2. **Deliberate combat** — long TTK band vs twitch; **one strong weapon** in slice (single-shot musket) before expanding arsenal.  
3. **PvPvE integrity** — players + machines + environment; **no safe zones in raid**; human threat is **players/factions**, not “filler bandits.”  
4. **Few systems, each excellent** — slice limits feature count; depth on included systems (gun feel, HUD, extract moment, minimal inventory).  
5. **Grounded frontier + uncanny tech** — historical texture; sci‑fi layered via **loot tiers, attachments, robots**, not lore dumps mid-fight.

---

## 5. Setting, world & fantasy

**Where & when:** Sonoran-adjacent **Arizona frontier**, **circa 1858–1862** — canyons, dust, golden-hour readability, silhouettes.  
**Who:** Faction tension (**Union / Apache / broader frontier politics**) provides **narrative and social texture**; **in-session**, opposition is **other players** and **machines**.  
**Fantasy:** You are **outgunned and out of time** — loot, fight or avoid, **race extraction**, bring something back to the **bank vault**; hub/base layers may reset on cadence while vault persists (see `01_vision/resets_and_world_events.md`, `04_systems/vault_and_loadout.md`).

---

## 6. Player fantasy & roles

- **Raid fantasy:** “I chose what to risk, I survived the map, I extracted (or lost it all).”  
- **Power fantasy curve:** Period weapons baseline; **future tech** escalates via **loot, attachments, crafting** (yellow-tier “fully future” weapons as a deliberate cap — see `04_systems/weapons_loot_tiers.md`).  
- **Role clarity:** Not class-heavy in slice; **loadout + execution** define the run.

---

## 7. Core gameplay loop (session)

Canonical detail: `01_vision/core_extraction_loop.md`.

**Summary:** Party → **loadout** (subset; rest in **vault**) → **join instance** → **raid pressure** (time) → **loot / fight / PvPvE** → **extract** (train v1) → **round review** (post-slice).

Non-negotiables in raid: **PvPvE**, **no fully safe spaces** in contested spaces; **extraction mandatory** for success framing (lore justification for *why* extract is forced: TBD narrative).

---

## 8. Key systems (overview)

| System | Intent | Detail lives in |
|--------|--------|------------------|
| **Combat** | Slow, methodical; mid-range default | `01_vision/design_goals.md`, `04_systems/weapon_single_shot_musket.md` |
| **Damage & feedback** | Clear hits, deaths; slice proves both sides | Slice strips + systems folder |
| **Loot & gear** | Tiers grey→yellow; attachments mostly future | `04_systems/weapons_loot_tiers.md`, `attachments_catalog.md` |
| **Vault & loadout** | Vault survives weekly hub wipe; loadout = raid carry | `04_systems/vault_and_loadout.md` |
| **PvE enemies** | Future robots; fast reposition, slow lethal telegraphs | `04_systems/enemies_future_robots.md` |
| **Crafting / vendors / skills** | Post-slice economy depth | `04_systems/crafting.md`, `vendors.md`, `skills.md` |
| **Base building** | Intent only; weekly reset fantasy | `04_systems/base_building.md`, `01_vision/meta_loop_intent.md` |
| **UI** | Minimal, legible HUD; intentional not debug | Slice strip #6, production notes |

---

## 9. Progression & meta (between raids)

**Intent** (not full slice v1): quests (co-op vs solo), **PvE-only base/social** as possible exception to raid rules, seasons, faction fantasy — see `01_vision/meta_loop_intent.md`. **Scale and server model** remain explicit TBDs: `01_vision/scale_and_unresolved.md`, `04_systems/player_server_cardinality.md`.

---

## 10. Narrative & tone

- **Tone:** Mystery, restraint, show-don’t-tell; cinematic reference for **trailer and mood** in `arizona_game_concept.md`.  
- **Story delivery in product:** Environmental, optional, and **compatible with repeatable raids** — full campaign scope is not the slice contract.  
- **Open lore:** Origin of the largest mechanical threat; mandatory extraction **why** — tracked as narrative/production questions, not guessed here.

---

## 11. World & levels (overview)

**World structure:** Raid spaces = **contested pocket environments**; slice uses a **small authored pocket** with readable sightlines for musket play (`05_production/playable_slice_strip_order.md`). **Act / level list** and beats per level: stub under `03_world_levels/_index.md` — to expand as levels are named.

---

## 12. Presentation

- **Visual identity:** Realistic base, **Timeworn** (aged, worn) read, strong light/shadow; high contrast, desert readability — see `arizona_game_concept.md` § Visual Identity.  
- **Audio / VFX:** Sell weight on slice weapons (musket) before library explosion.  
- **Branding note:** Game title **Timeworn**; platform store / legal final naming TBD if needed.

---

## 13. Scope — vertical slice & engineering

**Slice spine:** nine strips from player movement through **2P**, ordered in `05_production/playable_slice_strip_order.md` — **full loop playable in rough form** before feature creep.  
**Anti-pattern:** Second gun, full roster, deep meta UI before the loop ships.

---

## 14. Risks, dependencies & open questions

- **Lore vs mode:** Marketing “shared awe at the mech” must stay **compatible** with **repeatable extraction** and PvPvE rules.  
- **Scale:** Player counts, map size, instance vs realm — decide in `scale_and_unresolved.md`.  
- **Anti-grief:** Intent in `design_goals.md`; mechanics TBD.  
- **Extract variants:** Train v1; other exits later.  
- **Round review:** Not slice v1; design before post-slice milestone.

---

## 15. Documentation map (where to go next)

| Need | Path |
|------|------|
| Session truth & slice alignment | `01_vision/core_extraction_loop.md`, `05_production/playable_slice_strip_order.md` |
| Goals & PvPvE rules | `01_vision/design_goals.md` |
| Meta & resets | `01_vision/meta_loop_intent.md`, `resets_and_world_events.md` |
| Creative premise & trailer | `arizona_game_concept.md` |
| Systems depth | `04_systems/_index.md` |
| Production & tech | `05_production/tech_baseline.md`, `decisions.md` |
| Repo layout | `README.md` |

---

*This overview is the **scope contract** at a glance. When vision and concept diverge, **update this file first**, then align `core_extraction_loop.md` and `arizona_game_concept.md` so pitch, session truth, and folders stay one story.*
