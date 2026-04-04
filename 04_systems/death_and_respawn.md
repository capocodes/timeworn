# Death & respawn *(stub)*

**Purpose:** What happens when a player or enemy **reaches 0 HP** — loot consequences, respawn rules, and how death creates or resolves tension.

## Player death

- **Loot on death:** What stays on the body vs what's lost — TBD. This is the core risk/reward lever. Options:
  - Full drop (hardcore — everything is lootable by others).
  - Partial drop (insured slots survive, rest drops).
  - Tiered (death penalty scales with loot tier carried).
- **Respawn:** In the current raid or not? Options:
  - **No respawn** (single life per raid — high stakes, extraction shooter style).
  - **Limited respawns** (lives tied to a resource or team).
  - **Rally respawn** (teammate-gated, costs time/resources).
- **Downed state:** Optional DBNO (down-but-not-out) phase where a teammate can revive — TBD.
- **Spectate / exit:** Post-death flow before returning to [Stash & Social](session_flow.md).

## Enemy death

- Triggers [Loot & Gathering](loot_and_gathering.md) drop tables.
- Feeds [Stats](services.md) (enemies killed counter).
- Enemy corpse persistence and visibility — TBD.

## Open

- [ ] Player respawn model (no respawn, limited lives, rally).
- [ ] DBNO / revive mechanic.
- [ ] Death penalty severity (full drop vs partial vs tiered).
- [ ] Death camera / killcam (if any — balance info exposure in PvP).
- [ ] Duo/trio team-wipe handling (instant fail, grace period, last-stand).
- [ ] How death interacts with [Extraction](extraction.md) (missed train = death? or separate fail state?).

---

*Related:* [Health & Damage](health_and_damage.md), [Loot & Gathering](loot_and_gathering.md), [Extraction](extraction.md), [Session Flow](session_flow.md), [Spawning](spawning.md).
