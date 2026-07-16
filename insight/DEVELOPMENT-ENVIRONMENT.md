# Development Environment Baseline

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

This document records the initial development environment for the IACodeEditors project.

Following Extreme Programming (XP), the environment starts intentionally simple and evolves only when experience justifies it.

---

## Guiding Principle

> Do the simplest thing that could possibly work.

---

## Baseline Toolset

### Operating System

- Fedora Linux 44

### Version Control

#### Git
The source of truth for version control.

#### GitHub
Remote hosting and collaboration platform.

#### GitHub CLI (`gh`)
Used for repository management, GitHub integration and GitHub Copilot CLI.

#### Git GUI
Optional graphical interface for history, branches and merges.

---

### Documentation

#### Markdown

The single source of truth for documentation.

#### Pandoc

Used to generate:

- PDF
- DOCX
- ODT
- HTML
- EPUB

Markdown remains the canonical source.

---

### Programming Language

#### Ruby

Primary implementation language.

Reasons:

- expressive
- portable
- excellent standard library
- compatible with Fedora and Red Hat Enterprise Linux

---

### Editor

#### CudaText

Primary editor for the project.

---

### Artificial Intelligence

#### Initial Provider

GitHub Copilot CLI

Future providers may include:

- llama.cpp
- Ollama
- Red Hat AI
- OpenAI-compatible APIs

The architecture must remain provider-agnostic.

---

## Evolution Policy

New tools will only be introduced when they provide clear value to the project.

---

## Living Document

This document is expected to evolve together with the project.
