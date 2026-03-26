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
│   ├── performative/
│   ├── developer/
│   └── reflection/
├── session_logs/
│   └── README.md
└── templates/
    └── README.md
~~~

---

## What the Major Areas Represent

### `identity/`

This area represents the system’s stable identity-facing layer.

In a live private environment, files here help define how Addison is meant to persist as itself across sessions rather than collapsing into a generic assistant style.

A public example can show that this layer exists structurally without exposing private authored identity material.

### `shared/`

This area represents persistent shared artifacts that describe current state, held decisions, capabilities, and project posture.

These files matter because they help ground the system in current project reality rather than leaving it to reconstruct everything from scratch each time.

In public examples, these files should be understood as artifact classes, not as publication of live private state.

### `goals/`

This area represents active goals or current directional priorities.

In a live system, this helps preserve what is currently being worked on or protected.

A public example can safely show that a goals surface exists without exposing private or in-progress operating context.

### `modes/`

This area represents mode-specific behavior or context boundaries.

The exact implementation may change over time, but the high-level idea is that different working modes can be separated so the system does not treat all contexts as interchangeable.

A public example only needs to show the existence of this concept.

### `session_logs/`

This area represents session-specific records or carry-forward surfaces.

Depending on the system’s maturity, these may function as restart aids, historical notes, or bounded memory records.

Public examples should not be treated as publication of real internal logs.

### `templates/`

This area represents reusable scaffolds, placeholders, or example artifact forms.

Templates are especially useful for public explanation because they can show intended structure without exposing live private contents.

---

## What This Example Is Showing

This example is showing three things:

- Addison uses a structured artifact layout rather than a single flat context dump
- different artifact classes serve different roles
- the artifact layer is part of how the system is grounded over time

The point is not that every directory name or file name is fixed forever.

The point is that the system relies on organized artifact surfaces with distinct purposes.

---

## What This Example Is Not Showing

This example is not:

- the full private brain
- a runnable release of private internal artifacts
- a guarantee that every live file has the same name or placement
- a complete disclosure of internal cognition structure
- a promise that all private artifact classes will be published publicly

It is a structural illustration meant to help external readers understand the model.

---

## Templates vs. Live Artifacts

A key distinction in Addison is the difference between templates and live artifacts.

Templates are safe examples or starting forms.

Live artifacts are the actual materials used in runtime grounding, identity continuity, state tracking, and ongoing development.

That distinction matters because a template can often be shown publicly, while a live artifact may remain private even when its structural role is described openly.

---

## Why Public Examples Need Simplification

A public example should be understandable on first read.

The real private system may include more detail, more constraints, more supporting files, or additional subdivision that would not improve public clarity.

For that reason, this example is intentionally simplified.

It is better for a public structure example to be clear and truthful than exhaustive and misleading.

---

## Relation to the Privacy Boundary

This example exists under the repository’s privacy boundary.

It helps explain how the artifact model works without exposing private authored content, live session data, or operator-linked internal surfaces.

That is the intended balance:

- enough structure to be legible
- not so much exposure that the public repo becomes a leak of the private brain

---

## Practical Summary

This document shows the shape of a brain-style artifact layout in public-safe form.

The example is meant to help readers understand that Addison depends on organized artifact surfaces for identity, state, goals, mode separation, and continuity.

It is a structural explanation, not a release of the live private system.
