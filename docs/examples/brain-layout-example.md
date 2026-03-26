# Brain Layout Example

## Purpose

This document provides a public-safe example of how Addison’s artifact layout is conceptually organized.

It is meant to help readers understand the role of the artifact layer without exposing the live private brain or publishing private runtime contents.

This is an illustrative structure, not a dump of the real internal system.

---

## Why This Example Exists

A large part of Addison’s design depends on artifacts being treated as part of the system’s grounding layer rather than as incidental notes.

That idea is easier to understand when the structure is visible.

At the same time, the real private brain contains materials that should not be exposed directly. A public example therefore needs to show the shape of the system without pretending to be the full live internal artifact set.

This document exists to provide that shape safely.

---

## Example Layout

```text
brain/
├── identity/
│   ├── core_identity.md
│   ├── personality_rules.md
│   └── speaking_style.md
├── shared/
│   ├── system_status.md
│   ├── decisions.md
│   ├── capabilities.md
│   └── project_state.md
├── goals/
│   └── active.md
├── modes/
│   ├── performative/
│   ├── developer/
│   └── reflection/
├── session_logs/
│   └── README.md
└── templates/
    └── README.md
