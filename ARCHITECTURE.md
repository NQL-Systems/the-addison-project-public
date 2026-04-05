# Addison Architecture

**Status:** Public-facing architecture overview
**Authority:** Public-safe technical orientation

---

## 1. Architectural Motivation

Most AI systems keep continuity inside the conversation or inside the model.

That can produce useful outputs in the moment, but it also makes continuity fragile. State can blur into generated text, context can degrade across sessions, and the model can start acting like the hidden authority.

Addison is built in the opposite direction.

Its core architectural idea is simple:

- the **system** owns memory and continuity
- the **model** is a replaceable reasoning tool
- the **human** remains the governing authority over meaningful action

The architecture exists to make that idea concrete in a form that can be restarted, inspected, and reasoned about without depending on model-side memory.

---

## 2. Architectural North Stars

Addison is built around a small set of rules that shape every layer of the system.

**Artifact primacy.** Persistent truth lives in artifacts, not in model-side memory.

**Daemon authority.** The daemon is the system's authority layer. Interfaces and adapters consume state from it rather than owning truth themselves.

**Deterministic core.** Memory handling and context construction are deterministic. The core does not rely on inference to decide what system state is.

**Stateless inference.** Inference is treated as a utility. The model operates on prepared context and does not serve as the continuity layer.

**Human-governed operation.** Meaningful system action remains governed rather than silently delegated.

---

## 3. Layer Model

Addison is structured as three layers with explicit authority boundaries.

### Layer 1 — Core Authority

The daemon-centered core.

This layer is responsible for persistent state, artifact-backed memory, deterministic context assembly, governed action boundaries, and protocol orchestration across connected runtimes.

This is where system truth is held and maintained.

### Layer 2 — Operator Runtimes

Operator-facing surfaces that connect to the daemon, present state and responses, send operator requests, and provide bounded interaction workflows.

These runtimes are intentionally **non-authoritative**. They do not replace the daemon's role as the source of truth.

### Layer 3 — Optional Presentation Adapters

Subordinate surfaces that may enhance expression or presentation, including optional voice synthesis and avatar presentation.

They can make the system more expressive to use, but they are not required for the core system to remain coherent. The system degrades truthfully when these adapters are unavailable.

---

## 4. How State Flows

1. Persistent artifacts hold the current durable truth.
2. The daemon reads and manages that state.
3. Deterministic context is assembled from approved artifacts.
4. Inference operates on that prepared context.
5. Runtime adapters present results back to the operator.
6. Any meaningful follow-on action remains subject to system rules and operator control.

This keeps continuity outside the model and makes the system easier to inspect, restart, and reason about.

---

## 5. Memory Model

Addison uses an artifact-backed memory model with three tiers.

**Canonical memory.** Durable system truth stored in persistent artifacts. These can include identity scaffolds, current system status, goals and decisions, and other continuity-bearing surfaces.

**Non-canonical derived support.** Material derived from canonical artifacts for bounded reduction or convenience. Derived outputs do not replace canonical truth.

**Volatile runtime state.** Runtime-local state that may exist for temporary hydration or operator experience. This is not the same thing as durable system memory.

---

## 6. Inference Model

Addison does not treat the model as the system.

Context is built outside the model. The model receives prepared input, produces reasoning and output, and then returns control to the system.

The system remains responsible for memory, continuity, and authority.

That distinction is one of the most important parts of the architecture. The goal is not to let the model silently become the system. The goal is to apply intelligence inside a structure where truth remains visible and owned.

---

## 7. Runtime Philosophy

Addison is designed to be runtime-agnostic.

Operator surfaces can change without changing the architectural role of the core system. A runtime may be minimal, broader and more inspectable, or more presentation-oriented.

The architectural contract stays the same:

- the daemon remains authoritative
- artifacts remain the continuity layer
- inference remains downstream of prepared context
- runtimes remain consumers rather than truth owners

---

## 8. Observed Public Proof Relationship

This document is a public-safe architecture overview, not a proof dump.

The current public surface supports a bounded claim that this architecture is not merely aspirational language. The repo's public proof and status surfaces are intended to show that the daemon-authoritative, artifact-backed, deterministic posture reflects a real system rather than a purely conceptual design.

For the current public claim boundary, see [PUBLIC_STATUS.md](PUBLIC_STATUS.md).

---

## 9. What This Architecture Prioritizes

This architecture is intentionally biased toward truthful structure over convenience. It prioritizes:

- restartable continuity
- inspectable state
- clear authority boundaries
- deterministic memory and context handling
- bounded human-governed operation

The central system question Addison is trying to answer is not just how to make AI more capable in the moment. It is where truth lives, who owns continuity, how state is preserved, how boundaries stay visible, and how intelligence can be applied without becoming the hidden authority.

---

This document is a public-safe architecture overview. It does not include live private memory, operator-specific identity content, internal prompts, or the full private development authority. See [README.md](README.md) for repository boundary details.
