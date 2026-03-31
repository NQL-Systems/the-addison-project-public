# Public Proof — Operator-Controlled Model Switching

**Status:** Public proof artifact  
**Authority:** Public-safe observed behavior record

---

## Purpose

A core public claim of Addison is that the inference model is a replaceable utility rather than a hidden authority layer.

This document records a bounded proof of that claim. During live use, the operator switched Addison across multiple inference models, and an independent provider log showed requests from the same application reaching different models from different providers.

This matters because it supports the claim that model choice is operator-controlled and materially real, not just a cosmetic label inside the runtime.

---

## Claim Under Test

Addison can be directed by the operator to use different inference models, and those model changes result in real requests to the selected provider/model path.

---

## Why This Matters

Addison's architecture treats the model as a replaceable reasoning tool rather than the source of system continuity or authority.

If this claim holds, then:

- the operator controls which model is used
- model switches are real changes in the live inference path
- the system is not locked to one provider or one model family
- model identity is not merely presentation text inside the client

This reinforces the broader architecture claim that the daemon and artifact-backed system hold continuity, while the model remains interchangeable.

---

## Setup

- The Addison daemon was running locally.
- Inference traffic was routed through OpenRouter.
- The operator used Addison normally while changing the active model across live use.
- OpenRouter independently recorded requests with timestamp, provider/model, and application identity.

---

## Observations

The OpenRouter activity log shows requests from the **Addison** application reaching three different models from three different providers on the same day:

- **Gemini 3.1 Pro Preview** — Google
- **Grok 4.1 Fast** — xAI
- **GPT-5.3 Chat** — OpenAI

All three entries are associated with the same application name: **Addison**.

This shows that the live inference path was not fixed to one provider or one model. The system was used with multiple operator-selected models, and those requests were recorded by the external provider layer rather than only by Addison's own local reporting.

---

## What This Supports

This proof supports the claim that Addison's model switching is real and operator-controlled.

Specifically, it supports that:

- the same system can send inference requests through multiple model/provider paths
- those requests are externally visible in independent provider logs
- model switching is not only a UI label change inside Addison
- the model remains a replaceable utility within the system architecture

This is evidence for operator-controlled model switching in the bounded sense that model/provider changes can be initiated in live use and verified outside the local runtime.

---

## What This Does Not Prove

This proof is bounded.

It does **not** prove that:

- model switching is seamless in every runtime or session condition
- context is preserved perfectly across all switches
- every available model works equally well with Addison's context pack
- the switch-confirmation flow is fully hardened across every runtime surface
- automatic fallback, hidden routing, or autonomous model selection exist

It proves a narrower point:

**Addison can be used with different operator-selected models, and those selections result in real requests to different provider/model paths.**

---

## Public-Safe Evidence

This proof can be supported publicly without exposing private artifact contents or sensitive provider data.

Public-safe evidence includes:

- an OpenRouter activity-log screenshot
- visible provider/model entries across multiple requests
- the shared application identity (`Addison`)
- timestamps showing the requests occurred during the same day of live use

No API keys, token details, cost data, or conversation content need to be shown in order to support this proof.
