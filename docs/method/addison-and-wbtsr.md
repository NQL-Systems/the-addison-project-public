# Artifact-Gated Startup

**Status:** Public proof artifact
**Authority:** Public-safe observed behavior record

---

## Purpose

A reasonable question about any system like Addison is: how do we know this is more than a themed assistant with extra files around it?

This document records an early proof point that addresses that question. During local runtime testing, startup behavior depended on the artifact layer being present, and once startup was unblocked, the live system answered from newly instantiated local artifacts rather than falling back to generic model behavior.

This mattered because it turned the artifact model from a design claim into observed runtime behavior.

---

## What "Artifact-Gated Startup" Means

Artifact-gated startup means the system's path into usable runtime operation depended on required artifact surfaces being present.

In practice, Addison did not behave like a loose prompt wrapper that could simply improvise around missing structure. The artifact layer had to exist in order for the system to come up cleanly and operate against the intended local grounding layer.

That made the artifact boundary functionally meaningful rather than decorative.

---

## What Was Observed

During local daemon bring-up, missing artifacts had to be created before startup could complete correctly.

After startup was unblocked, the CLI was used to ask grounded questions about current system state, held decisions, and active goals. These questions were chosen because they should map directly to newly created local artifacts under the private brain structure.

The runtime answers reflected those artifacts rather than falling back to vague assistant summary. In particular, the responses correctly reflected the current slowdown/readiness posture, held decisions such as Addison being more than a model wrapper and canonical memory living under `brain/`, and active goals focused on making shared memory artifacts real and truthful before pushing further runtime expansion.

This showed that the new artifact layer was participating in live answers.

---

## What This Proved

**The daemon could boot against the local artifact layer.** Startup was not fully clean until the needed artifact surface existed.

**The CLI could reach the daemon and receive grounded replies.** The runtime was not only booting — it was answerable through the CLI in a live way.

**Newly instantiated private artifacts were being read in practice.** The system answered from current local artifacts covering state, decisions, and goals rather than relying on stale abstraction or generic response behavior.

**The artifact layer was operational, not cosmetic.** The artifact model had crossed into real runtime effect.

---

## What Was Only Partially Aligned

The content grounding worked better than the final response voice.

The answers were correct, but the runtime still wrapped them in a more report-like interpreter style than the intended Addison voice — phrasing like "Based on the artifact..." or "According to the record..." suggested that the grounding layer was working more cleanly than the final response-layer voice.

That distinction matters because grounded answers do not automatically mean full voice alignment. Voice alignment is treated as a separate, bounded future investigation.

---

## Scope and Limits

This proof point is meaningful, but it should stay bounded. It did not prove that the full architecture is complete, that every subsystem is validated, that the response layer is fully aligned, or that the system is production-ready.

It proved a narrower and stronger point: Addison's runtime depended on real artifact grounding, and once startup was unblocked, the live system answered from newly instantiated local artifacts in practice.

---

## Public Boundary Note

This document describes the behavior without publishing the private artifact contents themselves. Public proof does not require dumping private system state — it requires making the observed behavior legible and defensible.
