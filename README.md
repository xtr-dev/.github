# xtr-dev shared workflows

Reusable GitHub Actions workflows for the xtr-dev npm packages. (The organization profile lives in `profile/README.md`.)

| Workflow | Purpose |
|---|---|
| `.github/workflows/plugin-release.yml` | Manual release: checks, then [@xtr-dev/changelog](https://github.com/xtr-dev/changelog) derives the version and CHANGELOG.md from conventional commits, then publishes to npm via OIDC trusted publishing with provenance. The commit and tag are pushed only after npm accepted the package, and a GitHub Release is created. |
| `.github/workflows/pr-title.yml` | Fails PRs whose title is not a conventional commit (the squash-merge subject feeds the changelog). |
| `.github/workflows/claude-review.yml` | Claude code review on every non-draft PR. |
| `.github/workflows/claude.yml` | `@claude` on issues and PRs, only for the logins in `allowed-actors`. |

## Adopting in a package repo

Copy `callers/release.yml`, `callers/pr.yml` and `callers/claude.yml` into the repo's `.github/workflows/`, and `callers/changelog.config.json` into the repo root. Then:

1. On npmjs.com → package → Settings → Trusted Publisher → GitHub Actions: organization `xtr-dev`, the repository, workflow `release.yml`, no environment. Delete the repo's `NPM_TOKEN` secret.
2. Repository settings: allow squash merging only, with the PR title as the default commit message.
3. Make sure the repo has a `CLAUDE_CODE_OAUTH_TOKEN` secret.

Callers pin `@v1`, a moving tag on the latest v1.x of these workflows. Breaking changes get a new major tag.

## Releasing

Actions → Release → Run workflow. Optional inputs: `dry-run` (preview only), `release-as` (force a version), `preid` (pre-release, published under the `next` dist-tag).

Version bumps: `feat` → minor, `fix`/`perf`/`refactor`/`revert`/`security`/`deps` → patch, breaking (`!` or `BREAKING CHANGE:`) → major (minor while on 0.x). `docs`, `test`, `ci`, `chore` and the rest are listed in the changelog but do not cause a release on their own.
