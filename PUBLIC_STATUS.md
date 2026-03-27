# PUBLIC_STATUS

**Status:** Current public status surface
**Authority:** Public-facing status summary

---

## 1. Purpose

This document exists to keep the public Addison surface honest.

It records what this repository currently proves, what remains deferred, and where the boundary is between public claims and private development reality.

If this file conflicts with the architecture documentation or higher-authority public materials, this file is stale and should be corrected.

---

## 2. What Is Currently Proven

The public surface currently supports these claims:

**Architectural shape is real and deliberate.** The daemon-authoritative core, artifact-backed memory, deterministic context construction, and stateless inference model are not aspirational descriptions. They reflect the system as built. See [ARCHITECTURE.md](ARCHITECTURE.md) for the full technical overview.

**Artifact-gated startup has been observed.** The system's runtime path depends on the artifact layer being present, and once startup completes, the system answers from locally grounded artifacts rather than falling back to generic model behavior. See [Artifact-Gated Startup](artifact-gated-startup.md) for the proof writeup.

**The system is experimental.** Addison is a real system under active development, but it is not complete or production-ready. This repository does not present it as either.

---

## 3. What Is Explicitly Deferred

The public repository does not currently claim:

- full source or implementation exposure
- production readiness
- autonomous planning loops
- hidden routing or hidden authority behavior
- model-owned memory
- broad public release of live private artifact trees
- exhaustive publication of internal governance or runtime details

If a capability is not clearly shown or documented here, it should not be assumed from wording, reputation, or implication.

---

## 4. What May Change

This is a living status surface. As the project develops, proof artifacts may be added, deferred items may move to proven, and the public boundary may shift.

Changes to this document should follow the same discipline as the rest of the public surface: explicit, bounded, and honest about what is real.
