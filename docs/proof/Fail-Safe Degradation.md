# Proof — Fail-Safe Degradation

## Claim Under Test

Addison remains functional and communicates honestly when optional layers are unavailable. The system degrades gracefully rather than crashing, hanging, or silently failing.

## Why This Matters

Fail-safe degradation is one of Addison's protected core invariants. The system is designed so that the daemon and its operator runtimes remain usable even when the inference layer, TTS, or presentation layers are unavailable.

This matters because a system that crashes or goes silent on infrastructure failure isn't trustworthy for real work. The operator should always know what happened and what state the system is in.

## Setup

- The Addison daemon was running locally.
- `addison-shell` (Electron/Vue) was connected as the active runtime.
- The operator sent a message during a session.
- The inference API request timed out — the language model was unreachable.

## Observations

The daemon log recorded:

- `LLM error: Request failed: The read operation timed out`

The shell did not crash, hang, or display a raw error trace. Instead, it displayed a clear operator-facing message:

- "I couldn't reach the language model right now. Check your API key and network."

The shell remained usable after the failure. The runtime did not enter an unrecoverable state.

The daemon also continued processing — expression labels (`calm`, `think`, `neutral`) were still being emitted and evaluated by the VTSBridge layer, even though the bridge was not authenticated at the time. Those expressions were logged and ignored cleanly rather than causing secondary failures.

## What This Supports

This supports the claim that Addison degrades gracefully when optional layers fail:

- An inference timeout did not crash the daemon or the runtime.
- The operator received an honest, readable error message instead of a stack trace or silent failure.
- The runtime remained functional after the error.
- Secondary subsystems (VTSBridge expression handling) also degraded cleanly — unauthenticated bridge state was logged and handled rather than causing cascading errors.

## What This Does Not Prove

- This does not prove that every possible failure mode is handled gracefully. It proves that one real infrastructure failure (inference timeout) was handled without crash or silent failure.
- This does not prove that the system recovers automatically — only that it degrades into an honest, usable state.
- This does not prove that extended or repeated failures would be handled identically.

## Public-Safe Evidence

- daemon log showing the LLM timeout error and continued VTSBridge expression handling
- shell screenshot showing the clean operator-facing error message
- no private artifact content, personal data, or sensitive information is visible in either the log or the shell output
