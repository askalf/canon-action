# Security Policy

truecopy-action is a CI gate: it fails the build when a vetted agent skill or
MCP server drifts from its `truecopy.lock` or turns poisonous. A vulnerability
here means the gate **failing open** — letting a drifted or poisoned change
merge while reporting success.

## Reporting a vulnerability

Please **do not open a public issue** for security reports.

- **Preferred:** [GitHub private vulnerability reporting](https://github.com/askalf/truecopy-action/security/advisories/new) — creates a private advisory visible only to maintainers.
- **Email:** support@askalf.org with `truecopy-action security` in the subject.

You'll get an acknowledgement within 72 hours. Please include a minimal
reproduction (a repo layout + lock file where the gate passes but should fail)
where possible.

## Scope

- **Fail-open** — any drifted, missing, or poisoned entry that the action lets
  through with a green check.
- **Input injection** — action inputs reaching a shell or the truecopy CLI in a
  way that alters what gets vetted.
- Vulnerabilities in the underlying scanner belong to
  [truecopy](https://github.com/askalf/truecopy/security/policy) itself.

## Supported versions

Pre-1.0: only the latest release receives security fixes.
