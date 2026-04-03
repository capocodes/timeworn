# Technical baseline — Unreal **Lyra**

**DECISION:** The **Timeworn** Unreal project is **rebased on** (or **merged with**) Epic's **[Lyra](https://dev.epicgames.com/documentation/en-us/unreal-engine/lyra-sample-game-in-unreal-engine)** starter game as the **technical foundation**.

## Rationale (typical wins)

- **Production-ready patterns** for **multiplayer**, **game features** (modular GAS-style setup), **UI**, **sessions**, and **weapon/character** scaffolding — aligns with **nine-strip** goals (**2P**, **HUD**, **inventory**, **menus**) without inventing plumbing from zero.
- **Upgrade path** with engine versions; sample content to **replace** or **strip** as **Timeworn** identity lands.

## Implications

- **Design docs** stay **gameplay-first**; **implementation** maps into **Lyra's** extension points where possible (**custom experiences**, **weapons**, **modes**).
- **Vertical slice** work may include **Lyra cleanup** (remove sample branding/content) in parallel with **musket**, **enemy**, **train extract** — budget time in **devlogs** if rebasing is visible to viewers.
- **Python / tools** in [Tools](../tools/README.md) should assume **Lyra-style** project layout until documented otherwise (update that README when paths stabilize).

## Progress *(user update)*

- [x] **Learning exercise complete:** Lyra-based **prototype** in place — **prototype level**, **prototype character**, **prototype weapon(s)** with **custom reload animation** (first-pass).
- [ ] **Reload animation** — **cleanup / polish** pass.
- [ ] **Placeholder audio** — reload, fire, foley (supports devlog + feel tests).
- [ ] **Placeholder UI** — minimal HUD prompts where needed for weapon state (even greybox).
- **Note:** Lyra's default look is **distractingly futuristic** but **very polished**. For **devlogs** and **pitch**, plan **visual framing** (lighting, env, shot choice) and **incremental** swap of Lyra chrome for **Western / period** tone until **custom** UI and art land.

## Open (engineering)

- [ ] **Fork model:** Lyra → **Timeworn** rename vs **Timeworn** assets → Lyra shell (document **repo / `.uproject`** name for collaborators).
- [ ] **Which Lyra experiences** ship in slice v1 (e.g. B_Shooter vs custom) — **TBD**.
- [ ] **De-Lyra pass** — when to strip/replace sample branding, menus, and **sci-fi** UI skins (priority vs slice features).

---

*Logged in the [Decision Log](decisions.md) (2026-03-29).*
