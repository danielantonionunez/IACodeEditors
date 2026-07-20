# GITHUB-DESKTOP-FORK-COMPARISON.md

## Authors
Daniel A. Nuñez C. and IAN

## Purpose

This document summarizes the architectural differences observed between the official GitHub Desktop project and the Linux community fork while researching IACodeEditors.

---

## Motivation

The Linux Flatpak package is not an official GitHub Linux release.

Instead, it is based on the Shiftkey community fork, which tracks the upstream project but may lag behind new capabilities.

---

## Evidence

### Official upstream

Repository:
https://github.com/desktop/desktop

Observed:

- Active development.
- Copilot source under:
  app/src/ui/copilot
- Continued evolution beyond repository management.

### Linux fork

Repository:
https://github.com/shiftkey/desktop

Observed:

- Linux adaptations.
- Flatpak packaging.
- Version:
  3.4.13-linux1
- Based on upstream but not feature-identical.

---

## Runtime characterization

The installed Flatpak revealed:

- Freedesktop SDK runtime
- Electron application
- Unpacked JavaScript bundle
- Embedded Git distribution
- Embedded Git LFS
- Credential Manager
- Keytar integration
- SSH Agent integration through Flatpak
- Electron runtime assets

The application ships its own Git implementation instead of depending on the host installation.

---

## Embedded Git

The packaged application contains:

- git
- git-lfs
- scalar
- git-credential-manager
- git-credential-desktop
- templates
- hooks
- locale files
- SSL certificates
- manuals

This guarantees consistent behavior across supported operating systems.

---

## Architecture comparison

Official Desktop

- Repository management
- Pull Requests
- Git integration
- Copilot modules (development branch)

Linux fork

- Repository management
- Pull Requests
- Git integration
- Linux-specific adaptations

Current evidence indicates that the Linux fork has not yet incorporated the latest Copilot modules present in the upstream repository.

---

## Implications for IACodeEditors

Separate these concepts:

1. Platform capabilities
2. Upstream implementation
3. Community forks
4. Packaging technology

Do not assume every distribution exposes identical functionality.

---

## Lessons Learned

- Community ports can lag behind upstream.
- Packaging technology is independent from product capabilities.
- Characterizing packaged applications is useful before studying source code.
- After characterization, the upstream repository becomes the preferred architectural reference.

---

## Future Work

- Compare upstream Copilot implementation with the Linux fork.
- Study the Copilot UI architecture.
- Characterize Electron process separation.
- Compare authentication across Desktop, gh CLI and Copilot.
- Extract reusable architectural patterns for IACodeEditors.
