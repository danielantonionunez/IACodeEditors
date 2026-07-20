# GITHUB-AUTHENTICATION-DECISION

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

Record the authentication strategy adopted for GitHub CLI during the initial stages of IACodeEditors.

---

## Decision

The project will initially use the official OAuth Web authentication flow:

```bash
gh auth login --web
```

Only after validating all required GitHub CLI capabilities will the authentication strategy be revisited using a Fine-grained Personal Access Token (PAT).

---

## Motivation

The goal is to understand the complete behaviour of GitHub CLI before reducing permissions.

Starting with the official authentication flow minimizes the risk of confusing missing permissions with product limitations.

---

## Evaluation Plan

### Phase 1

- Authenticate with OAuth Web.
- Explore GitHub CLI capabilities.
- Validate repository, collaboration and Copilot features.
- Document observations.

### Phase 2

- Create a Fine-grained PAT.
- Repeat the same experiments.
- Compare both authentication models.
- Identify the minimum required permissions.

---

## Architectural Notes

Git transport and GitHub authentication are independent concerns.

Git:
- SSH transport.
- SSH commit signing.

GitHub CLI:
- OAuth Web or Fine-grained PAT.
- GitHub API access.

---

## Guiding Principle

> Understand first, optimize later.

The project intentionally begins with the most complete supported authentication mechanism and only afterwards applies the Principle of Least Privilege.

---

## Expected Outcome

This approach should produce:

- Better understanding of GitHub CLI.
- Fewer false assumptions caused by restricted permissions.
- A documented migration path from OAuth to Fine-grained PAT.
- A reproducible authentication strategy for future automation.

---

## Living Document

This decision may evolve as additional authentication mechanisms are evaluated.
