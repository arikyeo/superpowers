---
name: writing-plans
description: Use when turning a spec or requirements into a concise implementation or research plan, before execution
---

# Writing Plans

Plan from source evidence for the user's complete intended outcome. User instructions and explicit gates govern this skill.

For approved reversible projectless config/skill/app changes, execute directly. Skip plan/spec artifacts, tasks JSON, worktrees, commits, review packages, and execution-choice reapproval.

## Outcome and scope

Group related implementation, integration, documentation, and delivery into coherent outcomes sharing context and acceptance. Split only for independent ownership, a real dependency, a different safety boundary, or demonstrated context limits. File counts, small time slices, and individual test steps are not task boundaries. A literal cheap-model packet still needs exact edits and zero unresolved choices; do not force ordinary implementation into that format.

Read relevant source before planning. Reuse settled decisions and existing progress. Record only unknowns that affect the outcome. Resolve routine technical choices from evidence; ask once only for a material unresolved user choice or missing authority. Preserve explicit plan-only requests: deliver the plan without implementing.

## Context-sensitive interfaces

For context-dependent interfaces, inspect source defaults. Separate **Source default**/**Proposed change**; state omitted/explicit/invalid inputs and availability. Add mixed-context/idempotency acceptance and verifier owner/capability when relevant. Use fields only, no global matrix for trivial plans. Proposed/spec-only text is not acceptance evidence; later implementation supersedes it while standing permissions/limits remain.

## Plan format

Write scan-first Markdown with a title, one-sentence outcome and descriptive headings. Number complete outcomes; use short nested bullets for exact paths/symbols, concrete changes and observable acceptance. Put shared verification commands and expected results once under Verification. Include dependencies, relevant edge cases and explicit gates where they affect execution.

Compact implementation shape; omit unused fields, retain stable task IDs:

```markdown
# <Outcome> implementation plan

Goal: <observable result>
Scope: <in scope; explicit exclusions>

## Steps

1. <Complete outcome>
   - Path: `<file:symbol>`
   - Change: <specific behavior/interface>
   - Done: <observable acceptance>

## Verification

- `<command>` → <expected result>
```

For a research plan, use Question/decision, Scope and numbered investigations. Each investigation names the source/method, what it will establish and the stop criterion; do not invent findings or force code-edit fields. A research report leads with the answer, then findings paired with evidence links and implications, and consequential unknowns; separate observation from inference.

Use real tables only for comparable repeated fields (at most four short columns); use numbered sections when cells need paragraphs or code. Keep paragraphs to 1–3 short sentences, with blank lines around headings/lists. Avoid pipe-delimited pseudo-tables, empty headings, duplicated summaries and chronological research narration. Plans default to <=120 non-code lines; add detail only for evidence, safety or explicit user depth. Chat-summary caps do not truncate requested documents. Preserve meaning, commands and authority; literal code/diffs only when needed to remove ambiguity. No per-step commits or synthetic audit of the plan.

Track substantive work with available native tools after evidence. Keep 3–6 concrete steps and one in progress; if unavailable keep tracking internal. Use the existing progress file for long-work continuity. Do not create a second tracking system. Preserve existing task IDs, dependencies, gate metadata, and persistence when continuing an established workflow.

## Explicit user gates

A user gate requires an actual instruction to wait, obtain approval, meet a specified ordering condition, or demonstrate named evidence. Ordinary words such as check, verify, smoke test, or ensure do not create an approval gate. Do not label agent-invented precautions as user-ordered.

For an explicit gate, preserve its scope, required evidence, and exact invocation when supplied. Existing metadata uses `userGate`, `tags`, `verifyCommand`, `acceptanceCriteria`, and declared evidence axes. Put required gate metadata in the task description if the native API does not return metadata separately. Set `requiresUserSpecification` only when a consequential choice genuinely cannot be resolved from the user's request and evidence. Never downgrade a user-selected live verification to a paper check.

## Continue

When implementation is already authorized, proceed in the same task. Do not ask the user to select an execution method or approve each internal wave. Use subagents for independent work that saves time/context; reuse capable specialists. A requested plan review or explicit approval boundary remains binding. Do not add hooks, review packages, tests of plans, or a fresh session by default.
