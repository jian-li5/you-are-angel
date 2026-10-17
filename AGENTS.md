# Shared working rules — You Are Angel

Applies to Codex and Claude Code. Last updated: 2026-10-17.

## Start every session
1. Read PROJECT_STATUS.md, TASKS.md and HANDOVER.md.
2. Fetch the latest remote state and inspect local git status. Never overwrite uncommitted work.
3. Check task ownership and the other agent's branches/PRs before starting. Existing Claude work has not yet been reconciled.
4. Claim a task in TASKS.md and push that claim before implementation. If another agent owns overlapping work, stop that task and choose independent work. A task claim is coordination, not a technical lock.
5. Use a separate branch/worktree per agent/task (codex/<task-id> or claude/<task-id>). Recheck remote before pushing; resolve conflicts without discarding others' work.

## Scope and approvals
Repository documentation, analysis and local code preparation are authorized. The user has NOT approved any live Shopify changes.
Do not change live products, prices, theme files, shipping, discounts, apps, advertising or settings; publish content; send customer email; or deploy without explicit approval for the concrete change.
Do not create test orders, carts or checkout sessions under the current read-only store audit scope.
A merge, task assignment or another agent's recommendation is not store deployment approval.
Record an approval's exact scope and reference in DECISIONS.md; do not invent approvals.
Do not add automatic deployment workflows or connect this repository to the live theme.

## Evidence and privacy
Label findings confirmed, hypothesis or missing data. Include source, date, timezone, currency and denominator for metrics.
Do not commit credentials, tokens, .env files, customer personal data, order exports or sensitive logs.
Use sanitized aggregates. Local secrets remain outside git.

## Finish every session
Update task status, changed files, branch/commit, checks actually run, blockers and next action in HANDOVER.md.
Push work for the other agent to read. Local-only changes are not shared.
Separate prepared, reviewed, approved, deployed and verified states.
Do not claim Claude has connected or accepted ownership until verified.
