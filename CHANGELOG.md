# Changelog

All notable changes to `truecopy-action` are documented here. The action follows
the moving-major-tag convention: pin `@v1` to track patches, or `@<full-sha>` for
an airtight supply chain.

## [Unreleased]

### Changed
- **Renamed `canon-action` → `truecopy-action`.** Tracks the [`canon` → `truecopy`](https://github.com/askalf/truecopy) rename. The old `askalf/canon-action` name still resolves via GitHub's rename redirect, and the `canon-ref` input is now `truecopy-ref`.
- Default `truecopy-ref` bumped to `v0.8.0` (was `v0.6.1`).

### Fixed
- **`canon.lock` back-compat now actually works from the action.** The action previously always passed `--lock truecopy.lock`, which defeated truecopy's built-in fallback to a pre-rename `canon.lock`. The `lock` input now defaults to empty and only passes `--lock` when you set a non-default path, so a repo pinned before the rename verifies with zero changes.

### Added
- `SECURITY.md` with private vulnerability reporting.
- Dependabot (`github-actions`) to keep the pinned `actions/checkout` SHA fresh.

## [0.1.0] — 2026-07-04

### Added
- Initial release: composite action wrapping the engine (then `canon`). `verify` gates the lock for drift / poisoning / publisher trust; `scan` poison-scans manifests, skill directories, or a cloned marketplace repo. Zero third-party action dependencies; the engine is installed at the ref you pin.

[Unreleased]: https://github.com/askalf/truecopy-action/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/askalf/truecopy-action/releases/tag/v0.1.0
