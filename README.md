# Addison

Addison is a local, daemon-backed state system built around persistent artifacts, deterministic context construction, and stateless inference.

This repository is a bounded public surface for the project. It contains public-safe documentation, proof artifacts, and inert examples. It does not contain live private memory, operator-specific identity, or the full private development authority.

## Why It Exists

Most AI systems keep continuity inside the conversation or inside the model.

Addison is built in the opposite direction. It keeps memory, continuity, and system truth in persistent artifacts, uses deterministic context construction, and treats inference as a replaceable tool rather than as the system itself.

Part of that exploration came from a practical need to externalize ideas, preserve project state, and return to active lines of thought without rebuilding everything from scratch each time.

The goal is to explore a system where intelligence can be applied without surrendering control of state, boundaries, or operator authority.

## What Addison Is

Addison is a personal agent system where a local daemon owns system state, memory lives in persistent artifacts under a `brain/` directory, and the model is a stateless inference tool that gets replaced between sessions without losing continuity. The human operator remains the governing authority over all meaningful action. It is not a chatbot wrapper, a hidden-autonomy system, or a production-ready platform.

## System Shape

At a high level, the system has three layers:

- A **daemon** that owns runtime authority and enforces system boundaries.
- An **artifact layer** (`brain/`) that holds persistent memory, identity, and continuity surfaces.
- A **CLI/TUI interface** that serves as the operator's primary control surface.

Inference is called into this structure on demand. It does not own state, and it does not persist between sessions.

For full architectural detail, see [ARCHITECTURE.md](ARCHITECTURE.md).

## Method

Addison is the system. WBTSR is the workflow used to build it.

WBTSR stands for **Work, Build, Truth, Session, Rehydrate**. It is a human-governed development method based on bounded work slices, explicit truth surfaces, separate builder and auditor roles, and restart-safe rehydration. It emerged from the Addison build process but is maintained as a separate, portable methodology.

For more on the relationship, see [Addison and WBTSR](addison-and-wbtsr.md).

## Public Proof

This repository includes a small set of bounded proof surfaces that show observed system behavior rather than just design claims.

The primary proof artifact is **artifact-gated startup** — a demonstration that the system's runtime path depends on the artifact layer being present, and that once startup completes, the system answers from locally grounded artifacts rather than falling back to generic model behavior. See [Artifact-Gated Startup](artifact-gated-startup.md) for the full writeup.

## Documentation

- [ARCHITECTURE.md](ARCHITECTURE.md) — Technical architecture: daemon, artifact layer, context construction, and inference.
- [Addison and WBTSR](addison-and-wbtsr.md) — The distinction between the system and the workflow.
- [Artifact-Gated Startup](artifact-gated-startup.md) — Proof artifact showing runtime dependency on the artifact layer.
- [PUBLIC_STATUS.md](PUBLIC_STATUS.md) — What this repo currently proves, what remains deferred, and what it does not claim.
- [CONTRIBUTING.md](CONTRIBUTING.md) — How to contribute to the public surface.

## Repository Boundaries

This repository is intentionally partial. It contains public-safe documentation, proof artifacts, and inert examples. It does not contain live private memory, operator-specific identity, private prompts or transcripts, or the full private development authority.

Public material here should be read as a bounded representation of the project, not as the full internal system.

## Status

Active, experimental, and intentionally partial.
