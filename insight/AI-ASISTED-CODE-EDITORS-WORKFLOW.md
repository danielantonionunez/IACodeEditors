# AI-Assisted Code Editors Workflow

## Project

IACodeEditors

**Owner (Accountable):** Daniel Nuñez

**Authors:** Daniel Nuñez, Ian (AI Collaborator)

---

# Purpose

This document defines the initial operating model adopted by the
IACodeEditors project for AI-assisted software development.

Rather than describing a software architecture, this document defines
how developers, SCM, platforms, AI capabilities and development tools
collaborate under real-world enterprise constraints.

The model emerged from experimental characterization of the GitHub
ecosystem instead of theoretical assumptions.

---

# Motivation

Enterprise environments introduce restrictions that directly influence
which AI capabilities are available.

Instead of attempting to bypass those restrictions, the project adopts
them as architectural constraints.

The resulting operating model provides an immediately usable workflow
while remaining compatible with future automation.

---

# Guiding Principles

- Respect enterprise governance.
- Reuse existing platform capabilities.
- Keep editors independent.
- Separate SCM from Platform.
- AI capabilities are consumed through platform integrations.
- Favor operational simplicity.

---

# Layered Operating Model

```

+------------------------------------------------------+
| Developer |
+------------------------------------------------------+
|
v

+------------------------------------------------------+
| Code Editor |
| (CudaText, VS Code, future editors...) |
+------------------------------------------------------+

|
v

+------------------------------------------------------+
| Git |
| Source Control Management |
+------------------------------------------------------+

|
| SSH Authentication
| SSH Commit Signing
v

+------------------------------------------------------+
| GitHub Platform |
+------------------------------------------------------+

|
+--------------------+---------------------+
| |
v v

GitHub Services AI Capabilities

|
+-----------+------------+---------------+
| | |
v v v

VS Code GitHub Desktop GitHub Web

```
---

# Operating Responsibilities

## Source Control Management

Git is the authoritative SCM.

Responsibilities:

- repository history
- branches
- merge
- rebase
- commits
- tags

Git remains independent from GitHub.

---

## Transport

SSH provides:

- authentication
- secure transport
- commit signing

SSH replaces the need for GPG in this project.

Every commit should become Verified on GitHub.

---

## Platform

GitHub extends Git by providing:

- repositories
- collaboration
- pull requests
- AI services
- policies
- enterprise governance

---

# Branching Strategy

The project adopts Trunk-Based Development.

Characteristics:

- short-lived branches
- merge through Pull Requests
- approved Pull Requests
- obsolete feature branches after merge

The platform becomes responsible for collaboration while Git remains
responsible for repository history.

---

# Editor Independence

Editors remain independent applications.

Examples include:

- CudaText
- VS Code
- future lightweight editors

Editors are selected according to developer preference rather than
platform requirements.

---

# AI Capability Consumption

AI capabilities are consumed through clients that are compatible with
enterprise policies.

Current observations:

## GitHub CLI

Provides platform capabilities.

Enterprise restrictions may disable Copilot features.

---

## GitHub Copilot CLI

Powerful AI runtime.

Unavailable under current enterprise policies.

Not part of the initial operating model.

---

## GitHub Copilot App

Depends internally on Copilot CLI capabilities.

Unavailable under current enterprise policies.

---

## GitHub Desktop

Windows:

Provides:

- AI-generated commit messages
- merge assistance
- configurable AI models

Linux:

Community implementation.

Currently exposes GitHub platform capabilities but not integrated AI.

---

## VS Code

Available on Linux and Windows.

Provides:

- integrated AI Chat
- repository awareness
- AI-assisted repository actions
- commit assistance
- merge assistance

Enterprise policies are automatically respected.

Current limitation:

Model selection remains automatic under current policy.

---

## GitHub Web

Provides:

- AI Chat
- repository access
- configurable AI models
- enterprise token consumption

Acts as an additional AI client.

---

# Enterprise Policies

Enterprise governance determines available capabilities.

Observed examples include:

- disabled CLI agents
- managed session synchronization
- managed semantic indexing
- managed feature visibility
- automatic capability negotiation

The IDE explicitly communicates policy-controlled features, making
governance visible to developers.

Restrictions are therefore considered architectural inputs rather than
technical obstacles.

---

# Resulting Workflow

Developer

↓

Editor

↓

Git

↓

SSH

↓

GitHub Platform

↓

Enterprise Policies

↓

Available AI Capabilities

↓

Implementation

---

# Benefits

This operating model provides:

- immediate usability
- enterprise compatibility
- editor independence
- provider isolation
- reusable architecture
- future automation path

The workflow remains productive despite enterprise restrictions.

---

# Future Evolution

This operating model represents the first delivery of IACodeEditors.

Future iterations may progressively introduce:

- Provider abstraction
- AI Toolkit
- Automation scripts
- AI orchestration
- Local LLM providers
- MCP integration
- Multiple SCM providers
- Multiple Platform providers

Each evolution should preserve the same architectural separation
identified during this characterization effort.

---

# Key Insight

The objective is not to recreate GitHub.

The objective is to define a practical operating model that combines
existing SCM, platform and AI capabilities into a cohesive development
experience.

The operating model becomes the foundation upon which future tooling,
automation and provider abstraction can evolve incrementally.