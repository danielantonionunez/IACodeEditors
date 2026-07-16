# IACodeEditors

## Purpose

**IACodeEditors** is an engineering project whose purpose is to build a modular toolkit that integrates AI assistants into lightweight code editors through a provider-agnostic architecture.

The project seeks to:

- Integrate GitHub Copilot as the initial AI provider.
- Keep the editor independent from the AI backend.
- Allow future support for local and remote AI providers (e.g. llama.cpp, Ollama, Red Hat AI, OpenAI-compatible APIs).
- Favor simplicity, portability and long-term maintainability.
- Build the solution incrementally using Extreme Programming (XP).

---

# Development Approach

This project adopts **Extreme Programming (XP) Version 1** as its software development methodology.

Rather than redefining XP, this document records the **XP Profile** used by this project.

The profile may evolve as experience is gained.

---

# XP Profile

## Values

The project follows the original XP values.

## Practices

### 1. Collective Ownership

Every project artifact belongs to the whole team.

This includes:

- source code
- documentation
- tests
- architecture
- scripts
- knowledge

No artifact has a permanent owner.

---

### 2. On-Site Customer

The customer represents the product domain.

The customer may be represented by:

- one or more people
- domain documentation
- AI assistants
- domain models

"On-Site" means continuously available and actively engaged, not necessarily physically present.

---

### 3. Planning Game

Planning is treated as a continuous decision-making activity.

Scope, priorities and releases evolve according to feedback.

---

### 4. Metaphor

A shared understanding of the system may be expressed through:

- Domain-Driven Design
- CRC Cards
- Event Storming
- System metaphors
- other shared modeling techniques

---

### 5. Sustainable Pace

Maintain a development rhythm that can be sustained over the long term.

---

### 6. Pair Programming

A Pair is defined as a collaborative development entity.

It may consist of:

- two people
- one person and one AI assistant
- multiple participants (Mob Programming)

---

### 7. Design Improvement

Continuously improve the design.

This practice embeds:

- Simple Design
- Refactoring

The goal is to reduce complexity while preserving behavior.

---

### 8. Testing

Testing begins before implementation.

The project adopts the ideas from:

- xUnit Test Patterns (Gerard Meszaros)

Conceptually:

- TDD encompasses BDD.
- Tests help discover and refine the design.

---

### 9. Short Releases

Deliver value frequently.

Release size is determined by delivered value rather than artifact size.

Vertical slicing is encouraged.

---

### 10. Standards

Standards apply to every project artifact.

This includes:

- coding conventions
- documentation
- naming
- commits
- repository organization

---

### Deferred Practice

Continuous Integration is intentionally deferred.

It will be incorporated when collaboration scenarios require systematic integration workflows.

---

# Living Document

This document is expected to evolve as the project evolves.

# Authors

Daniel A. Nuñez C. e IAN
