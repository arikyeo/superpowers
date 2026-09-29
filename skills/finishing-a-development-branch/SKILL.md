---
name: finishing-a-development-branch
description: Use when completing development work and delivering or preserving its branch under the user's integration instructions
---

# Finishing a Development Branch

Finish the authorized delivery in this task. Reuse the user's explicit integration target and prior decisions; do not turn a settled choice into a menu.

## Confirm the candidate

1. Identify the checkout, branch or detached state, base, remote, and worktree owner from the repository, task record, and conversation. Use source facts, not a `.worktrees` pathname.
2. Reuse existing green evidence when the candidate is unchanged. Run one proportionate final verification, including configured gates, only when it is needed for the actual delivery.
3. Do not automatically rerun a full suite, create an audit, or test a prior verification. For a real failure, diagnose the affected scope within hard user limits; do not silently bypass it.

Useful identity commands when the source does not already establish it:

```bash
git rev-parse --show-toplevel
git branch --show-current
git remote
git worktree list --porcelain
```

## Resolve only material unknowns

Use an approved base branch, remote, merge target, PR target, or deployment target as given. If an essential identity or delivery choice remains unknown, ask once with the concrete candidates and impact. Do not infer push, PR, merge, deployment, deletion, or discard authority from completed work.

If the user requested code only, preserve the checkout and deliver the code and evidence without asking for an integration choice.

## Deliver the authorized outcome

- For an authorized local merge, resolve the recorded base and merge target, then complete the merge. Do not change the target without authority.
- For an authorized push or PR, use the approved remote and target. A rejected push requires focused investigation; never force-push without explicit authority.
- For an authorized deployment, follow the approved target and existing release safeguards. Completion alone does not authorize it.
- For an authorized keep-as-is outcome, report the branch and checkout path; preserve both.

Do not archive this task or create a replacement task as part of delivery.

## Deletion and worktree cleanup

For cleanup already included in the approved integration workflow, prove the work is merged and ownership is recorded; remove only the authorized merged branch or owned worktree. Otherwise preserve it without demanding a cleanup decision.

Discarding unmerged work is separate: require an explicit discard request, state the exact branch, worktree path and commits affected, then obtain the typed confirmation `discard`.

```text
This will permanently delete:
- Branch: <branch>
- Commits: <commit-list>
- Worktree: <path>

Type `discard` to confirm.
```

For either cleanup path, remove only a worktree whose creation and ownership are proven by the current task's recorded provenance. Never automatically remove host-managed, current, active-writer or other-task worktrees. A `.worktrees` or `worktrees` pathname alone does not prove ownership. If ownership is unknown, preserve the worktree and finish unaffected delivery.

When removal is authorized and proven, run it from outside the target worktree:

```bash
git worktree remove <path>
git branch -d <merged-branch>
# Only for explicitly confirmed discard of unmerged work:
# git branch -D <discard-branch>
```

Never use deletion or force push as a recovery shortcut.

## Final status

Use the user's compact final status table for multi-step or multi-item delivery: `Work item | Status | Why / evidence | Next`. Include unfinished authorized items with their concrete blocker and next action; state `Remaining: none` only when none remain. Keep a single-step, single-item final concise, with the delivered result, evidence, and any user action still required.
