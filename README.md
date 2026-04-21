# Addison

## ⚠️ Documentation Status

I am currently behind on updating this public documentation.

The project is evolving rapidly (daily changes, active exploration work), and this repo has not caught up yet. Some content here is now historical or does not reflect the current system.

I will bring this documentation forward once the current development cycle stabilizes.

For now, consider this a **lagging snapshot of the project**, not the current state.

Addison is a local, daemon-backed state system built around persistent artifacts, deterministic context construction, and stateless inference.

This repository is a bounded public surface for the project. It contains public-safe documentation, bounded proof framing, and contributor-facing orientation. It does not contain live private memory, operator-specific identity, or the full private development authority.

You can find a devlog of this project in [The-Addison-Project-Devlogs](https://github.com/Zerolxgic/The-Addison-Project-Devlogs). That is my personal repository page.

## Why This Repo Exists

Most AI systems keep continuity inside the conversation or inside the model.

Addison is built in the opposite direction. It keeps memory, continuity, and system truth in persistent artifacts, uses deterministic context construction, and treats inference as a replaceable tool rather than as the system itself.

This public repository exists to make that project legible without collapsing the boundary between public-safe explanation and private live system state.

## What Addison Is

Addison is a personal agent system where:

- a local daemon owns runtime authority
- persistent artifacts carry durable continuity
- deterministic context construction happens outside the model
- inference is used as a stateless reasoning tool
- the human operator remains the governing authority over meaningful action

It is not a chatbot wrapper, not a hidden-autonomy system, and not a production-ready platform.

## System Shape

At a high level, the system has three layers:

- a **daemon** that owns runtime authority and system boundaries
- an **artifact layer** (`brain/`) that holds persistent memory and continuity surfaces
- **operator runtimes** that connect to the daemon and provide bounded control surfaces
- **optional presentation adapters** that can enhance expression — including voice synthesis and avatar presentation — without owning system truth

Inference is called into this structure on demand. It does not own system state, and it does not serve as the continuity layer.

For the public architecture overview, see [ARCHITECTURE.md](ARCHITECTURE.md).

## Method

Addison is the system. WBTSR is the workflow used to build it.

WBTSR stands for **Work, Build, Truth, Session, Rehydrate**. It is a human-governed development method built around bounded work slices, explicit truth surfaces, separate production and review roles, and restart-safe rehydration.

For the distinction between the system and the workflow, see [addison-and-wbtsr.md](addison-and-wbtsr.md).

## Public Proof Posture

This repository includes a bounded public proof surface. It is intentionally narrow.

The goal is not to claim that every internal implementation detail is public. The goal is to show enough observed evidence that the public description remains grounded rather than purely aspirational.

For the current proof and claim boundary, see [PUBLIC_STATUS.md](PUBLIC_STATUS.md).

## Documentation Map

- [ARCHITECTURE.md](ARCHITECTURE.md) — public-safe architecture overview
- [PUBLIC_STATUS.md](PUBLIC_STATUS.md) — current public claims, proof posture, and deferred areas
- [addison-and-wbtsr.md](addison-and-wbtsr.md) — distinction between the system and the workflow
- [CONTRIBUTING.md](CONTRIBUTING.md) — how to contribute without weakening the public boundary
- [docs/](docs/) — boundaries, examples, and proof artifacts

## Repository Boundary

This repository is intentionally partial.

It contains public-safe explanation, bounded proof framing, and contribution guidance. It does not contain live private memory, operator-authored identity artifacts, internal prompts, private transcripts, or the full private development authority.

Material here should be read as a bounded public mirror of the project, not as the full internal system.

## Status

Active, experimental, and intentionally partial.
