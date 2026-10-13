# GitHub Execute

Turn an agreed outcome into bounded, verified work without making the user supervise routine execution.

## Entry

Start from an execution-ready ticket or a user request that already establishes the intended outcome. Surface missing product, strategy, taste, cost, safety, ownership, or irreversible decisions through the coordinator when present, otherwise to the user; do not invent the answer. Ask the user to select or define the intended outcome when it is unselected or needs redefining. Findings and product choices that preserve that outcome stay in the current execution workflow; continue independent work while decisions are pending.

### Identify the execution relationship

Default to direct execution for the user. A coordinator is present only when the assignment or explicit native parent context identifies that relationship and a usable reporting route. Do not infer one from GitHub comments, labels, branch names, chat titles, or presumed shared history, and do not search unrelated chats for one.

For delegated work, establish the coordinator identity, reporting route, assignment boundary, source/base and permissions from the assignment. Request missing reporting details through the current channel while continuing independent work; messaging another chat still requires authorization.

GitHub checkpoints apply to both direct and coordinated execution when issue updates are authorized. The direct worker records progress and raises material decisions in its current user chat; the coordinated worker also reports to its identified coordinator.

## Execution Loop

### 1. Orient

- Read the repository README, relevant instructions, ticket and its recorded decisions, and current assignment. Recover the agreed requirements from these sources rather than assuming an earlier session is available.
- Inspect the current state before deciding what must change.
- Prefer the smallest complete solution that satisfies the intended outcome.

#### Choose a safe checkout before editing

- Confirm the intended repository, checkout path, branch/base, dirty changes, and relevant concurrent work. Inspect local worktrees and attached artifacts when available; do not infer ownership from a branch name or scan unrelated chats.
- Reuse a suitable task checkout. A solo task in a safe checkout needs no additional worktree. Concurrent writing assignments use separate worktrees and task branches; sequence changes that depend on unfinished work. Isolation prevents mixed edits, not semantic integration conflicts.
- When another checkout is necessary, use the host's managed worktree tools when available in the host's managed worktree location, not feature folders beside canonical repositories. Resolve the dependency base explicitly: the tool defaults to the remote default branch and does not copy uncommitted changes. Use the returned absolute path for every worker command; creating a worktree does not move the chat. When managed tools are unavailable, follow the repository's checkout rules and sequence writers in a safe checkout.
- Preserve unrelated changes. Commit or push only task-owned work when the request or established workflow authorizes it. Coordinate contested simulators, devices, ports, or other shared resources with the execution owner; separate worktrees do not isolate these resources.

### 2. Establish the outcome

Establish the intended outcome, necessary scope, completion evidence and decisions requiring the user. Keep this in context unless a written artifact is required. State the boundary when helpful, then proceed without routine approval. Create additional artifacts or task branches only when the request, repository workflow or checkout safety requires them.

### 3. Execute autonomously

- Choose and adapt the technical approach using the available code, evidence and expertise. Own reversible decisions and steps needed to deliver the agreed outcome.
- Defer optional cleanup, polish, abstractions, and follow-on ideas.
- When a material user decision is missing, pause dependent work and raise it through the coordinator or current user chat. Continue independent work.

#### Record verified progress and keep going

When GitHub updates are authorized, add one compact comment to the owning issue after a meaningful observable behavior or acceptance criterion is implemented and verified. Group related small changes; do not comment for every edit, test run, or turn.

Record what works, the source (commit/PR, or checkout/branch and explicit uncommitted status), relevant verification and the source/build it covers, remaining requirements, and the next action. Distinguish an installed build from the source verified. For integration, supply task-owned commits or an inspectable task-owned diff consistent with the agreed delivery workflow; a progress comment alone is insufficient. Preserve unrelated work. Record material deviations and blockers when they affect execution.

A verified increment is a checkpoint. Continue until the whole assignment is accounted for; issue acceptance also requires its agreed integration and delivery conditions. Report blocked requirements as unfinished.

When working under a coordinator, also send it a compact update at a verified checkpoint, dependency/blocker, or assignment completion. Include the source/evidence, issue/comment reference, and what happens next; the GitHub comment alone does not notify the parent agent. If later changes invalidate evidence, identify what must be rechecked instead of leaving the earlier checkpoint as proof of the new source.

### 4. Prove completion

Run or reuse the repository-required gate or the smallest relevant verification for the affected surface. Accept valid evidence covering the final candidate; run only missing or invalidated checks.

Before reporting assignment completion:

- Inspect the actual result and changed-file scope against the agreed outcome, scope and completion conditions.
- Confirm every completion condition has evidence and no material in-scope work remains. Fix gaps and rerun only the verification those changes invalidate.
- Keep relevant technical documentation current and explain necessary deviations from the boundary.

If a genuine external blocker remains, finish useful independent work, then report the unfinished conditions and resumable source without claiming completion.

### 5. Hand off precisely

In direct execution, use [GitHub Review](github-review.md) before final handoff when implemented work needs human review or authorized GitHub review bookkeeping. Reuse completed verification; do not add a mandatory test or independent review pass. Delegated workers keep reporting checkpoints to their coordinator, which owns the final integrated review and bookkeeping. Corrections within an active review return to that review instead of invoking another handoff review.

Lead with the achieved outcome, verification evidence, meaningful decisions or deviations, and any real remaining risk or external action.

Use precise states such as implemented locally, validated, committed, pushed, merged, or deployed. Never call an earlier state complete when the requested outcome requires a later one.

## Keep It Lean

This skill executes work. It is not another planning system. Do not add ceremony, persistent artifacts, repeated check-ins, or approval gates merely to demonstrate process.
