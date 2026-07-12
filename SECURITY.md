# Security Policy

`truecopy-action` is the GitHub Action wrapper for [truecopy](https://github.com/askalf/truecopy) — the supply-chain gate for AI agents. It is a supply-chain tool, so vulnerability reports get priority attention.

## Reporting a vulnerability

Please **do not open a public issue** for security reports.

- **Preferred:** [GitHub private vulnerability reporting](https://github.com/askalf/truecopy-action/security/advisories/new) — creates a private advisory visible only to maintainers.
- **Email:** support@askalf.org with `truecopy-action security` in the subject.

You'll get an acknowledgement within 72 hours. Please include a minimal reproduction where possible.

## Scope

This repo is the thin composite-action layer. Report here anything specific to how the action shells out:

- The action passing the wrong ref, path, or flag to truecopy so a poisoned or drifted source slips past `verify` / `scan`
- Command or argument injection through an input (`command`, `path`, `marketplace`, `lock`, `trust`, `working-directory`, `truecopy-ref`)
- Installing truecopy from a ref other than the one pinned via `truecopy-ref`
- The `report` output or step summary leaking secrets present on the runner

Findings in truecopy's own detection or verification engine (a poisoned skill passing verification, pin bypass, signature forgery, a missed injection pattern) belong in the [truecopy security policy](https://github.com/askalf/truecopy/security/policy).

## Supported versions

Only the latest release and the moving `v1` major tag receive fixes; there are no maintenance branches. Pin `askalf/truecopy-action@<full-sha>` for an airtight supply chain, or `@v1` to track patches automatically.
