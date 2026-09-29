---
name: brainstorming
description: "You MUST use this before any creative work - creating features, building components, adding functionality, or modifying behavior. Explores user intent, requirements and design before implementation."
---

# Brainstorming Ideas Into Designs

Understand the intended outcome before choosing an implementation. User instructions and explicit gates govern this skill.

## Use existing intent

Read relevant source and established decisions. Treat a clear request to build, fix, apply, or complete as authorization for normal reversible work within that scope. A supplied design, accepted recommendation, or sufficiently concrete request does not need another design approval.

For approved reversible projectless config/skill/app changes, proceed directly. Skip design/spec artifacts, tasks JSON, worktrees, commits, review packages, and execution-choice reapproval.

If the user asks only for brainstorming, options, or a plan, provide that output without implementation. If an essential unresolved choice materially changes the outcome, explain the concrete tradeoff and ask once. Otherwise choose the simplest compatible approach and continue. Do not ask routine technical questions that source inspection or existing decisions answer.

## Keep the outcome together

Identify scope, success criteria, ownership, relevant interfaces, and real risks. Group related requirements into complete deliveries. Split only for independent ownership, dependencies, safety boundaries, or demonstrated context limits; internal steps are not approval checkpoints.

Explore alternatives that change the decision. Preserve existing patterns and unrelated work. Get approval before investigating or fixing adjacent issues; evidenced necessary dependencies under existing authority may proceed. Exclude neighboring refactors, speculative hardening and extra features.

## Context-sensitive interfaces

For context-dependent interfaces, inspect source. Separate **Source default** and **Proposed change**; state omitted/explicit/invalid inputs and availability. Add mixed-context/idempotency acceptance and verifier owner/capability when relevant. Use needed fields only, no global matrix for trivial specs. A proposal is not acceptance evidence; later implementation supersedes spec-only scope while standing permissions/limits remain.

## Record and proceed

When a durable spec is needed, use a title, one-sentence goal and short sections: Scope/non-goals, numbered testable Requirements, relevant Decisions/interfaces, and Acceptance. State behavior and constraints concretely. Use bullets for distinct facts and a compact table only for genuine comparisons; no long narrative paragraphs or dense pseudo-tables.

Research output leads with the answer/recommendation, then findings with evidence links and implications; distinguish observed facts, inference and consequential unknowns. Research plans name the decision, sources/methods and stop criteria. Do not invent evidence or retell search history.

Keep each fact once, paragraphs to 1–3 short sentences and supporting detail linked on demand. Preserve exact literals, safety and meaningful uncertainty. Chat-summary caps do not truncate requested specs/research. Reuse existing progress and native tracking; no duplicate metadata or separate checklist for every brainstorming step.

A requested design review is one gate. After approval, execute the approved work in the same task without a second written-spec review or execution-method menu. Scope-expanding, destructive, costly, irreversible, or production-facing actions still need authority when not already authorized.

Choose proportionate verification of the actual result before implementation; no synthetic audit of the design or test-of-test loop. For multi-step implementation use writing-plans or subagent-driven-development only where they help, without repeating approvals.

## Visual decisions

Offer the visual companion only when a real visual choice benefits from it and no suitable native artifact suffices. If accepted, read visual-companion.md before use. Never start its server, add a watcher, or open tools merely because brainstorming began; follow the user's runtime restrictions.
