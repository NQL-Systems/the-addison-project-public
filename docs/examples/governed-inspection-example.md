# Governed Inspection Example

## Purpose

This document provides a public-safe example of how Addison's governed action lifecycle works in practice.

The example uses the system's first governed seam — bounded read-only file inspection — to show the proposal, approval, execution, and result stages. The lifecycle described here is real and landed, not aspirational.

This is an illustrative walkthrough, not a dump of internal governance artifacts.

---

## What Governed Action Means

In Addison, meaningful system actions beyond ordinary conversation are subject to a governed lifecycle. The system does not silently perform side effects. Instead, it moves through explicit stages with operator control at each gate.

The core stages are:

1. **Proposal** — the system creates a candidate action request with an explicit target and scope
2. **Approval** — the operator reviews the proposal and explicitly approves or rejects it
3. **Execution** — if approved, the system attempts the bounded action
4. **Result** — the system reports what actually happened, without assuming success

Each stage is daemon-owned. Runtimes present the stages to the operator but do not own the proposal, approval, or result truth.

---

## Example: Read-Only File Inspection

The first governed seam in Addison is one-shot, operator-approved, repo-bounded, read-only inspection of a single file.

### What the operator does

The operator requests inspection of a specific file:

~~~text
/inspect brain/shared/system_status.md
~~~

### What the daemon does

1. The daemon creates a canonical proposal for read-only inspection of that specific repo-relative path.
2. The daemon checks tool eligibility — is this action class available under the current mode?
3. If eligible, the daemon presents the proposal to the operator through the runtime.
4. The daemon waits for explicit operator approval.

### What happens at approval

- If the operator approves, the daemon attempts one bounded read of the specified file.
- If the operator rejects, the daemon records the rejection and stops. No action is taken.
- If the proposal is ineligible, degraded, or invalid, the daemon refuses truthfully before approval is even offered.

### What happens at execution

- The daemon reads the file within the approved scope.
- The result is returned to the operator through the runtime.
- The proposal is consumed — it cannot be reused for a second read.

### What does not happen

- The system does not browse, search, or discover files on its own.
- The system does not read multiple files under one approval.
- The system does not modify, delete, or execute anything.
- The system does not treat a successful read as permission for further action.
- The runtime does not own proposal or approval state — it only presents daemon-owned truth.

---

## Why This Matters Architecturally

This lifecycle demonstrates several architectural properties:

- **Daemon authority over governed action.** The daemon owns the full proposal/approval/result lifecycle. Runtimes are downstream presenters only.
- **Explicit operator consent.** Nothing governed happens without the operator saying yes.
- **One-shot scope.** Each approval covers exactly one bounded action. There is no standing permission.
- **Truthful refusal and degradation.** If the system cannot do what was asked, it says so explicitly rather than pretending success.
- **Tool eligibility gating.** The system checks whether the action class is even available under the current mode before presenting it to the operator.

---

## What This Example Is Not

This example shows the lifecycle of one governed seam. It does not expose:

- internal governance artifact schemas
- the full tool-eligibility taxonomy
- internal approval state structures
- private governance enforcement code

It is a structural illustration of how governed action works, not a release of internal governance surfaces.

---

## Related

- [ARCHITECTURE.md](../../ARCHITECTURE.md) — public architecture overview
- [PUBLIC_STATUS.md](../../PUBLIC_STATUS.md) — current public claims including governed action boundaries
- [action_policy.template.md](../templates/action_policy.template.md) — public-safe action policy scaffold
