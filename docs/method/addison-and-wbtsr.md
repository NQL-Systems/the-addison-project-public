# Addison and WBTSR

**Status:** Public-facing distinction note  
**Authority:** Public-safe explanatory surface  
**Purpose:** Clarify the difference between Addison as the system and WBTSR as the workflow used to build it.

---

## 1. The Short Version

Addison is the system.  
WBTSR is the workflow.

They are related, but they are not the same thing.

That distinction matters because the system and the method solve different problems.

---

## 2. What Addison Is

Addison is a local, daemon-backed state system built around:

- persistent artifacts
- deterministic context construction
- stateless inference
- human-governed operation

It is the actual system being built.

Its focus is architectural:

- where memory lives
- how continuity is preserved
- how state is managed
- how inference is used without becoming the hidden authority

Addison is the built thing.

---

## 3. What WBTSR Is

WBTSR is the named workflow used to build and govern the work around Addison.

WBTSR stands for:

- **Work**
- **Build**
- **Truth**
- **Session**
- **Rehydrate**

It is a human-governed method for working with AI through:

- bounded runs
- bounded slices
- separate builder and auditor roles
- explicit truth surfaces
- closeout discipline
- restart-safe rehydration between sessions

WBTSR is not the system itself.

It is the method used to help build the system honestly and in controlled steps.

---

## 4. Why the Distinction Matters

Without the distinction, it becomes easy to blur together:

- the thing being built
- the workflow used to build it
- the evidence that the workflow worked

Those are not interchangeable.

A system can be real even if the method changes.

A workflow can be portable even when it originated inside one specific build.

Addison is evidence that WBTSR worked in one real context, but Addison is not identical to WBTSR.

---

## 5. Different Roles

### Addison answers questions like

- How should state be held?
- Where should continuity live?
- What should the daemon own?
- How should inference relate to the system?

### WBTSR answers questions like

- How should work be scoped?
- How should agent output be audited?
- How should truth be preserved across sessions?
- How should bounded work be closed and carried forward?

One is an architecture and runtime problem.  
The other is a workflow and governance problem.

---

## 6. How They Relate

WBTSR emerged through the process of building Addison.

That means the two are connected:

- Addison gave the method a real proof case
- WBTSR helped keep Addison’s build process bounded, inspectable, and restart-safe

But connection is not identity.

The method may be useful outside Addison.
The system may continue evolving even if the workflow is adapted.

---

## 7. What This Public Surface Claims

This public distinction note makes a modest claim:

- Addison is a real system under active development
- WBTSR is a real workflow extracted from building that system
- the system and the workflow are related but separate

It does **not** claim:

- that WBTSR is universally proven
- that Addison is complete
- that the method and the system collapse into one thing
- that every part of either is fully exposed in this public repository

---

## 8. Working Summary

Addison is the system.  
WBTSR is the workflow used to build it.

Addison is about system architecture, continuity, state, and governed operation.

WBTSR is about bounded work, explicit truth, separate build/audit roles, closeout, and rehydration.

The system is the built result.  
The workflow is the method that helped produce it.
