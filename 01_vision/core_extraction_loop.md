# Core session loop — extraction shooter

**Canonical session flow.** Other vision, systems, slice, and business docs should **stay compatible** with this loop unless we explicitly revise it here.

## Full loop (target experience)

1. **Party** — Choose **solo** or **party** (**duo** or **trio**).
2. **Loadout** — Configure what you bring into the raid (subset of your gear; **bank vault** holds the rest — `../04_systems/vault_and_loadout.md`).
3. **Join server** — Enter a **match / instance** (server model TBD — see `scale_and_unresolved.md`).
4. **Raid pressure** — **Timer** (or equivalent pressure) to **extract or die**. **Lore justification** for why extraction is **mandatory** is **TBD** (must support tension without undermining fantasy — track in narrative when split out).
5. **Mid-raid play** — **Loot** and/or **fight**; **PvPvE always**, **no safe zones** (see `design_goals.md`).
6. **Extract** — Primary v1 exit: **train extraction** (other exits, e.g. **mine**, later).
7. **Round review** — Post-raid summary (rewards, stats, downtime hook into meta — scope TBD).

## Vertical slice alignment

The **nine-strip** playable slice (`../05_production/playable_slice_strip_order.md`) is the **minimum spine** of this loop in-engine—not a disconnected tech demo.

| Loop phase | What the slice must prove |
|------------|---------------------------|
| **Party / join** | **#9** — **two players** in the same instance (duo path stub); solo still valid. Full **matchmaking UI** out of scope for slice. |
| **Loadout** | **#7** — **minimal inventory / equip** (enough to feel “I brought this in”). Deep loadout meta **later**. |
| **Deploy into raid** | **#2** env subset + **#3** menu flow into level. |
| **Pressure + PvPvE + loot + combat** | **#4–#6** — musket, **damage**, **HUD**; loot rules **as simple as needed** to not fake the fantasy. |
| **Extract** | **#8** — **train** moment is the **contract** with the full loop. |
| **Round review** | **Not in slice v1** — document when adding **#10+** or post-slice milestone; don’t let slice avoid **thinking** about what review must show later. |

**Rule of thumb:** If a slice task **doesn’t** connect to a step above, **question whether it belongs** in the slice—or flag it as **tooling** / **devlog** only.

## Related

- Meta between raids: `meta_loop_intent.md`
- **Vault & loadout** (vault survives **weekly** hub wipe): `../04_systems/vault_and_loadout.md`
- **Vendors / crafting / skills:** `../04_systems/vendors.md`, `../04_systems/crafting.md`, `../04_systems/skills.md`
- **Who plays where** (realm vs instance, friends/solo): `../04_systems/player_server_cardinality.md`
- Open numbers (maps, time split, player counts): `scale_and_unresolved.md`
- Combat tone: `design_goals.md`
