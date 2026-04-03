# Multi-timeline resets & world events

**Purpose:** Stack **several cadences** — fast, slow, and ad hoc — so the world **breathes**, **rebalances**, and **surprises** without one system doing all the work. **Intent only** until scoped.

**Reference touchstone:** **Weekly hub/base reset** is **Dune-inspired** — the feeling of **periodic world pressure** and **starting fresh** on the land you claim (franchise DNA; e.g. storms / cycles / *Dune: Awakening*-style rhythms you **liked**). Not a licensed mechanic copy — **capture the fantasy** in Western **session / sandbox** form.

---

## Layer 1 — Weekly (hub / base)

- **What:** **Homestead / neighborhood build state** (and possibly **hub-bound** resources) **resets** on a **fixed weekly** tick.
- **Why:** **Rebuild challenge**, **weekly rebalance** window, **neighborhood ops** (shard count tuning on the boundary — `../04_systems/player_server_cardinality.md`).
- **Wipes:** **Base / plot layout** and **hub-tied** build progress.
- **Persists:** **`Bank vault`** — persistent storage **larger than** your **raid loadout**; contents **survive** the weekly hub wipe. (**Loadout** = what you take **into** the raid; see `../04_systems/vault_and_loadout.md`.)
- **Also persists (unless a slower layer says otherwise):** Account **meta**, **skills**, **blueprints**, **cosmetics** — TBD overlap with **seasonal** (`Layer 2`).

---

## Layer 2 — Seasonal (slower)

- **What:** **Larger** progression / meta reset or rollover — **weeks–months** scale (exact length TBD).
- **Why:** **Ranked** brackets, **economy** passes, **faction** arcs, **battle pass** or **chapter** boundaries, **fairness** for late joiners.
- **Differs from weekly:** Season might **wipe or soft-reset** things the **week** does **not** (e.g. **ladder**, **seasonal currency**, **map pool**), or **only** add **overlays** while hub still wipes weekly.

---

## Layer 3+ — Other timelines & world events

**Examples (mix and match over time):**

- **Narrative chapters** — scripted **beats** (train schedule changes, new POI, faction escalation) that may **not** wipe progress but **reshape** raids.
- **Live / curated world events** — **Double extract risk**, **sandstorm** rule modifiers, **machine surge**, **limited-time quest chains**.
- **Mid-season patches** — balance hotfixes **between** weekly ticks if needed (don’t rely on cadence alone for emergencies).

**World events** can **align** to a **reset boundary** (big splash) or **offset** (mid-week surprise). Calendar **clarity** matters so players don’t feel **stacked** punishments **without warning**.

---

## How layers stack (design rules)

1. **One pillar, one owner per tick** — e.g. don’t **full-wipe stash** on the **same** day as **season** end **unless** that’s **communicated** as **The Big One**.
2. **Player-facing calendar** — show **weekly wipe**, **season** end, and **flagged** events.
3. **Raids** can read **event modifiers** from **any** layer (season rule + weekly weather + one-off **event**).

---

## Open questions

- [ ] **Season length** vs **weekly count** (e.g. 12-week season = 12 hub wipes per season — is that right?).
- [ ] **World events** — % **hand-authored** vs **systemic** (emergent from player actions)?
- [ ] **Lore** for each layer — same diegetic explanation (storm, treaty, timetable) or **UI-only** for some?

---

*Related:* `meta_loop_intent.md` (base + seasons summaries), `../04_systems/player_server_cardinality.md`, `../04_systems/vault_and_loadout.md`, `core_extraction_loop.md`, `../05_production/decisions.md`.
