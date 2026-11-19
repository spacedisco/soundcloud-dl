# Status

Updated 2026-11-19, when the repo standard baseline was applied.

**State:** dormant. Space Disco is being revived (spacedisco.com); this repo is kept as part of that.

## What works
- `go vet`, `go test` and `go build` pass (CI checks them on every PR).

## Known broken or missing
- Nothing known.

## Next
- Compare with upstream AYehia0/soundcloud-dl and pull in fixes, or fold the few functions cli uses into cli.

## Not done yet from the repo standard
- Default branch `main`, branch protection with required checks and squash-only merges: repo settings, Steven's to-do.
- release-please, signed releases and a coverage floor: added when the repo is revived and has something to release.

## Log
- 2026-11-19: repo standard baseline (AGENTS.md, CLAUDE.md, CONTRIBUTING, SECURITY, STATUS, decision record, editorconfig, templates, CODEOWNERS, Dependabot, CI).
- Fixed a flaky `TestDownloadM3u8`: it built the segment list from a map, whose order is random, so the joined file only matched sometimes. Segments are now requested in order.
