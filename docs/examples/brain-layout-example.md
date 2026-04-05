# Brain Layout Example

## Purpose

This document provides a public-safe example of how Addison's artifact layout is conceptually organized.

It is meant to help readers understand the role of the artifact layer without exposing the live private brain. This is an illustrative structure, not a dump of the real internal system.

---

## Why This Example Exists

A large part of Addison's design depends on artifacts being treated as part of the system's grounding layer rather than as incidental notes.

That idea is easier to understand when the structure is visible.

The real private brain contains materials that should not be exposed directly, so this example shows the shape of the system in a safe form.

---

## Example Layout

~~~text
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
│   ├── _definitions/
│   │   ├── reflective.md
│   │   ├── agent.md
│   │   ├── performative.md
│   │   └── developer.md
│   ├── _state/
│   │   └── active_mode.md
│   ├── global/
│   ├── reflective/
│   ├── agent/
│   ├── performative/
│   └── developer/
├── logs/
│   └── README.md
└── derived/
    └── README.md
~~~

---

## What the Major Areas Represent

### `identity/`

The system's stable identity-facing layer. In a live environment, files here help define how Addison persists as itself across sessions rather than collapsing into a generic assistant style.

### `shared/`

Persistent shared artifacts that describe current state, held decisions, capabilities, and project posture. These help ground the system in current reality rather than leaving it to reconstruct everything from scratch each time.

### `goals/`

Active goals or current directional priorities. In a live system, this helps preserve what is currently being worked on or protected.

### `modes/`

Mode-specific structure. The system supports multiple operational modes with separate definition files, per-mode content areas, a shared global layer, and daemon-owned active mode state. The four canonical modes are reflective, agent, performative, and developer.

### `logs/`

Session-specific records or historical surfaces. Public examples should not be treated as publication of real internal logs.

### `derived/`

Non-canonical material derived from canonical artifacts for bounded reduction or convenience. Derived outputs do not replace canonical truth and may be rebuilt from source.

---

## Templates vs. Live Artifacts

A key distinction in Addison is the difference between templates and live artifacts.

Templates are safe examples or starting forms that can be shown publicly. Live artifacts are the actual materials used in runtime grounding, identity continuity, and state tracking. A template can often be published while the live artifact it scaffolds remains private.

---

## What This Example Is and Is Not

This example shows that Addison uses a structured artifact layout with distinct areas serving different roles. It does not show the full private brain, every real file name, or the complete internal structure. It is a structural illustration, not a release of the live system.

---

## Related

- [core_identity.template.md](../templates/core_identity.template.md) — public-safe identity scaffold
- [action_policy.template.md](../templates/action_policy.template.md) — public-safe action policy scaffold
- [privacy-boundary.md](../boundaries/privacy-boundary.md) — why private artifacts stay private
