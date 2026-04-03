# Playable slice — strip order (vertical slice)

**Intent:** **Limit breadth** (fixed strips below) so scope stays under control — but **each strip is implemented with a high quality bar**: clear, juicy, and **fleshed out enough to feel “real”** for that pillar. **Not** “placeholder everything until the loop ships,” and **not** endless new systems before the loop closes.

**Implementation baseline:** Unreal work targets the **Lyra**-based **Timeworn** project (`tech_baseline.md`) — use Lyra’s **multiplayer / UI / weapon** scaffolding where it accelerates the strips; **replace** sample content with **Timeworn** identity over time.

**Core loop:** This slice is the **in-engine spine** of the **extraction session loop** in `../01_vision/core_extraction_loop.md`, scoped first to **tier 1 (survive / low loot)** in the **macro loop** (`../01_vision/game_loop.md`). Every strip should **trace** to stash/loadout → party/join → raid → **train extract** (**Extract Train 1** in target tier language) and stay forward-compatible with **round review** and later tiers (**town, build, defenses, Exodus**). **Meta** (base, quests, seasons, **vendors/crafting/skills**) lives under `../01_vision/meta_loop_intent.md` plus `../04_systems/vendors.md`, `../04_systems/crafting.md`, `../04_systems/skills.md` — **out of slice v1** except where it informs **tone or UI copy**. **Realm vs raid instance** (friends/solo): `../04_systems/player_server_cardinality.md`.

**Guardrail:** **No feature creep inside a strip** before the **end-to-end loop** is playable (e.g. don’t add gun #2, full enemy roster, or advanced settings until the nine-strip spine is shippable in rough form).

**Order (locked until you revise explicitly):**

| # | Strip | Scope & quality bar (working) |
|---|--------|-------------------------------|
| 1 | **Player** | Controllable character; locomotion and camera **feel good** for the slice. *(Overlaps Mar 29 devlog: movement / weapon anims.)* |
| 2 | **Level / env subset** | **Small** authored pocket — **readable** sightlines/cover for **mid** musket play, not a full chapter. |
| 3 | **Very basic menu** | **Session flow:** main menu (start / quit) → load slice; pause if needed. **Clean and reliable**, not a settings maze. |
| 4 | **Single shootable gun** | **One** weapon wired end-to-end with **strong handling** (input → fire → feedback). **Slice v1:** **single-shot musket** — `../04_systems/weapon_single_shot_musket.md` (*Arc Raiders* **Ferro** as feel reference). |
| 5 | **Damage (player + enemy)** | Rules **clear** and **satisfying** on both sides (hit feedback, death/fail) — **not** full combat design space, but **not** invisible damage either. |
| 6 | **HUD** | **Minimal elements**, **high legibility** — health, ammo/weapon state, prompts as needed. Feels **intentional**, not debug UI. |
| 7 | **Super simple inventory** | **Smallest** viable carry/equip/ammo loop — **tight UX**, no RPG sprawl. |
| 8 | **Extraction (train leaves)** | Exit condition **sold as a moment** (timing, feedback, clarity) within slice constraints. |
| 9 | **Multiplayer (2 players)** | **Two** players **stable** and understandable — topology TBD; favor **works well** over extra MP features. |

**Rationale (menu + HUD placement):** **Menu** after **env** so “start” has somewhere to load; **HUD** after **gun + damage** so HUD elements **mean something** in play.

## Devlog mapping (informal)

- **2026-03-29** — mostly **#1** + weapon animation pipeline feeding **#4** musket feel.
- **2026-04-05** — **enemy** + **#5** (enemy-side damage); frame as **quality** threat encounter, not “grey capsule = done.”

## Delivery risks

- **Multiplayer last** is still **high blast radius** in Unreal. If needed: **SP loop complete first**, then MP as **9b**; or stub replication early if it affects movement/weapons.
- **Extraction + MP** — synced win condition / authority plan early if train timing matters in 2P.
- **Per-strip polish** can **slide dates** if unmanaged — keep **Sunday** targets but **cut optional beats** inside a video before you cut **core feel** of a strip.

*Revise this file when strip order or definitions change; note date in `decisions.md` if direction shifts.*
