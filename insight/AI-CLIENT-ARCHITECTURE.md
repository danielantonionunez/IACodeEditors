# AI-CLIENT-ARCHITECTURE.md

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

Capture the architectural findings obtained while evaluating GitHub Copilot CLI, GitHub Copilot App and GitHub Desktop as potential integration points for AI-assisted development.

This document extends the GitHub Platform Provider model by introducing the concept of AI Clients.

---

# Motivation

Initial experiments suggested that GitHub CLI was the primary integration point.

Subsequent experiments demonstrated that GitHub exposes multiple official clients with different capabilities and governance policies.

Authentication alone is not sufficient to access every capability.

---

# Key Findings

## Authentication vs Authorization

Successful OAuth authentication does not imply every Copilot capability is enabled.

OAuth Success
→ Platform Policies
→ Capability Granted (or Denied)

---

## Official AI Clients

Current evidence indicates several official clients coexist:

- GitHub CLI (gh)
- GitHub Copilot CLI
- GitHub Copilot App
- GitHub Desktop
- IDE integrations
- GitHub Web

Each exposes a different subset of platform capabilities.

---

## Policy-driven capabilities

Enterprise policies can independently enable or disable features such as:

- Copilot CLI
- Copilot App
- Cloud Agent
- Desktop integration
- IDE Chat
- Model availability
- MCP
- Spaces
- Memory

The Platform Provider should therefore expose capability discovery rather than assuming functionality.

---

## AI Context Artifacts

The Copilot App automatically generated:

    .github/copilot-instructions.md

after analysing repository documentation.

This suggests AI context is becoming a first-class repository artifact rather than provider-specific metadata.

---

# Architectural Model

                  GitHub Platform

                         │
      ┌──────────────────┼───────────────────┐
      │                  │                   │
 Git Services      Copilot Services   Collaboration
      │                  │
      │        Policy / Licensing Layer
      │                  │
      └──────────┬───────┘
                 │
     ┌───────────┼─────────────────────────┐
     │           │           │             │
     ▼           ▼           ▼             ▼
   gh CLI   Copilot App GitHub Desktop IDE Plugins

---

# Implications for IACodeEditors

The project should evolve towards an AI-capable editor instead of targeting a single vendor tool.

Suggested abstraction:

IACodeEditors
    |
AI Integration Layer
    |
+------------------------------+
| GitHub | OpenAI | Local LLMs |
+------------------------------+

The editor should interact with capabilities, not vendor-specific commands.

---

# Design Principles

- Model providers instead of tools.
- Model capabilities instead of commands.
- Discover capabilities at runtime.
- Separate authentication from authorization.
- Treat AI context as a repository artifact.
- Keep the architecture provider-agnostic.

---

# Future Experiments

1. Evaluate GitHub Desktop.
2. Compare Desktop authentication with GitHub CLI.
3. Compare Desktop authentication with Copilot App.
4. Characterize IDE integrations.
5. Investigate BYOM support.
6. Investigate MCP integration.

---

# Working Hypothesis

GitHub is evolving from a collection of tools into a platform with multiple specialized AI clients.

IACodeEditors should aim to become one more AI-capable client rather than emulating a terminal utility.
