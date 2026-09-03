# Conventions across jwwitt repos

One person, several repos, one set of habits. Repo-specific rules live in each repo's README or CLAUDE.md and win over this file.

## Issues

- Every issue carries one `type:` label: `feature`, `bug`, `chore`, `decision`, `spike`. `out-of-scope` closes an issue that will not be done.
- Each repo has `area:` labels for scope within it. Priority and size are **not** labels: they are fields on the [JWW Roadmap](https://github.com/users/jwwitt/projects/2) project.
- Epics are ordinary issues titled `Epic: …` whose children are sub-issues.
- `type:decision` issues produce an ADR under `docs/adr/`; the issue closes when the ADR merges.

## Branches and pull requests

- Branch from `main` as `jwwitt/<topic>` or `jwwitt/issue<N>`.
- Squash merge only; the PR title becomes the commit subject and the PR body its message, so write both for the log.
- The PR carries the `type:` label — auto-generated release notes group by PR labels.
- Direct commits to `main` are fine in config-only repos with no CI; code repos require a PR and green checks.

## Milestones and releases

- Milestones are named `vX.Y <name>` and have no due dates; target dates live on the project.
- Tagging `vX.Y.0` publishes a release with generated notes and closes the `vX.Y` milestone.

## Commits

- Signed (SSH). Message says what the change is for and what was rejected, not only what moved.
