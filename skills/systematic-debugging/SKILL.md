---
name: systematic-debugging
description: Use for bugs, failing checks, unexpected behavior, performance regressions, drift after a steering correction, or a task resumed after compaction, before proposing fixes
---

# Systematic Debugging

Find the actual cause before changing code, and keep the fix inside the user's existing authority and verification budget.

Provider safety-classifier refusals are not code defects: if an otherwise legitimate request is refused, follow the refusal clause in `/Users/Shared/AgentRules/shared/refs/waiting-and-delegation.md` instead of this flow.

Cheaper models (e.g. Luna, Haiku or Sonnet) and models needing clearer steps: apply the conditional scaffold in `/Users/Shared/AgentRules/shared/refs/subagent-output.md`, then use the diagnostic flow below.

## Flow

1. **Confirm the symptom on the affected flow.** Start with the affected real browser or API user flow on an authorized deployed target; otherwise use runnable local/staging or evidence already recorded. Capture the failing command or request and its output, the affected caller and data path, and the environment and version. Keep standing production restrictions (no generic suites or destructive, schema, concurrency and purge checks on production; read-only or expressly authorized seed-QA actions only) and do not create a new approval for already authorized safe work. Separate observation from inference; a reported cause is a hypothesis, not a finding — if a source or baseline it alleges is absent, say so without inventing evidence, while authorized creation still happens. Confirm the symptom is the one reported rather than a neighbour.
2. **Use the smallest existing surface.** Prefer an existing test, script, log, trace, or a single command that exercises the exact path. A fix needs an observed failure, a concrete reachable defect, or an explicit requirement; a failing automated reproduction is not a prerequisite for a defect demonstrated by the real flow or supported by source evidence. A user live-only rule prohibits generated tests, test scripts, synthetic prompts, and forced-compaction trials; exercise the authorized real path or name the exact gap. Do not build diagnostic infrastructure or instrument unrelated components to satisfy a ritual. When a boundary is genuinely opaque, inspect its inputs and outputs with the tools already at hand. When a real debugger backend is available, observe live state with breakpoints (conditional or invariant) instead of adding print statements, and trace where a wrong value first appears up the call stack. Tag temporary probes and remove them before reporting.
3. **Compare with working behavior.** Find the closest working case — the same path before a change, a sibling component, the reference implementation — and name the concrete difference. Check recent changes to that path. Trace only the duplicate producers/consumers of the touched behavior that bear on the hypothesis; an intentional copy is not a defect by itself.
4. **State one falsifiable hypothesis** in a sentence: "X causes the failure because Y; if X is changed or removed, the symptom disappears while Z stays constant." Name the observation that would disprove it.
5. **Change one supported cause.** Make the smallest edit that addresses the hypothesis. Keep unrelated improvements out of the diff. If the hypothesis fails, revise it from the new evidence; do not stack fixes. Surface a silent fallback only when it explains the observed symptom.
6. **Verify the affected flow within the existing budget.** Exercise the affected real browser or API flow again — or the command that demonstrated the failure — plus any check the user's own rules require. An isolated green suite does not establish deployed behavior. Add the smallest focused automated check only when demonstrated behavior needs durable protection, an explicit gate requires it, or a consequential invariant cannot be established by the live flow; name that gap. Reuse valid observed failures and green evidence: do not replay a known failure, and do not start repeated test loops, full suites or new infrastructure unless the task's rules require it. Green ends checking, not authorized integration or delivery.
7. **Report** the cause, the fix, the evidence, and what remains unknown. If no cause can be established, say so with the evidence gathered instead of presenting a guess as a fix.

Re-steering after a correction means reconciling the actual symptom, the current authority, and the evidence with the next action. Do not replay work that is already complete.

Unsupported possible regressions and vulnerabilities stay outside the current fix. Record an actual deferred finding in the project's existing KIV/backlog — one concise entry, or a single doc only when none exists — with hypothesis, evidence, impact and a concrete reopening condition; no speculative findings list or empty docs. A credible security, money or concurrency defect may still warrant a bounded investigation from a reachable path without a live exploit; missing live reproduction is not by itself an automatic deferral.

## Root-cause tracing

When the failure appears deep in a call stack, work backwards: where does the bad value originate, what passed it in, and what does the source tolerate. `root-cause-tracing.md` has the full technique. `defense-in-depth.md` covers validation layers after the cause is known; `condition-based-waiting.md` replaces arbitrary sleeps with condition polling.

## Performance

When the problem is slowness, memory, throughput, or a claimed speedup, read `performance-profiling.md` before changing code: measure a comparable baseline, profile on the axis that matches the metric, and confirm the hotspot before optimizing. Do not profile production or add benchmark frameworks without authorization.

## Safety

- Never print, log or commit secret values, environment dumps or keychain contents to diagnose anything. Presence checks must return booleans, never values; keep diagnostic output out of shared logs.
- Destructive, irreversible, costly, or production-facing actions need the user's existing authorization. Diagnosis that does not require them continues; a required production restart, rollback, or data change is a gate.
- Preserve the user's uncommitted work. Do not revert, reset, or clean their tree to make a check pass.
- Report only what the evidence supports. "Fixed" means the affected behavior is observed resolved on the real flow, or the relevant check now passes; otherwise name the gap.

## When to stop

Stop when the cause is established and the fix verified within budget, when the user's verification limits are reached, or when the next diagnostic step needs authority you do not have. Report what was established, what was ruled out, and the next action. Complete any remaining authorized integration and delivery.
