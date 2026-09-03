# Conventions across jwwitt repos

One person, several repos, one set of habits. Repo-specific rules live in each repo's README or CLAUDE.md and win over this file.

## Issues

- Every issue carries one `type:` label: `feature`, `bug`, `chore`, `decision`, `spike`. `out-of-scope` closes an issue that will not be done.
- Each repo has `area:` labels for scope within it. Priority and size are **not** labels: they are fields on the [JWW Roadmap](https://github.com/users/jwwitt/projects/2) project.
- Cross-repo blocking is recorded with GitHub's issue **dependencies** (`blocked_by`), not only in prose. A dependency written in a sentence is invisible to the board, and the board is where the order is actually read.
- Epics are ordinary issues titled `Epic: …` whose children are sub-issues.
- `type:decision` issues produce an ADR under `docs/adr/`; the issue closes when the ADR merges.

## Branches and pull requests

- Branch from `main` as `jwwitt/<topic>` or `jwwitt/issue<N>`.
- Squash merge only; the PR title becomes the commit subject and the PR body its message, so write both for the log.
- The PR carries the `type:` label — auto-generated release notes group by PR labels.
- Direct commits to `main` are fine in config-only repos with no CI; code repos require a PR and green checks.

## Sprints

- The **Sprint** iteration field on the [JWW Roadmap](https://github.com/users/jwwitt/projects/2) is the time box: two weeks, starting Monday 2026-09-07.
- Sprints are the *time* box; milestones are the *outcome* box. A milestone slips by moving its issues to a later sprint, never by moving a date — which is what keeps a slip visible instead of absorbed.
- Sprints cross repos. A milestone cannot, which is the reason both exist.

## Milestones and releases

- Milestones are named `vX.Y <name>` and have no due dates; target dates live on the project.
- Tagging `vX.Y.0` publishes a release with generated notes and closes the `vX.Y` milestone.

## Wikis

- Every repo has one, and it holds **operator and how-to documentation only**: runbooks, setup walkthroughs, troubleshooting, screenshots.
- The README stays the front door — scope, layout, and what never gets committed.
- **ADRs stay in `docs/adr/`.** A wiki edit bypasses PR review and is not versioned with the code that made the decision true, and the convention above — a `type:decision` issue closes when its ADR *merges* — has no meaning without a merge.
- Rule of thumb: if being wrong about it breaks a *build*, it belongs in the repo. If being wrong about it breaks a *restore at 2am*, it belongs in the wiki.

## Commits

- Signed (SSH). Message says what the change is for and what was rejected, not only what moved.
