# Public Proof — Human Consent Gate

**Status:** Public proof artifact  
**Authority:** Public-safe observed behavior record

---

## Purpose

A core claim of Addison is that governed writes to canonical truth surfaces do not happen silently.

This document records a bounded proof of that claim. During normal runtime operation, Addison generated a proposal to write to a canonical artifact path, and the governance layer blocked that write because explicit human approval had not been granted.

This matters because it shows that the consent boundary is operational in practice, not only described in architecture.

---

## Claim Under Test

Governed proposals in Addison require explicit human authorization before they can write to canonical artifact paths.

---

## Why This Matters

The Human Consent Gate is one of Addison's architectural north stars.

Without a real consent boundary, an inference-driven system could quietly mutate its own memory, goals, metrics, or other canonical truth surfaces during ordinary runtime behavior.

If this claim holds, then governed write proposals remain subordinate to operator approval rather than becoming canonical truth automatically.

---

## Setup

- The Addison daemon was running locally.
- A runtime was connected and a normal conversation turn was in progress.
- During that turn, the system generated a governed proposal targeting a canonical artifact path.

---

## Observations

During runtime, the daemon logged a governed proposal attempting to write to:

- `brain/metrics/token_ledger.jsonl`

The governance layer evaluated that proposal and returned:

- `policy_outcome: approval_required`
- `status: blocked`

The logged reason explicitly referenced the approval boundary.

The write did not proceed. The proposal was stopped because operator authorization had not been granted.

This was not a synthetic or isolated harness test. It occurred during ordinary runtime behavior.

---

## What This Supports

This proof supports the claim that Addison's governance layer enforces a real approval boundary on governed writes to canonical artifact paths.

Specifically, it supports that:

- a governed write proposal can be generated during normal runtime behavior
- the governance layer evaluates that proposal against an approval rule
- a proposal that requires approval is blocked rather than silently executed
- the block is logged explicitly rather than being hidden

This makes the consent gate an active system boundary rather than a decorative policy statement.

---

## What This Does Not Prove

This proof is bounded.

It does **not** prove that:

- every possible write path in the system is already covered by the same enforcement layer
- the full end-to-end approval workflow is complete in every direction
- the system is immune to all forms of unauthorized mutation

It proves a narrower point:

**When the governed proposal path is hit, Addison can block canonical writes pending explicit human approval.**

---

## Public-Safe Evidence

This proof can be supported publicly without exposing private artifact contents.

Public-safe evidence includes:

- daemon log output showing the proposal evaluation
- the `approval_required` policy outcome
- the `blocked` status
- the canonical target path involved in the proposal

No private artifact content, operator identity material, or sensitive internal state needs to be published in order to support this proof.
