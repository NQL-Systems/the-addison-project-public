# Proof — Runtime Agnosticism

## Claim Under Test

The Addison daemon serves multiple runtimes built on different technology stacks through standard protocols, without requiring changes to the core system. Runtimes are interchangeable operator surfaces over the same authoritative daemon.

## Why This Matters

Runtime agnosticism is one of Addison's architectural northstars. It means the "mind" (daemon/core) remains stable regardless of the "body" (CLI, TUI, shell). If this claim holds, it means:

- the operator can switch runtimes without losing session truth
- the daemon does not depend on any particular frontend to function
- multiple runtimes can observe the same session simultaneously
- no runtime holds authority over system truth — the daemon does

## Setup

- The Addison daemon was running locally.
- `addison-cli` (Python + prompt_toolkit + websockets) was connected to the daemon.
- `addison-shell` (Electron + Vue) was connected to the same daemon simultaneously.
- A fresh session had just been started, with the prior session archived locally by the CLI.
- Both runtimes were connected to the same session ID (`e92350a8`).

## Procedure

1. The operator triggered a session reset through the CLI.
2. The CLI confirmed the prior session was archived and a fresh session started.
3. The operator sent one message through the CLI: "testing session restarts."
4. Both the CLI and the shell received and displayed the daemon's response.

## Observations

Both runtimes displayed the same grounded response from the daemon:

- "I am here, and the thread is intact."
- A reference to boundaries settled in Phase 34 and the CLI holding archive truth.

The CLI rendered this in its managed terminal transcript surface. The shell rendered the same content in its Electron/Vue chat interface with the Addison avatar.

Both runtimes showed the same session identity. Both received the same daemon-authored response. Neither runtime generated the response independently — it came from the daemon through the ShellBridge WebSocket protocol.

The shell's status area displayed "RUNTIME DIVERGED," which is honest self-reporting that its own local state differs from the daemon's current posture. This is consistent with the architectural claim that adapters report their own status truthfully rather than silently masking divergence.

## What This Supports

This supports the claim that the Addison daemon is runtime-agnostic:

- Two runtimes built on entirely different technology stacks (Python terminal vs Electron/Vue) connected to the same daemon simultaneously.
- Both received and displayed the same daemon-authored response from the same session.
- The daemon did not need to know or care which runtimes were connected.
- Adapter-level status reporting (the shell's "RUNTIME DIVERGED" indicator) showed honest local posture rather than false synchronization.

## What This Does Not Prove

- This does not prove that all runtimes are equally mature or feature-complete. The CLI is the current primary runtime; the shell is active but limited.
- This does not prove that runtime switching is seamless in all scenarios — only that simultaneous connection and response delivery works.
- This does not prove that session state transfers perfectly across all runtime transitions, reconnections, or daemon restarts.
- This does not prove that the TUI runtime (`addison-tui`) behaves identically, though it connects through the same ShellBridge protocol.

## Public-Safe Evidence

- screenshot showing both the CLI and the shell displaying the same session, same operator message, and same daemon response side by side
- visible session ID match across both runtimes
- visible shell status reporting ("RUNTIME DIVERGED") demonstrating honest adapter-level posture
- no private artifact content, personal data, or sensitive information is visible in either runtime's display
