# Game loop — Timeworn (macro structure)

**Purpose:** Canonical **macro** loop for the **action sandbox**: stash ↔ raid, **three progression tiers**, **train / final extract** as **stakes mechanics** (not the whole game identity), and the **craft → town → build → defenses → Exodus** spine—**building** outputs **defenses** (RTS-style “construction matters”), not troop queues; **Exodus** is the **endgame craftable**. Text equivalent of the **Game Loop** flowchart (team artifact). Session step-by-step detail and vertical-slice mapping stay in **`core_extraction_loop.md`**.

**Diagram (optional):** If you add the exported PNG to the repo, place it at `07_reference/diagrams/timeworn_game_loop.png` and link it from here for artists and new readers.

---

## Outer loop: stash, social, and loadout

- **Stash & social** — Off-raid state: inventory persistence, social hooks, preparation. (Full meta: `meta_loop_intent.md`, vault: `../04_systems/vault_and_loadout.md`.)
- **Choose loadout** — What you risk on the run; enters the raid at **spawn**.
- **Return** — Successful extraction: **keep what you extracted** (and loadout rules) back into stash/social. Failed runs use the same product rules as today (TBD tuning in systems/production).

---

## Three tiers (two axes)

Progression and content are organized in **three horizontal tiers**. They align on two parallel axes:

| Axis | Tier 1 (top / early) | Tier 2 (mid) | Tier 3 (bottom / end) |
|------|----------------------|--------------|------------------------|
| **Player goal** | **Survive** | **Build** | **Extract** (session climax) |
| **Loot & resources** | **Low** | **Medium** | **High** |

Higher tiers assume you have unlocked capabilities and gear from lower tiers; exact gating is systems/production detail.

---

## Extraction trains (per tier)

Each tier has a corresponding **extract train** moment (escalating stakes / difficulty):

1. **Extract Train 1** — Early / low tier; first reliable “get out” read for the session.
2. **Extract Train 2** — Mid / medium tier.
3. **Extract Train 3** — Late / high tier.

**Final extract** — After **Exodus** (end-tier objective), the run resolves through a **final extraction** beat (product framing: “close the loop” for that session arc). Train remains the v1 fantasy for extract moments unless we branch variants later (`core_extraction_loop.md`).

---

## Tier 1 — Survive / low tier

- **Entry:** **Spawn** into the raid space.
- **Threats:** **Easy** PvE bots; **environment** (e.g. **storms**) as readable pressure.
- **Core micro-loop:** **Loot** ↔ **Survive** ↔ **Unlock** ↔ **Craft** (repeat as needed).
- **Key facilities (outputs of craft / progression):**
  - **Workbench**
  - **Blacksmith**
  - **Town claim** — Stakes ground for moving into mid-tier **town** play.
- **Unlocks into tier 2:**
  - **Unlock** path feeds **tech buildings** (tier 2).
  - **Town claim** feeds **town** (tier 2).

---

## Tier 2 — Build / medium tier

- **Threats:** **Medium** PvE bots (escalation from easy).
- **Spine:** **Town** → **Build** → **Tech buildings** → **Defenses**.
- **Extraction:** **Extract Train 2** is the mid-tier exit option.
- **Unlock into tier 3:** **Defenses** (when satisfied per design) **unlock Exodus** — the end-tier arc.

---

## Tier 3 — Extract / high tier

- **Threats:** **Hard** PvE bots (escalation from medium).
- **Spine:** **Exodus** → **final extract** (climax of the session macro-loop for this structure).
- **Extraction:** **Extract Train 3** supports high-tier staging toward that finale.

---

## PvPvE and slice alignment

- **Raid spaces** remain **PvPvE** and **no fully safe zones** in-contested areas (`design_goals.md`). Stash/social is out-of-raid.
- The **vertical slice** proves the **end-to-end session spine** at **tier-1 / survive** fidelity first (train extract v1, musket, minimal inventory, 2P) — see `../05_production/playable_slice_strip_order.md` and the mapping table in `core_extraction_loop.md`. Later strips or milestones layer **town, build, defenses, Exodus** without redefining the slice contract until production revises it explicitly.

---

## Related docs

- Session steps + nine-strip table: **`core_extraction_loop.md`**
- Meta between raids: **`meta_loop_intent.md`**
- Crafting / base: **`../04_systems/crafting.md`**, **`../04_systems/base_building.md`**
- Loot tiers: **`../04_systems/weapons_loot_tiers.md`**
- Robots: **`../04_systems/enemies_future_robots.md`**
- Overview GDD: **`../GAME_DESIGN_DOCUMENT.md`**
