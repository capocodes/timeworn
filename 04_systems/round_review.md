# Round review (post-raid) *(stub)*

**Purpose:** The screen players see **after a raid ends** — whether they extracted, died, or the session timed out. Summarizes what happened and bridges back to the stash & social loop.

## Intent

- **Loot summary:** What you extracted (or lost). Drives the "was that run worth it?" feeling.
- **Stats snapshot:** Kills, damage dealt, resources gathered, buildings placed, extraction tier reached — pushed to [Stats Service](services.md).
- **XP / progression:** If any session-level progression exists (skills, season pass), this is where it's awarded.
- **Vault transfer:** Extracted loot is committed to [Vault](vault_and_loadout.md) via [Stash Service Client](stash_service_client.md). Player sees the "stash deposit" confirmation.
- **Return flow:** After review, player returns to stash & social ([Session Flow](session_flow.md) lobby) to prep the next run.

## Slice v1

- Minimal version: a results screen showing extracted loot list, kills, and a "return to menu" button. Strip **#11** or later ([Playable Slice](../05_production/playable_slice_strip_order.md)) — post-MVP but needed for the full loop feel.

## Open

- [ ] Show teammate results (duo/trio) or individual only?
- [ ] Replay / killcam integration (TBD).
- [ ] Failure screen vs success screen (different tone / layout).
- [ ] Time spent on round review before auto-return.
- [ ] Social hooks (share result, invite to next raid).

---

*Related:* [Gameplay Manager](gameplay_manager.md), [Vault & Loadout](vault_and_loadout.md), [Stash Service Client](stash_service_client.md), [Stats — Services](services.md), [Session Flow](session_flow.md).
