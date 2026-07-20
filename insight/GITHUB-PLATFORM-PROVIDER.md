# GITHUB-PLATFORM-PROVIDER.md

# Authors

Daniel A. Nuñez C. and IAN

## Purpose

Document the architectural model derived from the experimental
evaluation of GitHub CLI (`gh`) within the IACodeEditors project.

This document captures the evolution from viewing `gh` as a repository
utility to modelling it as a **GitHub Platform Provider**.

------------------------------------------------------------------------

# Context

The investigation has progressively characterized:

-   Git repository operations
-   SSH transport
-   SSH commit signing
-   OAuth authentication
-   GitHub CLI
-   Repository discovery
-   Repository cloning

The evidence shows that GitHub CLI does not replace Git; instead, it
orchestrates Git operations while exposing platform capabilities
provided by GitHub.

------------------------------------------------------------------------

# Architectural Decision

The Core of IACodeEditors should model GitHub as a **Platform
Provider**, not merely as a Git client or REST API wrapper.

``` text
                GitHub Platform Provider
                        (gh)
                            │
      ┌─────────────────────┼──────────────────────┐
      │                     │                      │
      ▼                     ▼                      ▼
 Git Repository        GitHub Services      AI Assistance
 (Git executable)      REST / GraphQL         Copilot
      │
      ▼
 SSH Transport
```

------------------------------------------------------------------------

# Responsibilities

## Git

Responsible for local repository management.

Examples:

-   add
-   commit
-   merge
-   rebase
-   status
-   branch
-   tag
-   push
-   fetch

Git remains the authoritative implementation of the repository model.

## SSH

Responsible for secure transport and commit signing.

SSH is independent from GitHub authentication.

## GitHub Platform

Responsible for:

-   Repositories
-   Pull Requests
-   Issues
-   Releases
-   Actions
-   Discussions
-   Packages
-   Gists
-   REST API
-   GraphQL API

## Copilot

Copilot is modelled as another capability of the GitHub Platform
Provider rather than a separate provider.

Future experiments will characterize installation, authentication,
licensing and command capabilities.

------------------------------------------------------------------------

# Experimental Evidence

The experiments demonstrated that:

-   OAuth authentication is independent of SSH.
-   Credentials are stored in the operating system keyring.
-   `gh repo clone` respects the configured Git transport.
-   The cloned repository is a standard Git repository.
-   Git commands continue working normally after cloning.

This confirms that GitHub CLI orchestrates Git instead of replacing it.

------------------------------------------------------------------------

# Design Principle

Model capabilities rather than individual commands.

Core capabilities include:

-   Repository Management
-   Pull Request Management
-   Issue Management
-   Workflow Management
-   Release Management
-   AI Assistance

Providers decide how those capabilities are implemented.

------------------------------------------------------------------------

# Benefits

-   Reduced coupling to a specific CLI.
-   Easier support for GitHub, GitLab, Forgejo and Gitea.
-   Clear separation between local repository concerns and platform
    concerns.
-   Git remains the repository engine.
-   AI assistance becomes another platform capability.

------------------------------------------------------------------------

# Next Experiment

Characterize `gh copilot`:

1.  Installation.
2.  Authentication.
3.  License detection.
4.  Commands.
5.  Internal architecture.
6.  Relationship with GitHub CLI.
7.  Relationship with Git.

------------------------------------------------------------------------

# Guiding Principles

> Characterize before constraining.

> Model capabilities, not commands.

> Keep provider responsibilities explicit.
