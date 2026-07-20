# SCM, Platform and AI Ecosystem Characterization

## Findings for IACodeEditors

## Executive Summary

This investigation characterized the GitHub ecosystem from an
architectural perspective rather than an implementation perspective.

The objective was **not** to reproduce GitHub Desktop, Copilot CLI or VS
Code, but to understand the responsibilities, integration points and
architectural boundaries required to design an extensible AI-enabled
development environment.

## Main Architectural Findings

### 1. SCM and Platform are complementary layers

Git remains an independent SCM, while GitHub extends it with
collaboration, identity and AI services.

### 2. Platform account types directly influence capabilities

Identity, organization policies and licensing determine which
capabilities are available to each client.

Identity → Organization Policies → Available Capabilities → Client
Experience

### 3. Clients are isolated

Editors remain independent applications and integrate with platform
services through adapters rather than becoming part of the platform.

### 4. AI capabilities are platform services

Reusable capabilities observed include:

-   Chat
-   Commit Message Generation
-   Conflict Resolution
-   Instructions
-   Skills
-   Agents
-   Tool Runtime

Different clients expose different subsets.

### 5. Enterprise restrictions reveal architecture

Enterprise restrictions exposed capability negotiation, policy
enforcement and feature visibility, becoming an architectural probe
rather than merely a limitation.

### 6. Linux implementation maturity varies

-   GitHub CLI: Native
-   Copilot CLI: Native
-   VS Code: Native
-   GitHub Desktop: Community-maintained on Linux, official on
    Windows/macOS.

### 7. Touchpoints are understood

Git → GitHub Platform → Identity → Capability Discovery → Clients (VS
Code, GitHub Desktop, Copilot CLI)

## Architectural Decision

The current level of understanding is sufficient to redesign
IACodeEditors around stable architectural concepts rather than
implementation details.

## Design Principles

-   Separate SCM from Platform.
-   Treat AI as reusable Platform Capabilities.
-   Preserve Editor Independence.
-   Identity drives Capability Discovery.
-   Support multiple Platform Providers.

## Final Conclusion

Rather than reproducing GitHub internals, this investigation identified
reusable architectural concepts that provide a solid foundation for the
next evolution of IACodeEditors.

## Methodological Note

The objective was to understand responsibilities, boundaries and
interactions between components instead of reverse engineering
implementations. This produced reusable architectural knowledge that is
resilient to implementation changes.
