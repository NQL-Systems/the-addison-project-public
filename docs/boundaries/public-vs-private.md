# Public vs. Private

## Purpose

This document explains the boundary between the public Addison repository and the private working repository.

The public repository exists to make the system legible from the outside. It is meant to show what Addison is, how it is structured, what has been proven so far, and how the project is being approached.

It is not the full operating environment.

The private repository remains the canonical development surface for active implementation, governance evolution, internal testing, and private artifact work.

---

## Why the Boundary Exists

Addison is not just a codebase. It is a system built around runtime behavior, artifact grounding, operator-authored documentation, and persistent cognitive structure.

Some parts of that system can be published safely and usefully.

Some parts should not be published because doing so would either:

- expose private operator-facing artifacts
- reveal internal state or internal governance surfaces not intended for public release
- create a misleading impression that the public repo is a complete runnable mirror
- weaken the separation between explanatory material and live working internals

The boundary exists to make the system understandable without collapsing the distinction between public explanation and private operation.

---

## What the Public Repository Is

The public repository is a public-facing documentation and proof surface.

Its role is to provide:

- a readable explanation of what Addison is
- a high-level view of the architecture
- public-safe descriptions of workflow and method where relevant
- bounded proof artifacts showing that key system behaviors are real
- examples and templates that help others understand the artifact model
- project status and system-overview material that accurately reflect current public claims

This repository should help an external reader understand the shape of the system without needing access to the private repo.

---

## What the Public Repository Is Not

The public repository is not:

- the authoritative live development repo
- a complete mirror of private implementation
- a dump of internal prompts, private artifacts, or operator state
- a release surface for every internal governance document
- proof that every private capability or design idea is production-ready
- a promise that all internal structure will be published later

This matters because public visibility is not the same thing as full disclosure.

The goal is clarity, not total exposure.

---

## What Belongs in Public

Material is a good fit for the public repository when it helps explain or evidence the system without exposing private internals.

Examples include:

- public README and overview material
- architecture descriptions written for external readers
- public project status documentation
- public-safe proof writeups
- examples of artifact layout using templates or sanitized structures
- boundary documents explaining what is and is not included
- method-facing documents where publication does not expose private operating surfaces

Public material should be legible, accurate, bounded, and safe to stand on its own.

---

## What Stays Private

The private repository remains the home for materials that are operationally sensitive, personally anchored, incomplete in a way that would mislead external readers, or tightly coupled to the live development environment.

Examples include:

- active internal development code and experimental work
- private identity and cognition artifacts
- operator-specific runtime state
- internal memory surfaces and session artifacts
- internal governance material not intended for publication
- implementation details that would expose private operating posture
- raw development history that is not yet ready for public framing
- any artifact whose publication would blur the line between template and live private state

Private does not mean unimportant.

In many cases, the private surfaces are the most important parts of the system. They are simply not appropriate for public release.

---

## Canonical Source of Truth

For active development, the private repository is canonical.

That means the private repository is the source of truth for:

- current implementation work
- current internal architecture decisions
- runtime-facing artifact structure
- internal governance and enforcement evolution
- experimental changes not yet matured into public-safe form

The public repository is downstream from that work.

Public documentation may be derived from the private project, but it should not be treated as a one-to-one mirror of the private repo or as the complete authoritative surface for all technical detail.

---

## Relationship Between Public and Private

The public and private repositories are related, but they serve different roles.

The private repo is where the system is actively built, tested, corrected, and evolved.

The public repo is where the system is explained, bounded, and evidenced for outside readers.

In practice, that means:

- private work may happen first
- public documentation may follow later
- not every private artifact becomes public
- not every internal decision needs a public mirror
- public docs should only claim what can be defended safely and truthfully

The public repo should reflect the real system, but in a form appropriate for publication.

---

## Public-Safe Proof

A recurring principle in this repository is public-safe proof.

Public-safe proof means showing enough evidence to demonstrate that Addison is real, structured, and grounded without exposing the private artifact layer itself.

That can include:

- writeups of observed runtime behavior
- bounded proof documents describing what was tested
- screenshots where appropriate
- sanitized examples
- structural examples that show form without leaking private content

The standard is not maximum disclosure.

The standard is credible proof under a deliberate boundary.

---

## Why This Repo Should Not Be Read as a Stripped Mirror

A stripped mirror implies that the public repo is just the private repo with sensitive lines removed.

That is not the right model.

This public repo is a deliberately shaped surface. It is curated to explain the system well, show real proof, and preserve the privacy and integrity of the internal operating environment.

That means some public documents may be rewritten for clarity, reduced in scope, or reorganized for external readers rather than copied directly from private development materials.

This is intentional.

The goal is not to publish everything.
The goal is to publish the right things.

---

## Future Publication

The public boundary may change over time.

As the project matures, some materials that are currently private may become publishable in templated, abstracted, or rewritten form.

But publication should happen only when it improves public understanding without exposing private operational surfaces or creating false confidence about what is complete.

Expansion of the public surface should be deliberate.

It should not happen by drift, leakage, or convenience.

---

## Practical Rule

A simple rule governs this boundary:

**Public documents should explain the system and support truthful external understanding. Private materials should continue to support actual operation, development, and internal cognition without being exposed by default.**

That distinction is intentional and foundational to how Addison is being built.
