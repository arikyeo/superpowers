---
name: verification-before-completion
description: Use before claiming work complete, fixed, or passing, or before commit/PR - requires running verification commands, confirming output, before any success claim; evidence before assertions, always
---

# Verification Before Completion

## Overview

**Core principle:** Evidence before claims, always.

**Violating the letter of this rule is violating the spirit of this rule.**

## The Iron Law

```
NO COMPLETION CLAIMS WITHOUT VERIFICATION EVIDENCE
```

A claim needs evidence for the actual deliverable. Prefer the affected real browser/API flow on an authorized deployed target, otherwise runnable local/staging. An isolated green suite does not establish deployed behavior. Reuse valid recorded evidence for unchanged code/state within its demonstrated scope; a fresh run is required only for changed components, a live gate the user requested, or a claim whose evidence is stale or out of scope. A failing automated reproduction is not a prerequisite for fixing a defect demonstrated by the real flow or supported by source evidence.

## The Gate Function

```
BEFORE claiming any status or expressing satisfaction:

1. IDENTIFY: What check proves this claim on the real flow?
2. RUN (or cite valid evidence): Execute the check, or reuse a valid recorded result for unchanged code/state within its scope
3. READ: Full output, check exit code, count failures
4. VERIFY: Does output confirm the claim?
   - If NO: State actual status with evidence
   - If YES: State claim WITH evidence
5. ONLY THEN: Make the claim

Skipping the evidence step is the failure; a valid existing observation counts as evidence.
```

## Common Failures

| Claim | Requires | Not Sufficient |
|-------|----------|----------------|
| Tests pass | Test command output: 0 failures | Stale or out-of-scope result, "should pass" |
| Linter clean | Linter output: 0 errors | Partial check, extrapolation |
| Build succeeds | Build command: exit 0 | Linter passing, logs look good |
| Bug fixed | Original symptom observed resolved on the real flow or check | Code changed, assumed fixed |
| Regression test works | Seen failing on the old behavior, or an observed failure cited | Test passes once with no failure evidence |
| Agent completed | VCS diff shows changes | Agent reports "success" |
| Requirements met | Line-by-line checklist | Tests passing |

## Red Flags - STOP

- Using "should", "probably", "seems to"
- Expressing satisfaction before verification ("Great!", "Perfect!", "Done!", etc.)
- About to commit/push/PR without verification
- Trusting agent success reports
- Relying on partial verification
- Thinking "just this once"
- Tired and wanting work over
- **ANY wording implying success without valid evidence for the claim**

## Rationalization Prevention

| Excuse | Reality |
|--------|---------|
| "Should work now" | RUN the verification |
| "I'm confident" | Confidence ≠ evidence |
| "Just this once" | No exceptions |
| "Linter passed" | Linter ≠ compiler |
| "Agent said success" | Verify independently |
| "I'm tired" | Exhaustion ≠ excuse |
| "Partial check is enough" | Partial proves nothing |
| "Different words so rule doesn't apply" | Spirit over letter |

## Key Patterns

**Tests:**
```
✅ [Run test command] [See: 34/34 pass] "All tests pass"
❌ "Should pass now" / "Looks correct"
```

**Regression tests (Red-Green):**
```
✅ Watch the check fail on the old behavior (or cite the failure already observed), then see it pass with the fix
❌ "I've written a regression test" (never seen to fail, and no other evidence of the defect)
```

**Build:**
```
✅ [Run build] [See: exit 0] "Build passes"
❌ "Linter passed" (linter doesn't check compilation)
```

**Requirements:**
```
✅ Re-read plan → Create checklist → Verify each → Report gaps or completion
❌ "Tests pass, phase complete"
```

**Agent delegation:**
```
✅ Agent reports success → Check VCS diff → Verify changes → Report actual state
❌ Trust agent report
```

## When To Apply

**ALWAYS before:**
- ANY variation of success/completion claims
- ANY expression of satisfaction
- ANY positive statement about work state
- Committing, PR creation, task completion
- Moving to next task
- Delegating to agents

**Rule applies to:**
- Exact phrases
- Paraphrases and synonyms
- Implications of success
- ANY communication suggesting completion/correctness

## Scope and deferred findings

Unsupported possible regressions and vulnerabilities stay outside the current fix. Record an actual deferred finding in the project's existing KIV/backlog entry — hypothesis, available evidence, possible impact and a concrete reopening condition — instead of hunting for speculative findings or creating empty docs. A credible security, money or concurrency defect may still warrant a bounded investigation from a reachable path without a live exploit; missing live reproduction is not by itself an automatic deferral.

One verification pass, and no adversarial pass, test-of-test or audit-of-audit after green. Read the change and its evidence once against the claim; findings the reader needs go in as facts, process narration does not. When description and reality disagree, reality wins and the gap is itself a finding, reported in one line.

## Live State Beats Description

Verification runs against the LIVE system, not its description. Sources rank by how they lie:

| The claim comes from | Treat it as | Verify by |
|---|---|---|
| A README, doc, or wiki | Stale by default | Run the code path, read the actual source |
| A code comment | The code's opinion of itself | Read the code the comment describes |
| A config file in the repo | What was INTENDED | Query the running system for the EFFECTIVE value |
| Your memory or an earlier session | A point-in-time observation | Re-check now — the system moved since |
| The user's description | Honest but possibly outdated | Confirm with a read-only probe |
| A schema or type definition | Better, but migrations lie | Inspect actual data or live schema when it matters |

Pick the **cheapest sufficient check**: if the authoritative artifact is already in front of you, the check IS reading it — probe (run it, query it, curl it) only when the truth is not in view or behavior could differ from the text. When description and reality disagree, reality wins AND the gap itself is a finding — report it in one line ("README says X, code does Y"). Timestamp what you learn: "as of this check, X" ages honestly; "X is true" rots silently.
