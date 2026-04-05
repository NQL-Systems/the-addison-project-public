# Public vs. Private

## Purpose

This document explains the boundary between the public Addison repository and the private working repository.

The public repository exists to make the system legible from the outside. The private repository remains the canonical development surface.

They are related but serve different roles.

---

## What the Public Repository Is

The public repository is a curated documentation and proof surface.

Its role is to provide:

- a readable explanation of what Addison is
- a high-level view of the architecture
- public-safe descriptions of workflow and method
- bounded proof artifacts showing that key system behaviors are real
- examples and templates that help others understand the artifact model
- project status material that accurately reflects current public claims

This repository should help an external reader understand the shape of the system without needing access to the private repo.

---

## What the Public Repository Is Not

The public repository is not:

- the authoritative live development repo
- a complete mirror of private implementation
- a dump of internal prompts, private artifacts, or operator state
- a release surface for every internal governance document
- a promise that all internal structure will be published later

Public visibility is not the same thing as full disclosure. The goal is clarity, not total exposure.

---

## What Stays Private

The private repository remains the home for materials that are operationally sensitive, personally anchored, or tightly coupled to the live development environment.

Examples include:

- active internal development code and experimental work
- private identity and cognition artifacts
- operator-specific runtime state
- internal memory surfaces and session artifacts
- internal governance material not intended for publication
- raw development history not yet ready for public framing
- any artifact whose publication would blur the line between template and live private state

Private does not mean unimportant. The private surfaces are often the most important parts of the system. They are simply not appropriate for public release.

---

## Canonical Source of Truth

For active development, the private repository is canonical.

The private repository is the source of truth for current implementation, internal architecture decisions, runtime-facing artifact structure, internal governance, and experimental work.

The public repository is downstream from that work. Public documentation may be derived from the private project, but it is not a one-to-one mirror and should not be treated as the complete authoritative surface for all technical detail.

---

## How They Relate

- private work happens first
- public documentation follows when material is ready for safe publication
- not every private artifact becomes public
- not every internal decision needs a public mirror
- public docs should only claim what can be defended safely and truthfully

The public repo reflects the real system, but in a form appropriate for publication.

---

## This Repo Is Not a Stripped Mirror

A stripped mirror implies that the public repo is just the private repo with sensitive lines removed.

That is not the right model.

This public repo is a deliberately shaped surface. It is curated to explain the system well, show real proof, and preserve the integrity of the private operating environment.

Some public documents may be rewritten for clarity, reduced in scope, or reorganized for external readers rather than copied directly from private materials. That is intentional.

---

## Practical Rule

**Public documents should explain the system and support truthful external understanding. Private materials should continue to support actual operation, development, and internal cognition without being exposed by default.**

For the privacy principles and maintenance discipline that govern this boundary, see [privacy-boundary.md](privacy-boundary.md).
