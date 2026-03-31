# Artifact-Gated Startup

## Purpose

This document records an early proof point in the Addison project: runtime behavior depended on the artifact layer being present, and once startup was unblocked, the live system answered from newly instantiated local artifacts rather than falling back to generic project language.

This mattered because it turned the artifact model from a design claim into observed runtime behavior.

---

## What "Artifact-Gated Startup" Means

Artifact-gated startup means the system's path into usable runtime operation depended on required artifact surfaces being present.

Addison did not behave like a loose prompt wrapper that could improvise around missing structure. The artifact layer had to exist in order for the system to come up cleanly and operate against the intended local grounding layer.

That made the artifact boundary functionally meaningful rather than decorative.

---

## Why This Was Important

A major risk in projects like this is building something that sounds structured in documentation but behaves like an ordinary stateless assistant shell when actually run.

What was observed suggested two things:

- startup had real dependency on expected artifacts
- once startup was unblocked, the live runtime answered from those artifacts in practice

That is stronger than documentation alone.

---

## What Was Observed

During local daemon bring-up, missing artifacts had to be created before startup could complete correctly.

After startup was unblocked, the CLI was used to ask grounded questions about current system state, held decisions, and active goals. These questions were chosen because they should map directly to newly created local artifacts under the private brain structure.

The runtime answers reflected those artifacts rather than falling back to vague assistant summary. In particular, the responses correctly reflected:

- the current slowdown/readiness posture
- held decisions such as Addison being more than a model wrapper and canonical memory living under `brain/`
- active goals focused on making shared memory artifacts real and truthful before pushing further runtime expansion

This showed that the new artifact layer was participating in live answers.

---

## What This Proved

### 1. The daemon could boot against the local artifact layer

Startup was not fully clean until the needed artifact surface existed.

### 2. The CLI could reach the daemon and receive grounded replies

The runtime was not only booting; it was answerable through the CLI in a live way.

### 3. Newly instantiated private artifacts were being read in practice

The system answered from current local artifacts covering state, decisions, and goals rather than relying on stale abstraction or generic response behavior.

### 4. The artifact layer was operational, not cosmetic

The artifact model had crossed into real runtime effect.

---

## What Was Only Partially Aligned

The original runtime finding also recorded an important limitation.

The content grounding worked better than the final response voice. The answers were correct, but the runtime still wrapped them in a more report-like interpreter style than the intended private Addison voice. Phrasing such as "Based on the artifact..." or "According to the record..." suggested that the grounding layer was working more cleanly than the final response-layer voice.

That distinction matters because grounded answers do not automatically mean full voice alignment.

---

## What This Did Not Prove

This proof point is meaningful, but it should stay bounded.

It did **not** prove that:

- the full architecture is complete
- every subsystem is validated
- the response layer is fully aligned
- the memory model is fully mature
- the system is production-ready

It proved a narrower and stronger point:

**Addison's runtime depended on real artifact grounding, and once startup was unblocked, the live system answered from newly instantiated local artifacts in practice.**

---

## Why This Counts as Public Proof

A reasonable external question is: how do we know this is more than a themed assistant with extra files around it?

One answer is that the system did not just start cleanly by ignoring missing structure, and once brought up, it answered from current local artifact surfaces covering system state, decisions, and goals.

That is concrete evidence that the artifact layer was participating in runtime reality.

---

## Public Boundary Note

This document intentionally describes the behavior without publishing the private artifact contents themselves.

Public proof does not require dumping private system state. It requires making the observed behavior legible and defensible.

---

## Practical Summary

Artifact-gated startup means Addison did not come into intended operation as though the artifact layer were optional.

Once startup was unblocked and the expected local artifact surface existed, the daemon booted, the CLI connected, and live answers reflected current private artifacts covering system state, held decisions, and active goals.

Grounding worked. Voice alignment was only partial. That was still an important milestone because it showed the system was speaking from the right ground, even before the final response layer was fully refined.
