# Public Proof — Deterministic Context Assembly

**Status:** Public proof artifact  
**Authority:** Public-safe observed behavior record

---

## Purpose

A core public claim of Addison is that context assembly is deterministic and artifact-controlled rather than model-generated.

This document records a bounded proof of that claim. It shows that the Addison context builder assembles the system prompt from canonical markdown artifacts through a repeatable, inference-free process.

This matters because it means the system prompt is built from operator-controlled artifacts through inspectable logic rather than being shaped by hidden model-side reasoning.

---

## Claim Under Test

The Addison context builder (`tools/build_context.py`) assembles the system prompt deterministically from canonical markdown artifacts under `brain/`, with no inference involved in the assembly step.

---

## Why This Matters

Deterministic context assembly is one of Addison's core architectural invariants.

If this claim holds, it means:

- the operator can inspect what the model will receive before inference happens
- the same artifact state produces the same context pack
- changing canonical artifact content changes the resulting context pack
- no daemon, model, or external service is required to assemble the pack

This keeps context construction under system and operator control rather than treating the model as the continuity layer.

---

## Setup

- The Addison daemon project was present locally at its expected path.
- Canonical artifacts existed under `brain/` in their current working state.
- The context builder was invoked through `cli.py build`.
- No daemon or inference process was running during the tests.

---

## Procedure and Observations

### Test A — Repeatability

1. Ran the context builder against the current `brain/` artifact state.
2. Hashed the output file (`context/context_pack.md`).
3. Without changing any artifact, ran the context builder again.
4. Hashed the output file again.

**Results:**

- Run 1 hash: `6B0945FB2834BDECC5731327562ECD783C192E370EA2065ECFEAB0A44996BD5E`
- Run 2 hash: `6B0945FB2834BDECC5731327562ECD783C192E370EA2065ECFEAB0A44996BD5E`
- Match: **yes**

The same artifact state produced byte-identical output across two consecutive builds.

### Test B — Artifact-State Sensitivity

1. Ran the context builder and hashed the output.
2. Made one small, intentional, reversible change to a canonical artifact included in the build path.
3. Ran the context builder again and hashed the output.
4. Reverted the change immediately so no artifact remained in a modified state.

**Results:**

- Pre-change hash: `6B0945FB2834BDECC5731327562ECD783C192E370EA2065ECFEAB0A44996BD5E`
- Post-change hash: `AFD328F5DEC7EFF00F327504975C857DA3AE10ECE989260BA5111215F590A387`
- Hashes differ: **yes**
- Revert completed: **yes**

A change to canonical artifact content produced a different context pack. Context assembly was responsive to artifact-state change.

### Test C — No Inference or Daemon Dependency

1. Confirmed that no daemon process was running.
2. Ran the context builder.

**Results:**

- Daemon running: **no**
- Builder completed: **yes**
- Context pack produced: **yes**

The builder completed successfully and produced a context pack without requiring a running daemon, inference model, API key, or external service.

---

## What This Supports

This proof supports the claim that Addison's context assembly is deterministic and inference-free at the build step.

Specifically, it supports that:

- the same artifact state produces the same context output
- canonical artifact changes affect the assembled context pack
- the builder operates independently of daemon runtime and model inference

This makes context construction a real architectural mechanism rather than a descriptive idea.

---

## What This Does Not Prove

This proof is bounded.

It does **not** prove that:

- the assembled context pack is optimal or complete for every runtime situation
- derived support artifacts are themselves deterministic in how they are created
- restart safety, session continuity, or broader memory maturity are fully solved
- the inference layer always uses the resulting context pack faithfully

It proves a narrower point:

**Addison's context assembly step is deterministic, artifact-controlled, and independent of live inference.**

---

## Public-Safe Evidence

This proof can be supported publicly without exposing private artifact content.

Public-safe evidence includes:

- SHA-256 hash comparison results from the repeatability and artifact-state tests
- confirmation that the builder ran successfully without a daemon or model process
- confirmation that the test artifact change was minimal, intentional, and reverted immediately

No private artifact content needs to be published in order to support this proof.
