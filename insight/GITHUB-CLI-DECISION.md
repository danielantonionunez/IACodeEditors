# GITHUB-CLI-DECISION

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

Record the decision to adopt GitHub CLI (gh) as the primary interface to GitHub.

---

## Installation

Preferred installation:

```bash
sudo dnf5 install gh
```

Fedora 44 successfully installed:

```
gh version 2.94.0
```

No external repository was required.

Only if the native package is unavailable or too old should the official GitHub repository be added.

---

## Decision

Prefer native operating system packages before adding external repositories.

Benefits:

- Cleaner environment.
- Easier maintenance.
- Better OS integration.
- More reproducible installations.

---

## Architectural Observation

Git and GitHub CLI have different responsibilities.

Git:
- Version control.

GitHub CLI:
- Repository management.
- Pull Requests.
- Issues.
- Releases.
- GitHub Actions.
- Copilot.

The project prefers using gh whenever interacting with GitHub, while keeping Git as the underlying version control system.

---

## Repository Provider

Future architecture may abstract repository providers:

```
Repository Provider

GitHub (gh)
GitLab (glab)
Forgejo
Gitea
```

Changing providers should affect only this integration layer.

---

## Enterprise Ecosystem

The successful installation from Fedora repositories increases confidence that the same tooling will integrate naturally with the wider enterprise Linux ecosystem, including Fedora, Red Hat Enterprise Linux, CentOS Stream and Amazon Linux through their native packaging mechanisms.

This does not imply binary compatibility between all distributions, but it does support the project's preference for standard package-managed software.

---

## Guiding Principle

> Prefer native operating system integration over custom installation mechanisms whenever both satisfy the project's needs.

---

## Living Document

This document will evolve as additional repository providers are evaluated.
