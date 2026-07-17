# SSH-COMMIT-SIGNING

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

This document records the adoption of SSH commit signing for the IACodeEditors project.

Authentication and commit signing are different concerns.

---

## SSH Authentication

Used for:

- clone
- fetch
- pull
- push

It authenticates the developer to GitHub.

---

## Commit Signing

Commit signing proves the authenticity of an individual commit.

Signed commits appear on GitHub with the **Verified** badge.

---

## Why SSH instead of GPG?

The project already uses SSH.

Using SSH signing:

- reuses the existing key
- reduces configuration
- simplifies onboarding
- integrates well with GitHub

---

## Git Configuration

Enable SSH signing:

```bash
git config --global gpg.format ssh
```

Configure the signing key:

```bash
git config --global user.signingkey ~/.ssh/id_ed25519.pub
```

Enable signing by default:

```bash
git config --global commit.gpgsign true
```

---

## Allowed Signers

Typical file:

```text
~/.config/git/allowed_signers
```

Example:

```text
user@example.com ssh-ed25519 AAAAC3...
```

---

## GitHub

Register the same SSH public key as a **Signing Key**.

The same key may be used for:

- Authentication
- Commit Signing

---

## Expected Result

Future commits created locally should appear on GitHub as **Verified**.

---

## Design Principle

> Reuse existing infrastructure before introducing additional tools.

---

## Living Document

This document is expected to evolve together with the project.
