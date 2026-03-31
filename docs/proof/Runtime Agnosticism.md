# Public Proof — Runtime Agnosticism

**Status:** Public proof artifact  
**Authority:** Public-safe observed behavior record

---

## Purpose

A core public claim of Addison is that the daemon remains authoritative while operator runtimes act as interchangeable surfaces over that same core system.

This document records a bounded proof of that claim. During live runtime use, two different operator surfaces — the CLI and the shell — were connected to the same daemon-backed session and displayed the same daemon-authored response.

This matters because it supports the architectural claim that Addison's core state and response flow do not belong to any one frontend.

---

## Claim Under Test

The Addison daemon can serve multiple runtimes built on different technology stacks without those runtimes becoming independent truth owners.

---

## Why This Matters

Runtime agnosticism is one of Addison's architectural north stars.

If this claim holds, then:

- the daemon remains the center of truth
- runtimes can differ in presentation without redefining system state
- operator surfaces can be replaced or compared without requiring a new core architecture
- session truth does not belong to any one frontend

This keeps the system's core identity separate from its presentation layer.

---

## Setup

- The Addison daemon was running locally.
- `addison-cli` was connected as one operator runtime.
- `addison-shell` was connected simultaneously as a second runtime.
- Both runtimes were attached to the same active session.
- A live exchange was visible in both surfaces.

---

## Procedure

1. The operator used the live system with both runtimes connected to the same daemon.
2. A prompt was sent through the active session.
3. Both runtimes displayed the daemon-authored response for that same exchange.
4. Session identity and runtime posture were compared across the two surfaces.

---

## Observations

The screenshot shows both runtimes displaying the same active-session identity and the same Addison response.

Visible evidence includes:

- the same session ID across both runtimes
- the same operator exchange
- the same daemon-authored response appearing in both the CLI and the shell

The two runtimes clearly differ in presentation:

- the CLI renders the exchange in a terminal-managed transcript surface
- the shell renders the exchange in its Electron/Vue presentation layer

The shell also displays `RUNTIME DIVERGED`, which is useful evidence of truthful local posture reporting rather than false claims of total synchronization. Even while presentation and local status differ, both runtimes are still visibly attached to the same daemon-centered session truth.

---

## What This Supports

This proof supports the claim that Addison's core runtime is not tied to a single frontend.

Specifically, it supports that:

- two different runtimes can connect to the same daemon-backed session
- both can display the same daemon-authored response
- session truth can remain centralized while presentation differs by runtime
- runtime surfaces can report their own local posture without claiming authority over the core state

This is evidence for runtime agnosticism in the bounded sense that multiple operator surfaces can observe and present the same underlying daemon-centered interaction.

---

## What This Does Not Prove

This proof is bounded.

It does **not** prove that:

- all runtimes are equally mature or feature-complete
- runtime switching is seamless in every scenario
- every runtime transition, reconnect path, or restore path behaves identically
- all retained runtimes share identical capabilities or local state handling

It proves a narrower point:

**Different runtimes can attach to the same Addison daemon and present the same session-centered interaction without becoming separate owners of system truth.**

---

## Public-Safe Evidence

This proof can be supported publicly without exposing private artifact contents.

Public-safe evidence includes:

- a side-by-side screenshot of the CLI and shell
- visible session-ID agreement across both runtimes
- the same operator exchange and Addison response visible in both surfaces
- truthful local status reporting from the shell (`RUNTIME DIVERGED`) without exposing sensitive internal state

No private artifact content, operator identity material beyond the visible handle, or sensitive internal runtime data needs to be published in order to support this proof.
