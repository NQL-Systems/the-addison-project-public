# Privacy Boundary

## Purpose

This document explains the privacy principles that govern the public Addison repository.

For the structural distinction between the public and private repos, see [public-vs-private.md](public-vs-private.md). This document covers *why* the boundary exists as a deliberate design choice, what it protects, and how to maintain it.

---

## Why a Privacy Boundary Is Necessary

Addison is built around more than code alone. Its structure includes documentation, artifact grounding, persistent state surfaces, operator-authored materials, internal governance, and runtime-facing cognitive scaffolds.

Some of that material can be published safely. Some of it should remain private because publication would either:

- expose operator-specific information
- reveal private internal state
- disclose runtime cognition surfaces not meant for public release
- blur the boundary between public examples and live private artifacts
- reduce the integrity of the project by turning internal operating material into outward-facing spectacle

A privacy boundary is therefore part of the architecture of responsible publication.

---

## What This Boundary Protects

The privacy boundary protects classes of material that are tied to live operation, internal cognition, personal context, or private development posture.

That includes, but is not limited to:

- private identity artifacts
- internal memory and session artifacts
- operator-specific state
- internal governance material not intended for publication
- live runtime artifact content
- raw internal prompts and system-shaping materials
- any artifact that reflects private cognition rather than public explanation

The fact that these materials exist is part of the project's reality. Publishing them is not required in order to show that the system is real.

---

## Privacy Is Not Secrecy

This repo is not trying to create mystique by withholding everything important.

The privacy boundary exists to separate:

- what should be publicly explainable
- what is privately operational
- what can be safely evidenced
- what should remain internal to the working system

Where possible, the public repo should still provide truthful, grounded explanation of what exists behind the boundary. The boundary prevents inappropriate exposure. It does not replace clarity with vagueness.

---

## Proof Under Boundary

A core publication principle is that proof can exist without full disclosure.

The repo may provide bounded writeups of runtime observations, proof-oriented documentation describing what was tested and why it matters, sanitized structural examples, and public descriptions of tested behaviors.

This allows outside readers to evaluate whether Addison is real and structured without requiring publication of the full private artifact layer.

The standard is credible public evidence under controlled disclosure.

---

## Sanitized and Templated Publication

When private structures need to be shown publicly, they should be rewritten into safe forms:

- templates instead of live files
- examples instead of real artifacts
- structural illustrations instead of content dumps
- proof writeups instead of direct exposure of private state

This keeps the public surface useful while preserving the integrity of the private system. The aim is not to pretend the private layer does not exist. The aim is to represent it responsibly.

---

## Boundary Drift Must Be Resisted

A privacy boundary is easy to weaken accidentally. That can happen when:

- internal files are copied outward for convenience
- examples stop being examples and become leaked live surfaces
- public docs start mirroring private material too closely
- a desire to "show more" overtakes publication discipline

Public release should remain intentional. Any material that crosses from private to public should be reviewed for whether it is safe, truthful, necessary, and understandable outside its original internal context.

Not everything valuable becomes more valuable by being published.

---

## Practical Rule

**If a document helps explain Addison publicly without exposing private operational, cognitive, or operator-linked internals, it may belong in public. If it depends on live private state or exposes private internal surfaces, it stays private unless deliberately transformed into a safe public form.**
