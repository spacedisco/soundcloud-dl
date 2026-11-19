# soundcloud-dl: notes for agents

- What it is: a fork of AYehia0/soundcloud-dl, re-pathed as a Go library for Space Disco tooling. Part of the Space Disco org (Steven's party and music brand, being revived). Dormant code: keep changes small and say what you couldn't run.
- Stack: Go, cobra, goquery, m3u8.
- Layout: `main.go` + `cmd/` the CLI; `pkg/soundcloud` the client and downloader (what spacedisco/cli imports); `internal/`, `pkg/theme`; `testdata/` fixtures.
- Commands:

  ```sh
  go vet ./...
  go test ./...
  go build ./...
  ```

- CI runs: `go vet ./...`, `go test ./...`, `go build ./...`, plus gitleaks on new commits and a PR title check.
- Every change comes with a test when there is something testable; every bug fix with a test that failed before the fix.
- Commits and PR titles use Conventional Commits (`feat:`, `fix:`, `docs:`, `ci:`, `build:`, `chore:`, `test:`, `refactor:`).
- One PR per change, squash merged into the default branch. Agents merge their own PRs once CI is green. Say plainly in the PR what wasn't built or run.
- Never commit secrets or personal data. Config comes from environment variables; real values live in Steven's Bitwarden vault.
- Never without Steven's yes: deploying, publishing a package or app, making the repo public, changing repo settings, deleting data or rewriting history, spending money.
- Update docs/STATUS.md when a PR merges.
- This is a fork. Keep changes small and library-shaped so upstream fixes can still be merged in.

- The full repo standard and its model repo: spacedisco/playlog (docs/plan/repo-standard.md).
