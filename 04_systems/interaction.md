# Interaction system *(stub)*

**Purpose:** Generic **player ↔ world** interaction framework — the "press E" layer. Handles prompts, context actions, and channels interactions to the right system.

## Intent

- **Unified prompt:** Single interaction key; context determines action (loot, open, build, craft, mine, board train, talk to NPC).
- **Consumers:** [Loot & Gathering](loot_and_gathering.md) (pickup + mining), [Building](building.md), [Crafting](crafting.md), [Extraction](extraction.md) (boarding), [Vendors](vendors.md), doors/switches/world objects.
- **Priority:** When multiple interactables overlap, closest / most relevant wins (rules TBD).
- **Replication:** Interactions that change world state must replicate via [Multiplayer](multiplayer.md).

## Open

- [ ] Hold vs tap (per interaction type or global).
- [ ] Interaction range / cone.
- [ ] Cancel rules (damage interrupts, movement interrupts).
- [ ] UI prompt style (world-space widget, screen-space, minimal).
