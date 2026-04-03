# Attachments catalog *(working)*

**Rules:** See `weapons_loot_tiers.md` — **most** attachments are **future**; **few** **simple / period** exceptions marked explicitly. **Mixing:** **attachment tier** and **weapon tier** are **independent** — any legal combo allowed by **compatibility** (e.g. **yellow** mod on **grey** gun OK).

**Columns (fill as you design):**

| Field | Meaning |
|--------|---------|
| **Name** | Player-facing + internal id later |
| **Compatible** | Weapon families / slots (e.g. shotgun, long gun underbarrel) |
| **Buffs** | What improves |
| **Nerfs / tradeoffs** | What worsens or risks (balance + fantasy) |
| **Attachment tier** | Grey → yellow (loot rarity of the **mod** itself) |
| **Era** | **Future** (default) or **Simple** (period exception) |

---

## Seed list *(stats TBD)*

| Name | Compatible | Buffs *(draft)* | Nerfs / tradeoffs *(draft)* | Att. tier | Era |
|------|------------|-----------------|----------------------------|-----------|-----|
| **Sawn-off kit** | Shotgun | *TBD* — CQB / spread / handling | *TBD* — range, precision, pellet pattern | TBD | **Simple** *(kit modifies period weapon; could be future-manufactured part — pick)* |
| **Fore grip** | *TBD* — rifles, LMG-class, etc. | *TBD* — recoil / sway | *TBD* — ADS speed, snag | TBD | **Future** |
| **Collapsible stock** | *TBD* — long guns w/ stock rail | *TBD* — compact / swap stance | *TBD* — stability when extended | TBD | **Future** |
| **Laser** | *TBD* — rail-equipped | *TBD* — hip / point aim | *TBD* — visible to others, battery fantasy | TBD | **Future** |
| **Flashlight** | *TBD* — rail / tube mount | *TBD* — visibility / blind (PvE?) | *TBD* — reveal position | TBD | **Future** *(simple candle-oil lamp could be **Simple** alt)* |

---

## To add

- **Etc.** — new rows here; keep **compat** strict so UI and loot gen stay sane.
- **Slot taxonomy** — underbarrel, rail, stock, muzzle, internal, receiver… *(define once, reuse).*

---

*Related:* `weapons_loot_tiers.md`, `weapon_single_shot_musket.md` *(musket attachment slots TBD)*.
