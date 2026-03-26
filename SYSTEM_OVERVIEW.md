# SYSTEM_OVERVIEW

**Status:** Public-facing system overview  
**Authority:** Public-safe explanatory surface  
**Purpose:** Explain what Addison is, why it exists, and how it works at a system level without exposing private runtime state or internal-only development detail.

---

## 1. What Addison Is

Addison is a local, daemon-backed state system built around persistent artifacts, deterministic context construction, and stateless inference.

At a high level, it is an attempt to build an AI system where:

- continuity belongs to the system instead of the model
- memory lives in explicit artifacts instead of session haze
- the human remains the governing authority over meaningful action

Addison is not designed as a chatbot wrapper or a personality layer placed on top of a model.
It is designed as a system with its own state, boundaries, and continuity model.

---

## 2. Why It Exists

Most AI tools are strongest in the moment and weakest across time.

They can often produce useful outputs, but they usually depend on one or more fragile continuity layers:

- chat history
- hidden model-side assumptions
- loosely held context
- interfaces that blur system state with generated output

Addison exists to explore a different approach.

Instead of asking the model to *be* the system, Addison treats the model as one component inside a larger architecture.

The goal is to create a system that is easier to:

- restart
- inspect
- reason about
- govern
- carry forward across sessions without pretending continuity exists when it does not

---

## 3. Core Idea

The core idea behind Addison is simple:

> the system owns state; the model does not

That leads to a few architectural consequences:

- durable truth is kept in persistent artifacts
- context is assembled deterministically
- the daemon acts as the authority layer
- inference is applied to prepared context instead of serving as the continuity layer
- interfaces consume system truth rather than inventing it

This does not make the system simpler in every sense, but it does make the boundaries clearer.

---

## 4. How Addison Works

At a high level, the system works like this:

### 4.1 Persistent artifacts hold durable truth

Addison keeps continuity in artifacts rather than relying on remembered conversation alone.

These artifacts can represent things like:

- current system state
- decisions
- goals
- identity/voice scaffolds
- other continuity-bearing surfaces

### 4.2 The daemon manages system authority

A daemon-centered core reads, manages, and protects that state.

This layer is responsible for keeping the system’s continuity and boundaries coherent.

### 4.3 Context is built deterministically

Before inference happens, Addison prepares the context it wants the model to operate on.

That preparation is part of the system itself rather than something left to improvisation inside the model.

### 4.4 Inference operates on prepared context

The model is then used as a reasoning/output tool.

It receives prepared context, produces output, and returns control to the system.

### 4.5 Runtimes present and consume system state

Operator-facing runtimes connect to the daemon and interact with the system, but they do not replace the daemon as the source of truth.

---

## 5. What Makes It Different

Addison differs from many assistant-style systems in a few important ways.

### 5.1 Memory is externalized

Continuity is held in system artifacts rather than being treated as an implied property of the model.

### 5.2 The model is not the authority

Inference is useful, but it is not allowed to become the hidden source of memory, system state, or control.

### 5.3 Boundaries are explicit

The architecture is designed around clear roles:

- state
- context
- inference
- runtime interaction
- operator control

### 5.4 Restartability matters

Addison is designed to survive fresh sessions more honestly than systems that depend heavily on chat continuity alone.

---

## 6. Human-Governed by Design

Addison is not built around the idea that more hidden autonomy is automatically better.

Instead, it is built around explicit human-governed control.

That means meaningful system action is expected to remain inside visible boundaries rather than being quietly expanded through implication or convenience.

This is part of the system’s basic posture, not just a temporary UI choice.

---

## 7. Addison and WBTSR

Addison and WBTSR are related, but they are not the same thing.

- **Addison** is the system
- **WBTSR** is the workflow used to build and govern the work around it

WBTSR stands for:

- Work
- Build
- Truth
- Session
- Rehydrate

It is the human-governed method used to frame bounded work, separate building from auditing, preserve explicit truth surfaces, and maintain restart-safe continuity across sessions.

Addison is the built system.
WBTSR is the method used to build it.

---

## 8. What This Public Surface Does Not Claim

This public overview does not claim that Addison is:

- production-ready
- fully public
- fully exposed in source form
- an autonomous planner
- a hidden multi-model orchestration system
- a complete replacement for human judgment

It describes a real experimental system and its architectural posture.
It does not claim more than the public evidence supports.

---

## 9. Why This Matters

The value of Addison is not simply that it uses AI.

Its value is in the structure around that AI:

- where truth lives
- who owns continuity
- how state is preserved
- how boundaries are kept visible
- how intelligence is applied without becoming the hidden authority

That is the real system question Addison is trying to answer.

---

## 10. Working Summary

Addison is a local, daemon-backed state system that keeps continuity in persistent artifacts, builds context deterministically, and uses inference as a stateless tool rather than as the source of system truth.

It exists to explore a more inspectable, restartable, and human-governed way of building AI systems.
