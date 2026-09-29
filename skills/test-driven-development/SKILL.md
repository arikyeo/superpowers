---
name: test-driven-development
description: Use when a focused runnable automated check is necessary for behavior the browser cannot establish
---

# Behavior-First Verification

For user-facing behavior, exercise the real running app in a browser first: use an authorized deployed target when available, otherwise runnable local/staging. Record actual observations; a browser pass is never inferred.

Reuse existing green checks. Do not default to writing speculative/unit suites or synthetic harnesses. A user live-only rule forbids generated tests, test scripts, synthetic prompts, and forced-compaction trials; use the authorized real path or name the exact unverified behavior. Otherwise add a focused runnable check only when browser evidence cannot establish a consequential hidden financial/concurrency invariant, an explicit gate requires it, the browser/app is unavailable, or the work is non-UI. State the exact gap and smallest substitute.

Keep production authority, QA cleanup, and secrets intact. One verification pass applies; green freezes the verified component. Do not add suites or rerun unchanged checks after green.

When a focused check is needed, exercise real behavior and report its command, result, and limit. It complements browser evidence; it does not replace a feasible browser exercise.
