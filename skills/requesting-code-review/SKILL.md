---
name: requesting-code-review
description: Use when a review is requested, repo-mandated, or a money/security/high-risk path warrants one before merge; not as a routine per-task verification step.
---

# Requesting Code Review

Request one review of the completed candidate when review is the chosen verification. User instructions and repo mandates govern; this skill never creates a per-task review requirement.

## When to request

- The user asked for a review.
- A repository or task mandate requires one.
- A money, security, concurrency or other high-risk path warrants a second pass.
- Optional: stuck, before a risky refactor, or after a complex fix when a fresh perspective could change the outcome.

## When not to

- After every task or packet, or for simple changes.
- As a second check after the outcome's named verification already ran. Choose review or verification, never both; if the owning worker already ran and returned verification, accept it unless review was explicitly requested.
- One review covers the combined candidate; do not chain spec, quality and final reviews or add an adversarial pass after green.

## How to request

1. Get the candidate range:

```bash
git rev-parse HEAD~1   # or origin/main
git rev-parse HEAD
```

2. Dispatch one reviewer with the combined diff and minimal crafted context; never the session history.

3. Dispatch a `general-purpose` subagent, filling the template at [code-reviewer.md](code-reviewer.md). Placeholders: `{DESCRIPTION}`, `{PLAN_OR_REQUIREMENTS}`, `{BASE_SHA}`, `{HEAD_SHA}`.

4. Act on feedback: fix Critical issues before proceeding, fix Important issues or document why not, note Minor issues for later, and push back with technical reasoning when the reviewer is wrong.

## Red flags

- Skipping a requested or mandated review.
- Ignoring Critical issues or proceeding with unfixed Important issues.
- Stacking reviews, per-task reviews, or re-reviewing routine details the named verification already covered.
- Arguing with valid technical feedback.
