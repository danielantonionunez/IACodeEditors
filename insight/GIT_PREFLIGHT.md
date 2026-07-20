# Insight: Git Preflight

## Context

During the characterization of Git, GitHub, SSH signing, and multiple
GitHub identities, an important observation emerged.

The development workflow should make the correct path the easiest path.

Rather than relying on memory or post-push verification, the workflow
should validate its configuration before creating or publishing a
commit.

---

# Purpose

Reduce configuration mistakes before they become part of the project's
history.

Git Preflight provides a lightweight verification step immediately
before committing or pushing changes.

Its objective is prevention rather than correction.

---

# Philosophy

Verification should occur before publishing.

The earlier an inconsistency is detected, the easier it is to correct.

This follows the same philosophy applied throughout the project:

- Test First
- Early Feedback
- Small Releases
- Continuous Improvement

Git Preflight extends these ideas to version control.

---

# Git Remains the Launcher

Git is the single mechanism responsible for creating and publishing the
repository history.

Editors and graphical tools remain clients of Git.

Examples include:

- Git CLI
- GitHub Desktop
- Visual Studio Code
- IntelliJ IDEA
- Eclipse
- Other Git clients

Regardless of the client,
Git remains responsible for:

- creating commits
- signing commits
- maintaining history
- pushing changes
- interacting with remote repositories

The workflow therefore keeps Git as the authoritative launcher.

---

# Preflight Workflow

```
Conversation

↓

Implementation

↓

Git Preflight

↓

Commit

↓

Verify Commit

↓

Push

↓

Verify Remote

↓

Feedback
```

Every verification occurs before irreversible actions whenever
possible.

---

# Typical Verifications

Git Preflight may validate:

## Repository

- correct repository
- expected remote
- expected branch

---

## Identity

- user.name
- user.email

---

## Signing

- signing enabled
- signing key configured
- SSH signing available

---

## Authentication

- SSH authentication
- expected GitHub account

---

## Working Tree

- pending changes
- staged changes
- merge conflicts
- detached HEAD

---

## Last Commit

- author
- committer
- signature
- verification

---

# Example Checklist

```
✓ Repository

✓ Branch

✓ Remote

✓ user.name

✓ user.email

✓ Signing Key

✓ SSH Authentication

✓ Commit Signature

✓ Working Tree

✓ Ready to Commit
```

The checklist should remain short,
fast,
and easy to execute.

---

# Relationship with XP

Git Preflight reinforces several XP practices.

## Testing

Configuration is validated before publishing.

---

## Small Releases

Errors are detected before becoming part of the project's history.

---

## Sustainable Pace

Preventing mistakes reduces unnecessary rework and cognitive load.

---

## Standards

The same verification process is consistently applied before commits.

---

## Collective Ownership

Every contributor benefits from the same validation process.

---

# Future Evolution

The checklist may eventually evolve into a reusable command such as:

```
git-preflight
```

or another lightweight automation.

Automation should simplify the workflow rather than replace
understanding.

---

# Benefits

Git Preflight provides:

- earlier feedback
- fewer configuration mistakes
- consistent identities
- verified signatures
- predictable commits
- simplified collaboration
- increased confidence before publishing

---

# Key Insight

A good workflow makes the correct path the easiest path.

Git remains the authoritative launcher responsible for creating and
publishing project history.

Git Preflight simply verifies that everything is ready before that
history is written.

Verification should occur before the commit whenever possible, and
before the push whenever necessary, transforming configuration errors
into inexpensive corrections instead of historical artifacts.