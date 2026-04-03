# Weapon — single-shot musket (slice v1 focus)

## Role in the slice

- **Strip #4** in the [Playable Slice — Strip Order](../05_production/playable_slice_strip_order.md): the **first** ranged weapon wired end-to-end for the playable vertical slice.
- Supports **mid-first** engagement goals in [Design Goals](../01_vision/design_goals.md) — one gun that can **read** at multiple distances in a small env pocket (exact falloff / accuracy TBD).
- **Long-term arc:** **period** firearm vs **futuristic** weapons unlocked via **robot salvage** ([Enemies — Future Robots](enemies_future_robots.md) + [Crafting](crafting.md)).

## Identity

- **Single-shot** long gun (musket-class): **one round per shot**, then **reload / rechamber** loop — pacing leans into **slow, methodical** combat direction.
- Period-appropriate for the **frontier / 1860s-adjacent** fantasy (see [Concept](../arizona_game_concept.md)); implementation detail (cap vs paper cartridge, etc.) can stay abstract until art/narrative lock.
- **Loot tier:** Expect **grey–green** band for a **starter** musket; **yellow** = **fully future** weapon only ([Weapons & Loot Tiers](weapons_loot_tiers.md)). **Attachments** on top can still be **future** mods ([Attachments Catalog](attachments_catalog.md)).

## Reference (inspiration)

- **Feel / fantasy anchor:** **Ferro** (*Arc Raiders*) — not a 1:1 copy; use as **touchstone** for **handling fantasy**, **reload weight**, and **player fantasy** of a **deliberate** long gun. Replace with internal codename in outward-facing copy if needed.

## Quality bar (slice)

- Match project stance in [Design Goals](../01_vision/design_goals.md): **one gun, done properly** — animation timing, audio, hit feedback, and reload **read as intentional**, not temp silence + cube arms.

## Reload — cancel rules *(locked)*

- **Sprint** cancels reload.
- **Weapon switch** cancels reload.
- **Progress on cancel:** TBD whether chamber/sequence **resets fully** or **partial progress** is kept when returning to the musket — pick when implementing (full reset is simpler and reads clearly).

## Open design questions

- **Sights:** irons only for slice vs minimal ADS — choose what sells **mid** best.
- **Damage / drop-off:** tuned for **mid** as default band; headshot / limb multipliers later.
- **Audio / VFX:** **in scope** for selling **weight** on this weapon; scope to **one** musket, not a library of FX.

*Update this file when tuning numbers or when slice weapon changes.*
