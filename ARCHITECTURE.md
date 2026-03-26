# Addison Architecture

**Status:** Public-facing architecture overview  
**Authority:** Public-safe technical orientation  
**Purpose:** Explain the architectural shape of Addison without exposing private runtime state or internal development-only detail.

---

## 1. What Addison Is

Addison is a local, daemon-backed state system built around persistent artifacts, deterministic context construction, and stateless inference.

Its core idea is simple:

- the **system** owns memory and continuity
- the **model** is a replaceable reasoning tool
- the **human** remains the governing authority over meaningful action

Addison is designed to hold shape across sessions without depending on chat history, hidden model memory, or vague continuity.

---

## 2. Architectural North Stars

Addison is built around a small set of architectural rules:

### 2.1 Artifact Primacy

Persistent truth lives in artifacts, not in model-side memory.

### 2.2 Daemon Authority

The daemon is the system’s authority layer. Interfaces and adapters consume state from it rather than owning truth themselves.

### 2.3 Deterministic Core

Memory handling and context construction are deterministic. The core does not rely on inference to decide what system state is.

### 2.4 Stateless Inference

Inference is treated as a utility. The model operates on prepared context and does not serve as the continuity layer.

### 2.5 Human-Governed Operation

Addison is built so that meaningful system action remains governed rather than silently delegated.

---

## 3. Layer Model

Addison is easiest to understand as a layered system.

### Layer 1 — Core Authority

This is the daemon-centered core.

It is responsible for:

- persistent state
- artifact-backed memory
- context assembly
- governed proposal/action boundaries
- protocol orchestration across connected runtimes

This layer is where system truth is held and maintained.

### Layer 2 — Operator Runtimes

These are the operator-facing surfaces.

They exist to:

- connect to the daemon
- present state and responses
- send operator requests
- provide bounded interaction workflows

These runtimes are intentionally **non-authoritative**. They do not replace the daemon’s role as the source of truth.

### Layer 3 — Optional Presentation Adapters

These are subordinate surfaces that may enhance presentation or interaction.

They can make the system easier or more expressive to use, but they are not required for the core system to remain coherent.

---

## 4. How State Flows

At a high level, Addison operates like this:

1. persistent artifacts hold the current durable truth
2. the daemon reads and manages that state
3. deterministic context is assembled from approved artifacts
4. inference operates on that prepared context
5. runtime adapters present results back to the operator
6. any meaningful follow-on action remains subject to system rules and operator control

This keeps continuity outside the model and makes the system easier to inspect, restart, and reason about.

---

## 5. Memory Model

Addison uses an artifact-backed memory model.

### 5.1 Canonical Memory

Durable system truth is stored in persistent artifacts.

These artifacts can represent things like:

- identity and voice scaffolds
- current system status
- goals and decisions
- working state needed for continuity

### 5.2 Non-Canonical Derived Support

Some support material may be derived from canonical artifacts for convenience or bounded reduction, but derived outputs do not replace canonical truth.

### 5.3 Volatile Runtime State

Some runtime-local state may exist for operator experience or temporary hydration, but that is not the same thing as durable system memory.

---

## 6. Inference Model

Addison does not treat the model as the system.

Instead:

- context is built outside the model
- the model receives prepared input
- the model returns reasoning/output
- the system remains responsible for memory, continuity, and authority

This distinction is one of the most important parts of the architecture.

The goal is not “AI that just figures it out.”
The goal is a system where intelligence can be applied without surrendering control of state.

---

## 7. Runtime Philosophy

Addison is designed to be runtime-agnostic.

That means operator surfaces can change without changing the architectural role of the core system.

A runtime may be:

- fast and minimal
- broader and more inspectable
- more performative or presentation-oriented

But the architectural contract stays the same:

- the daemon remains authoritative
- artifacts remain the continuity layer
- inference remains downstream of prepared context
- runtimes remain consumers rather than truth owners

---

## 8. What This Architecture Prioritizes

This architecture prioritizes:

- restartable continuity
- inspectable state
- clear authority boundaries
- deterministic memory and context handling
- bounded human-governed operation

It is intentionally biased toward truthful structure over convenience.

---

## 9. What Addison Is Not

Addison is **not**:

- a chatbot wrapper
- a hidden-autonomy system
- a model-owned memory system
- a general “multi-model round table”
- a polished production platform

It is an experimental local system designed to explore a different architectural posture:
one where state, control, and continuity belong to the system rather than to the model.

---

## 10. Public Boundary Note

This document is a public-safe architecture overview.

It explains the system’s structure and principles, but it does not include:

- live private memory
- operator-specific identity content
- runtime-local private state
- internal prompts or logs
- the full private development authority

Public surfaces for Addison are intentionally partial.

---

## 11. Working Summary

Addison is a local, daemon-backed state system with artifact-backed memory, deterministic context construction, and stateless inference.

Its architecture is built to keep truth and continuity in the system itself, so AI can be used as a tool without becoming the hidden authority.
