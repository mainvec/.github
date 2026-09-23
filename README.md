# mainvec/.github

Organization defaults for every `mainvec` repository.

- `CONTRIBUTING.md`, `PULL_REQUEST_TEMPLATE.md`, and `ISSUE_TEMPLATE/` apply to
  any repository that does not have its own copy. This repository must stay
  **public** for the defaults to apply.
- `.github/workflows/` holds reusable checks. Call them from a repository:

```yaml
# .github/workflows/workflow.yml
name: Workflow
on:
  pull_request:
    types: [opened, edited, synchronize, reopened]
jobs:
  pr-title:
    uses: mainvec/.github/.github/workflows/pr-title.yml@main
  plans:
    uses: mainvec/.github/.github/workflows/plan-lint.yml@main
```

The agent-facing version of these rules lives in the private `mainvec/agents`
repository (instructions and skills) and in each repository's `AGENTS.md`.
Change all three together.
