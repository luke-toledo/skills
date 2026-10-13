# Skills by Luke Toledo

Reusable agent skills by [Luke Toledo](https://luketoledo.com). Each skill lives in its own folder and can be installed individually.

## Available skills

| Skill | Purpose |
| --- | --- |
| [CTO](skills/cto/SKILL.md) | Coordinate an approved batch of GitHub issues through implementation, verification, and an integrated review candidate. |

## Install CTO

```bash
npx skills add luke-toledo/skills --skill cto
```

The Skills CLI lets you choose the target agent and installation scope. To list the skills in this repository without installing them:

```bash
npx skills add luke-toledo/skills --list
```

## Use CTO

Give the agent a repository, an approved set of issues or a project/milestone selection, the desired delivery state, and the operations it may perform. For example:

> Use CTO to coordinate issues #12, #18, and #23 in this repository. Produce a verified draft PR. You may create task branches, commit and push task changes, and update those issues. Bring new product decisions to this chat; ask before merging or deploying.

The coding agent owns technical coordination; the user remains the decision maker for product direction and consequential actions. CTO allocates independent work when native subagents are available, follows dependencies, integrates the result, and reconciles acceptance evidence. It also works sequentially when the host has no subagents.

## Requirements

- A coding agent that can load Agent Skills and access the project filesystem.
- GitHub access through a connector or an authenticated GitHub CLI.
- Git and the target repository's normal build/test tools for source changes.

GitHub Execute and GitHub Review are bundled in `skills/cto/references/`; no additional skill installation is required.

## CTO package

```text
skills/cto/
  SKILL.md
  agents/openai.yaml
  references/github-execute.md
  references/github-review.md
```

## Verification

The publishing copy was checked for valid skill metadata, bundled reference links, and author-specific filesystem paths. This is structural verification, not a claim that a real issue batch has been executed on every supported host.

## License

[MIT](LICENSE). Copyright (c) 2026 Luke Toledo.
