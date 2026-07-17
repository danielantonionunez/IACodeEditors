# COMMIT-SIGNING-DECISION

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

This document records the decision to preserve the original Git history after introducing SSH commit signing.

---

## Context

SSH commit signing was configured after the first local commits had already been created.

The repository therefore contains both unsigned and verified commits.

---

## Alternatives

### Rewrite History

Re-sign previous commits using an interactive rebase.

Pros:

- All commits become verified.

Cons:

- Changes commit hashes.
- Requires force push.
- Rewrites project history.

### Preserve History (Selected)

Keep the original commits unchanged.

Pros:

- Preserves the authentic evolution of the project.
- Shows when commit signing became part of the workflow.
- Avoids unnecessary history rewriting.

---

## Decision

The project intentionally preserves the existing history.

Unsigned commits are treated as part of the project's evolution rather than as mistakes to hide.

---

## Future

Commit signing is expected to become the normal practice.

Repository protection rules or pull request checks may later require signed commits.

Even so, if an unsigned commit reaches the repository, the preferred response is to understand why it happened instead of rewriting history unless there is a compelling reason.

---

## Insight

The objective is not a perfect-looking Git history.

The objective is an honest, traceable and understandable project history.

---

## Guiding Principle

> Prefer preserving meaningful history over rewriting the past for cosmetic consistency.

---

## Living Document

This document is expected to evolve together with the project.
