# Contributing to mainvec projects

This is the default contribution guide for every `mainvec` repository. A
repository's own `CONTRIBUTING.md` adds build, test, and project rules on top
of it.

## How work flows

```
idea → issue #NNN → branch → (plan) → draft PR → review → merge
```

| Stage | Where it lives |
|---|---|
| Idea or question | An issue, or a Discussion where the repo has Discussions enabled |
| Accepted work | An issue with a milestone |
| Design being reviewed | `design` label on the issue; plan on the issue branch |
| In progress | Draft pull request |
| Parked | `icebox` label |
| Done | Pull request merged with `Closes #NNN` |

Repositories that route ideas and bug reports through Discussions say so in
their issue templates. There, start a Discussion; a maintainer opens the issue
once the work is accepted.

## Trivial changes

Typo fixes, formatting, dependency bumps, and CI tweaks with no behavior change
need no issue. Open a pull request with a Conventional Commit title.

## Branches, commits, and pull requests

- Branch from `main`: `feat/NNN-slug`, `fix/NNN-slug`, `perf/NNN-slug`, `chore/NNN-slug`.
- Keep branches short-lived. Rebase on `main` before merging; maintainers squash-merge.
- Titles use [Conventional Commits](https://www.conventionalcommits.org/) with
  the issue: `feat(module): add thing (#NNN)`.
- The pull request body contains `Closes #NNN` on its own line.
- Large efforts are split into child issues, each with its own pull request.

## Plans

Substantial work (new behavior, APIs, commands, UI screens, protocol or storage
changes, security-sensitive or cross-module work) has a technical plan:

- Path: `plans/NNN-slug.md`, where `NNN` is the issue number (zero-padded to 3 digits).
- Create the issue first; never number a plan independently of its issue, and
  never put `DRAFT` or `WIP` in a file name.
- The plan links its issue and keeps a `## Progress` checklist of implementation tasks.
- The pull request's last commit moves the plan to `plans/archived/YYYY-MM-DD-NNN-slug.md`.

## Avoiding merge conflicts

- Never hand-merge generated code or lockfiles. Take either side, regenerate, commit.
- Do not add shared index or roadmap files; milestones and labels are the index.
- Follow the repository's changelog rule: most repositories generate the
  changelog from pull request titles, so do not edit `CHANGELOG.md` there.

## AI agents

AI-assisted contributions are welcome when you understand and can explain every
change. The full workflow that agents follow is in
[mainvec/agents](https://github.com/mainvec/agents/blob/main/com.github.copilot/rules/feature-workflow.instructions.md);
each repository's `AGENTS.md` adds its project rules.

## Security

Report vulnerabilities privately through the repository's **Security → Report a
vulnerability** page, never in a public issue or discussion.
