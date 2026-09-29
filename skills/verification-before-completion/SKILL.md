---
name: verification-before-completion
description: Use when about to claim work is complete, fixed, or passing, before committing or creating PRs - requires running verification commands and confirming output before making any success claims; evidence before assertions always
---

# Verification Before Completion

Claims require evidence for the actual deliverable. User instructions and explicit gates govern this skill. When the user requires live-only proof, use the authorized real browser/API/production path before and after the mechanism fix; do not generate theoretical tests, test files, scripts, synthetic prompts, or forced-compaction trials. Static document gates still apply when configured.

## One verification pass

Before the final pass, identify the smallest sufficient checks and inspect relevant risks in the actual change.

Evidence starts from the affected real browser or API user flow on an authorized deployed target; otherwise use runnable local/staging, or already-recorded evidence. Do not claim browser/API evidence without observations, and do not treat an isolated green suite as proof of deployed behavior.

A fix needs an observed failure, a concrete reachable defect, or an explicit requirement; a failing automated reproduction is not a prerequisite when the real flow or source evidence demonstrates the defect.

Reuse existing green checks; do not default to speculative suites or synthetic harnesses. Add the smallest focused automated check only when demonstrated behavior needs durable protection, an explicit gate requires it, or a consequential invariant cannot be established by the live flow — name that gap, and the smallest substitute when live observation is unavailable. Reversible instruction/config edits do not require synthetic agent pressure tests.

A credible security, money or concurrency defect may still warrant a bounded investigation from a reachable path without a live exploit; missing live reproduction is not by itself an automatic deferral. Unsupported possible regressions and vulnerabilities stay out of the current fix; record an actual deferred finding in the project's existing KIV/backlog entry with hypothesis, evidence, impact and a concrete reopening condition — no speculative finding lists or empty docs.

Preflight required paths, installed runtime versions, and access before consuming the test budget. Invocation errors are not proof of a product failure. Correct routine in-scope invocation faults within the user's limits; do not create approval requirements from agent-invented retry counters.

After a phase or profile change, compare historical capability claims with current tool definitions, permissions and task scope. When the required operation is exposed and permitted, run the planned verifier within the existing budget. If the tool is absent or forbidden, cite that current evidence without probing or bypassing the restriction. Distinguish not attempted, denied and executed-but-failed. An unexecuted verifier needs its exact command, observed limitation or reason for omission, and the smallest authorized recovery owner/route; "primary acceptance required" alone is incomplete.

Read exit status and substantive output. A tool error, timeout, missing dependency, or partial result is not a pass. On an actual failure, make one focused diagnosis under the user's budget and name the remaining blocker/limitation. Do not broaden to unrelated tests or repeat unchanged failed attempts.

Current evidence stays valid for unchanged code/state within its demonstrated scope. Reuse it after handoff or compaction; a fresh message or new agent does not require another run. Recheck only a changed component or an explicitly requested live gate. Do not claim current live state from stale evidence.

Green freezes the verified component. Complete other already-authorized requirements without rerunning it. No adversarial pass, test-of-test, audit-of-audit, speculative hardening, or extra review after green. Do not report the whole outcome complete while required work remains.

## Configured quality gates

For a repository with quality.json, include this in the existing verification pass:

```sh
python3 "/Library/Application Support/AgentRules/cleat/cleat-manual.py" --config /absolute/repo/quality.json
```

Shared rule/skill edits use /Users/Shared/AgentRules/quality/quality.json. The adapter supports doc_size, doc_citations, escapes, and duplication; other sections fail explicitly. Silent exit 0 passes. Report the failing gate's actionable sites or timeout. No automatic baseline acceptance, ceiling increase, attach, hooks, or strict/postflight rerun. Details: /Users/Shared/AgentRules/quality/README.md.

## Evidence and limits

Match the claim to the observation: tests prove the exercised behavior; syntax proves parsing; a deployment needs its relevant live evidence. Inspect a worker's actual diff/result rather than trusting a DONE label. Choose one sufficient verification method rather than stacking reviews.

Separate proposed, edited, executed, deployed and observed outcomes. A relevant behavior-specific check establishes the behavior it exercises; it does not establish unrelated deployment or live integration, and a generic green suite or a worker's DONE label is not observed behavior. Claim 'fixed' only where relevant evidence establishes the affected behavior; 'configured' may be claimed from actual source or delivery evidence. Missing evidence narrows the claim and never expands verification, reopens accepted work or pauses authorized delivery.

Explicit user gates preserve their required command, fixture, acceptance criteria, ordering, and evidence axes. Do not replace them with a cheaper check. Complete unaffected work if a gate is blocked. Report the exact missing evidence and safest substitute without pretending the original check passed.
