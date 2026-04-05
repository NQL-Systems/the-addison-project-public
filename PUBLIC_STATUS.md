# PUBLIC_STATUS

**Status:** Current public status surface
**Authority:** Public-facing status summary

---

## 1. Purpose

This document exists to keep the public Addison surface honest.

It records what this repository currently supports as a public claim, what remains deferred, and where the boundary is between public explanation and private development reality.

If this file conflicts with higher-authority public materials in the repo, this file is stale and should be corrected.

---

## 2. What The Public Surface Currently Supports

The current public repo supports these bounded claims.

### Architectural shape is real and deliberate

The daemon-authoritative core, artifact-backed memory posture, deterministic context construction, and stateless inference model are not being presented as vague future direction. They describe the actual system shape as it exists today.

See [ARCHITECTURE.md](ARCHITECTURE.md).

### The system supports mode-aware operation

The daemon owns mode state for multiple operational modes. Mode truth flows through deterministic context assembly — the context builder selects mode-relevant artifacts, loads mode-specific behavioral guidance, and shapes the prepared context before inference. Downstream runtimes consume daemon-confirmed mode state without owning it. Mode switching is explicit, operator-initiated, and daemon-confirmed.

### The system includes governed action boundaries

Meaningful system action is subject to a governed proposal lifecycle. The system includes a tool-eligibility framework that gates which governed actions are available under which modes, explicit operator-approval requirements before governed actions execute, and bounded governed memory movement for operator-directed artifact promotion and demotion. Ordinary conversation and runtime presentation remain ungated.

### The system supports daemon-backed voice synthesis

Voice is optional and additive — the system is fully functional without it. When enabled, the daemon owns synthesis with a primary/fallback provider posture and truthful degraded handling when providers are unavailable. Runtimes receive audio downstream without knowing or caring which provider generated it.

### The system supports multiple operator surfaces

Multiple operator runtimes connect to the daemon, including a primary CLI, a retained broader cockpit, and an optional desktop presentation surface. All remain downstream from daemon-owned truth. None are authoritative over system state.

### The project is grounded in bounded public proof, not only description

This public mirror is intentionally narrow, but it is not meant to be pure narrative. The repo's proof posture exists to keep the public explanation tied to observed system behavior rather than floating free as architecture language alone.

### The system is experimental

Addison is a real system under active development, but this public repository does not present it as complete, production-ready, or fully exposed.

---

## 3. What This Public Repo Explicitly Does Not Claim

This repository does not currently claim:

- full source or implementation exposure
- production readiness
- autonomous planning loops
- hidden routing or hidden authority behavior
- model-owned memory
- broad publication of live private artifact trees
- exhaustive exposure of internal governance or runtime detail
- integrated speech/motion choreography or lipsync
- that everything true in the private workspace is already visible here

If a capability is not clearly shown or bounded in this public surface, it should not be assumed by implication.

---

## 4. What Remains Deferred

The public repository remains intentionally partial.

Deferred here does not mean nonexistent. It means not currently claimed as part of the bounded public surface.

Areas that remain deferred from public claim include but are not limited to:

- full source publication
- broader desktop shell maturity claims beyond active-but-limited
- integrated speech/motion choreography, lipsync, and viseme behavior
- autonomous planning loops
- automation eligibility gating
- durable mode-memory population
- exhaustive internal governance exposure
- archive browsing, search, or transcript replay
- broader cross-platform runtime hardening

These may be real in the private workspace at various stages of development. They are not currently part of the bounded public surface.

---

## 5. Maintenance Rule

This is a living public status surface.

As the project develops, public proof may expand, deferred areas may move, and wording may need tightening. Changes to this file should stay explicit, bounded, and honest about what is real versus what is merely private, deferred, or still under development.
