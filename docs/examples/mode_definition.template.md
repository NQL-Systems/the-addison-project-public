# Mode Definition Template

This file is a public-safe scaffold. It is not a live mode definition.

## Purpose

Mode definition files provide current-turn behavioral guidance to the system. During context assembly, the active mode's definition file is loaded into a dedicated instruction layer so that inference receives mode-appropriate behavioral posture alongside the system's identity, shared state, and mode-local content.

Each canonical mode has one definition file at `brain/modes/_definitions/<mode_name>.md`.

## How To Use

1. Copy this file to `brain/modes/_definitions/<mode_name>.md` on the local machine.
2. Replace every placeholder with mode-specific behavioral guidance.
3. Keep the guidance focused on posture, tone, priorities, and boundaries for the mode — not on general identity or system rules that belong in shared surfaces.
4. The live definition file is loaded by the context builder at build time. It does not need to be referenced manually.

## Suggested Sections

### Mode Identity

- `[State what this mode is and what posture it represents.]`
- `[State how this mode relates to the system's continuous identity.]`

### Behavioral Posture

- `[Describe the expected tone, communication style, and interaction posture for this mode.]`
- `[Describe what this mode prioritizes in its responses.]`

### Boundaries

- `[State what this mode should not do or claim.]`
- `[State any specific constraints that differ from the system's default shared rules.]`

### Relationship To Other Modes

- `[Briefly describe how this mode differs from other canonical modes.]`
- `[State that mode switching does not change identity — it adjusts posture within one continuous identity.]`

## What This Template Does Not Cover

This template shows the structural shape of a mode definition. It does not expose the actual behavioral content of any canonical mode.

The four canonical modes are reflective, agent, performative, and developer. Each has authored guidance appropriate to its role. That guidance remains private.

## Related

- [brain-layout-example.md](../examples/brain-layout-example.md) — structural overview showing where mode definitions live
- [ARCHITECTURE.md](../../ARCHITECTURE.md) — public architecture overview
- [PUBLIC_STATUS.md](../../PUBLIC_STATUS.md) — current public claims including mode-aware operation
