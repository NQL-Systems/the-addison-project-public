# Proof — Operator-Controlled Model Switching

## Claim Under Test

The Addison operator can switch the active inference model at runtime. Model switches are real — they result in actual inference calls to the requested model through the configured provider.

## Why This Matters

Addison's architecture treats the inference model as a replaceable utility. The daemon owns runtime truth about which model is active, and switches are operator-initiated through the CLI or other runtime surfaces. The system is not locked to a single model or provider.

If this claim holds, it means:

- the operator controls which model is doing the thinking
- model switches are real state changes, not cosmetic labels
- the system works across multiple providers without architectural change
- no hidden routing or automatic fallback is involved — the operator decides

## Setup

- The Addison daemon was running locally.
- Inference requests are routed through OpenRouter, which supports multiple upstream model providers.
- The operator switched models during normal use through the runtime model-switch surface.
- OpenRouter independently logs each request with the provider, model, timestamp, and requesting application.

## Observations

The OpenRouter activity log shows inference requests from the Addison application hitting three different models from three different providers on the same day:

- **Gemini 3.1 Pro Preview** (Google) — Mar 29, 06:55
- **Grok 4.1 Fast** (xAI) — Mar 29, 08:14
- **GPT-5.3 Chat** (OpenAI) — Mar 29, 09:39

All three requests are logged under the same application name ("Addison"), confirming they came from the same system through the same inference pipeline.

The sequence shows the operator switching across providers over a normal working session. The switches were not simulated or staged — they occurred during real use.

## What This Supports

This supports the claim that Addison's model switching is real and operator-controlled:

- Three different models from three different providers were used through the same system in a single session.
- OpenRouter's independent logging confirms the requests reached the declared models.
- The application identity ("Addison") is consistent across all three, confirming a single system rather than separate tools.
- The switches correspond to the Phase 18 operator-control semantics: the operator initiates, the daemon routes, and runtime truth reflects the active model.

## What This Does Not Prove

- This does not prove that model switching is seamless or that context is perfectly preserved across switches.
- This does not prove that every available model works equally well with Addison's context pack.
- This does not prove automatic fallback or intelligent model selection — the architecture explicitly does not claim those.
- This does not prove that the switch confirmation flow is fully hardened in every runtime surface.

## Public-Safe Evidence

- OpenRouter activity log screenshot showing three different models from three different providers, all under the Addison application name, with timestamps on the same day
- no API keys, token counts, cost data, or conversation content is visible in the log
- the evidence is from a third-party provider's independent logging, not from Addison's own self-reporting
