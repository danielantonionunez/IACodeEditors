# Planning Game

## Project

IACodeEditors

**Practice:** Planning Game

**Owner (Accountable):** Daniel Nuñez

**Authors:** Daniel Nuñez, Ian (AI Collaborator)

---

# Purpose

Planning is performed continuously through conversation.

Instead of maintaining a heavyweight planning tool, planning emerges
naturally during collaborative work and is preserved when necessary as
lightweight artifacts.

The objective is to minimize planning overhead while maximizing shared
understanding.

---

# Philosophy

Planning is not considered a separate phase.

Planning occurs continuously while exploring ideas,
making decisions,
performing experiments,
designing architecture,
or implementing functionality.

Every technical discussion may potentially refine the plan.

---

# Continuous Planning

The project intentionally avoids rigid planning cycles.

Planning evolves incrementally as new knowledge appears.

This allows:

- immediate replanning
- continuous prioritization
- rapid architectural adaptation
- incorporation of experimental results

Planning therefore becomes part of the daily work instead of a scheduled activity.

---

# Conversation as Planning

The primary planning mechanism is conversation between collaborators.

Participants continuously negotiate:

- objectives
- priorities
- alternatives
- risks
- trade-offs
- implementation order

This preserves one of the original intentions of XP:

continuous negotiation instead of static plans.

---

# AI-assisted Planning

The AI collaborator participates by helping transform ideas into
structured planning artifacts when needed.

Examples include:

- User Stories
- Features
- Epics
- Acceptance Criteria
- Definition of Ready
- Definition of Done
- Technical Tasks
- Research Tasks
- Architecture Decisions
- Risk Lists

These artifacts are generated only when they provide value.

---

# Markdown as Planning Persistence

Markdown documents are not the planning process.

Markdown documents persist planning decisions.

They capture:

- decisions
- rationale
- experiments
- alternatives considered
- conclusions
- future work

The planning itself occurs during collaboration.

Markdown provides durable knowledge.

---

# Event Sourcing Analogy

Planning naturally generates a sequence of conversational events.

Those events can later be materialized into Markdown documents.

Conversation

↓

Planning Events

↓

Markdown

↓

Project Knowledge

↓

Future Reconstruction

The Markdown documents therefore act similarly to projections in an
Event Sourcing architecture.

They preserve the evolution of thought without requiring the complete
conversation to remain available.

---

# Planning Without Dedicated Tools

At the current stage the project intentionally avoids mandatory
planning software.

Tools such as:

- Super Productivity
- Trello
- Jira
- Azure Boards

remain optional.

The current conversational workflow has proven sufficient while
maintaining extremely low planning overhead.

---

# Knowledge Recovery

Because planning knowledge is preserved in Markdown documents, future
planning sessions can recover context from multiple sources.

Examples include:

- AI contextual memory
- Markdown documentation
- Architecture documentation
- Historical conversations
- Experimental results

This reduces dependence on large conversational contexts or token
availability.

---

# Dynamic Artifact Generation

Planning artifacts may be generated at any time from existing
knowledge.

Examples:

Conversation

↓

Feature

↓

User Stories

↓

Acceptance Criteria

↓

Tasks

↓

Definition of Done

The reverse process is also possible.

High-level planning may be reconstructed from detailed artifacts.

---

# Future Team Collaboration

The planning model naturally supports mixed teams.

Examples include:

- developers with AI assistance
- developers without AI assistance
- business stakeholders
- architects

Markdown artifacts become the common communication language between
all participants.

This allows AI-generated planning to integrate naturally into
traditional software development teams.

---

# Planning Without Estimates

The project intentionally avoids Story Points.

Velocity is not used.

The project follows ideas advocated by practitioners such as
Ron Jeffries, who has repeatedly explained why Story Points often
become organizational metrics instead of planning aids.

Observed issues include:

- false precision
- estimation bias
- metric gaming
- velocity misuse
- planning overhead

The project therefore prefers understanding work over estimating work.

---

# Towards NoEstimates

Future planning may adopt NoEstimates-inspired techniques.

Examples include:

- work classification
- similarity grouping
- historical comparison
- throughput observation
- completed work analysis
- probabilistic forecasting

Forecasts should emerge from observed data instead of subjective
estimations.

---

# Experimental Feedback Loop

Every completed experiment immediately influences future planning.

Experiment

↓

Knowledge

↓

Planning

↓

Implementation

↓

New Experiment

Planning therefore continuously improves as the project gains a better
understanding of the ecosystem.

---

# Benefits

This planning approach provides:

- continuous planning
- minimal overhead
- durable knowledge
- rapid adaptation
- AI-assisted documentation
- future automation
- enterprise compatibility
- planning based on evidence

---

# Key Insight

Planning is no longer a meeting.

Planning is a continuous knowledge flow.

Conversation creates decisions.

Decisions become knowledge.

Knowledge becomes reusable planning.

The project therefore plans continuously while simultaneously building
its long-term knowledge base.