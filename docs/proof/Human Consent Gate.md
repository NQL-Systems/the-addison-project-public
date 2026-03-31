# Proof — Human Consent Gate

## Claim Under Test

Governed proposals in Addison require explicit human authorization. The system blocks write operations that have not passed through the operator approval boundary.

## Why This Matters

The Human Consent Gate is one of Addison's architectural northstars. It means the system cannot silently mutate canonical truth surfaces — writes to governed paths must pass through a deterministic pending-proposal inbox and receive explicit operator authorization before they take effect.

Without this, an inference-driven system could quietly alter its own memory, goals, or behavioral grounding. The consent gate is what keeps the operator in control of what becomes canonical truth.

## Setup

- The Addison daemon was running locally.
- A runtime was connected and a conversation turn was in progress.
- During the turn, the system generated a governed proposal to write to a canonical artifact path.

## Observations

The daemon log captured a governed proposal attempting to write to `brain/metrics/token_ledger.jsonl`.

The proposal was evaluated against the governance layer and returned:

- `policy_outcome`: `approval_required`
- `status`: `blocked`
- `reason`: referencing the explicit approval boundary

The write did not proceed. The proposal was stopped by the governance layer because it had not received operator authorization.

This behavior was not triggered by a test or a synthetic scenario. It occurred during normal runtime operation as part of a real conversation turn.

## What This Supports

This supports the claim that Addison's governance layer enforces a real consent boundary on write operations to canonical artifact paths:

- A proposal was generated during normal runtime operation.
- The governance layer evaluated it and found it required approval.
- The write was blocked, not silently executed.
- The system logged the block with an explicit reason.

The consent gate is not decorative. It stopped a real write in practice.

## What This Does Not Prove

- This does not prove that every possible write path is covered by the governance layer. It proves that the governed proposal path enforces its boundary when hit.
- This does not prove that the approval workflow is complete end-to-end (proposal → operator review → promotion). It proves the blocking side works.
- This does not prove that the system is immune to all forms of unauthorized mutation — only that the governed proposal mechanism enforces its declared boundary.

## Public-Safe Evidence

- daemon log output showing the proposal with `approval_required` outcome and `blocked` status
- the logged reason referencing the explicit approval boundary
- the target path (`brain/metrics/token_ledger.jsonl`) is a canonical artifact path, confirming the governance layer applies to real artifact surfaces
- no private artifact content, operator identity, or sensitive data is visible in the log output
