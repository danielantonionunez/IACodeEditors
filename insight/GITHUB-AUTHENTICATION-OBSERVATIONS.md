# GITHUB-AUTHENTICATION-OBSERVATIONS.md

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

Document the observations obtained after completing the first successful OAuth authentication with GitHub CLI.

---

## Environment

- Operating System: Fedora
- GitHub CLI: `gh`
- Git Transport: SSH
- Authentication: OAuth Device/Web Flow

Command used:

```bash
gh auth login --hostname github.com --git-protocol ssh --skip-ssh-key --web
```

---

## Authentication Flow

The authentication process follows the OAuth Device Authorization Flow.

Observed sequence:

1. `gh` displays a one-time code.
2. The user opens (or `gh` opens) `https://github.com/login/device`.
3. The code is entered.
4. GitHub requests authorization for the GitHub CLI application.
5. After authorization, `gh` detects completion automatically.
6. An OAuth access token is stored securely in the system keyring.

---

## Authentication Status

Running:

```bash
gh auth status
```

produced information equivalent to:

```text
✓ Logged in
✓ Credentials stored in keyring
✓ Git protocol: SSH
✓ Active account
✓ OAuth token available
✓ Token scopes:
    - gist
    - read:org
    - repo
```

### Observations

The token itself is not stored in the repository.

`gh auth status` confirms:

- the token exists,
- it is stored in the operating system keyring,
- SSH remains the Git transport,
- the token is used for GitHub API operations.

---

## Token Inspection

Running:

```bash
gh auth token
```

returns the complete OAuth access token.

This command is intended for integration with other tools and should be treated as sensitive output.

The token should never be:

- committed,
- logged,
- shared,
- embedded in source code.

---

## Separation of Responsibilities

Current architecture:

```text
Git
 ├── SSH transport
 └── SSH commit signing

GitHub CLI
 ├── OAuth access token
 ├── GitHub REST / GraphQL API
 └── Credentials stored in OS keyring
```

Git authentication and GitHub API authentication are independent concerns.

---

## Initial Scopes

The initial OAuth authorization granted:

- gist
- read:org
- repo

These represent the baseline permissions supplied by the official GitHub CLI OAuth application.

Future experiments using Fine-grained PATs will compare whether a reduced permission set can preserve the required functionality.

---

## Next Step

Characterize GitHub CLI capabilities while using this baseline authentication.

Only after the expected behaviour has been documented should permissions be reduced and compared.

---

## Guiding Principle

> Characterize before constraining.

Understand the complete behaviour using the provider's recommended configuration before attempting to minimise permissions or capabilities.
