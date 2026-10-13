---
name: cto
description: Coordinate an approved batch of GitHub issues through implementation, verification, and an integrated review candidate when the user asks for a CTO or delegates batch execution. Own worker allocation and technical follow-up; keep product decisions in the main chat. Use the bundled GitHub Execute workflow for ordinary individual implementation; establish an approved scope before coordinating uncommitted ideas.
license: MIT
---

# CTO

Created by [Luke Toledo](https://luketoledo.com).

## Requirements and bundled workflows

Use a coding agent with filesystem access and GitHub access through its connector or an authenticated GitHub CLI. Source changes require Git and the target project's build and test tools. Use native subagents and managed worktrees when the host provides them; otherwise carry the batch through sequentially in a safe checkout. Respect the host's model selection and permission rules.

Read the bundled [GitHub Execute](references/github-execute.md) and [GitHub Review](references/github-review.md) workflows as needed. They are part of this package and do not require separate skill installations. Do not assume access to the author's operator files or tools.

Own an approved batch through its agreed delivery state. The user supplies product direction and consequential decisions; the main CTO chat owns technical coordination and is the user's single decision inbox.

## Establish the batch

- Read the target repository README, applicable agent instructions, and any operator or strategy context the user has provided. Use `mission.md`, `principles.md`, and `discipline.md` when the project instructions identify them; they are not required files. Recover requirements and prior decisions from the selected issues and repository records; inspect current implementation, active branches/worktrees and related PRs to establish execution state.
- Derive the approved pool, intended outcome, and observable batch finish from the request. Use existing readiness and priority conventions. For “all available tickets,” select execution-ready work inside the stated project/milestone or goal; do not treat open Inbox ideas as approved product commitments. Surface a missing selection decision only when it materially changes what should be built.
- Carry the request's GitHub-update, commit/push, and delivery permissions into assignments. This skill does not extend them. Use existing authorization; resolve genuinely missing permissions once for a concrete batch rather than asking at every checkpoint. Merge, release, production writes and other protected actions retain their authorization boundaries.
- State the batch boundary briefly when useful, then proceed. Do not require a new planning document, board, tracking issue, or approval of routine allocation.

## Allocate and launch

- Group work by real code dependencies and coupled behavior. One assignment may contain several issues or multiple features within one issue. Keep tightly coupled changes with one writer or sequence them; parallelize independent work when it earns the coordination cost.
- Use native subagents when useful, respecting the selected model/effort, applicable agent instructions and runtime concurrency. Run larger pools in waves, or execute sequentially when delegation adds little value.
- Allocate each writing assignment a safe checkout and dependency base using the [checkout rules in GitHub Execute](references/github-execute.md), in the target repository context supported by the tool.
- Give each worker a self-contained assignment: ownership and issue URLs, outcome/scope/finish, source and exact checkout/branch/base, permissions, verification, and coordinator identity/reporting route. Require reports at verified checkpoints, dependencies/blockers and completion. Implementation workers read and follow the bundled [GitHub Execute](references/github-execute.md) reference; include its resolved path in each assignment, rather than assuming a separately installed skill; other workers use their assigned review or investigation scope. Tell workers they are not alone and must preserve others' work; subagents do not isolate their filesystem.
- Do not automatically create user-owned sidebar chats for worker subtasks. Create an enduring separate chat only when the user explicitly requests one; message existing chats only with the user's authorization.

## Follow through without the user relaying status

- Implementation workers record verified increments according to Execute and keep working through their assigned scope. Route user decisions through the CTO.
- Receive updates and use native agent wait/follow-up controls. Review actionable results, redirect stalled or drifting work, and launch the next ready assignments without routine approval. A GitHub comment records progress but does not wake the coordinator; use native worker notifications rather than adding a polling service or schedule merely to collect worker status.
- Sequence contested devices, simulators, builds or ports. When a dependency becomes available, provide its actual source/base to the affected worker.
- Keep only a compact active queue in the main context. GitHub owns durable progress and decisions; commits/PRs own portable code. On resume or coordinator replacement, reconstruct from current issues/comments, source and tests before starting workers. Check existing work rather than repeating it or trusting stale completion claims.

## Keep one decision inbox

Own routine technical choices. Treat recorded product decisions as the baseline; raise new evidence when it materially changes the intended outcome, customer behavior, strategy, taste requirements or a protected commitment.

For a decision the user must make, present the goal, concrete choice, recommendation, material gain/downside, and work affected in the main CTO chat. Bundle related choices when useful. Use the available user-input mechanism when appropriate; keep required answers pending and never treat silence as approval. Pause dependent work and continue independent work.

When GitHub updates are authorized, record the pending question and affected scope on its owning issue. After the user answers in the CTO chat, record the decision there, update requirements when necessary, and inform affected workers. For a cross-issue decision, record it once and link affected issues. An assistant or secondary coordinator reports through this same lead; it does not become another user decision inbox.

## Integrate and finish

- Inspect task-owned worker changes and verification against the assignment and issue outcome. Comments locate evidence; they do not replace source review. Integration may use commits or inspectable task-owned diffs as the agreed delivery workflow permits; a progress comment alone is insufficient.
- Integrate into the agreed candidate using the authorized branch/commit/PR workflow. Own routine conflict resolution and in-scope corrections. Test affected interactions and run or accept the repository-required gate for the settled candidate when required by risk; reuse valid CI/workflow evidence for that source. Use Execute for corrections rather than expanding scope.
- Keep issue status honest: distinguish a verified increment, a completed worker assignment, and acceptance of the integrated issue. Close issues only when their acceptance conditions and required delivery state are met and closing is authorized. Name blocked or deferred work explicitly.
- Before the final batch handoff, use [GitHub Review](references/github-review.md) to reconcile acceptance evidence, return technical defects for correction, and prepare the remaining human checklist and authorized GitHub review bookkeeping. Reuse completed evidence and let active reviewers finish rather than starting a duplicate verification pass.
- Finish when all agreed batch work reaches its requested state. If no useful authorized work can proceed, report the exact blockers and resumable source without claiming completion. Return one concise result with delivered issues/candidate, verification, unresolved product decisions and real remaining actions.
- After the work is accounted for and no active chat or process needs a managed worktree, retire it through the host's archive tool when available. Preserve branch history and work; do not delete checkouts or branches as routine cleanup.
