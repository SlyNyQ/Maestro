# Maestro
Multi-agent AI Dungeon Master system using coordinated LLMs for dynamic, rule-driven tabletop campaigns.
## Overview

**Maestro** is a multi-agent AI Dungeon Master system designed to run dynamic, tabletop-style role-playing campaigns using coordinated large language models (LLMs).

Rather than relying on a single model to simulate all reasoning and storytelling, Maestro treats each model as a **specialized agent** with a defined role, personality constraints, and authority scope. A central orchestrator governs how these agents collaborate to generate coherent narratives, enforce rules, and adapt to player choices.

The system is built to support multiple tabletop rule systems, adjustable difficulty levels, and player-selected narrative paths, while remaining scalable from a solo developer prototype to a small multi-engineer team.

---

## Core Goals

### 1. Implement True Agentic AI (Not Prompt Layering)

Maestro’s primary goal is to demonstrate **real agentic orchestration**, where:

- Multiple LLMs operate as independent agents
- Each agent has a defined responsibility and behavioral boundary
- A central orchestrator controls routing, arbitration, and synthesis

The system avoids single-model “multi-personality” prompting in favor of explicit agent governance and message passing.

---

### 2. Treat Narrative Paths as System-Level Controls

Players can enable or prioritize narrative “paths” (e.g. Skeptic, Pacifist, Sage, Hero), each mapped to a distinct agent with its own reasoning style and narrative bias.

These paths:
- Influence how events are interpreted
- Shape moral framing, risk tolerance, and tone
- Can be combined, weighted, or suppressed dynamically

Narrative direction is treated as a **configurable control layer**, not a static script.

---

### 3. Enforce Separation of Story, Rules, and Judgment

Maestro enforces a strict separation of concerns to maintain consistency and fairness:

- **Narrative Agents** generate possible story outcomes
- **Rules Agents** retrieve and enforce tabletop mechanics using RAG
- **Judge / Orchestrator Agents** resolve conflicts, apply difficulty, and finalize outcomes

This prevents creativity from violating rules and prevents rules from flattening narrative depth.

---

### 4. Support Multiple Tabletop Systems via Retrieval (RAG)

Maestro does not train models directly on tabletop rulebooks.

Instead:
- Rulebooks are stored externally
- Relevant rules are retrieved dynamically via Retrieval-Augmented Generation (RAG)
- Only contextually necessary rules are injected per turn

This allows rapid support for new systems, clear legal boundaries, and cleaner model contexts.

---

### 5. Implement Difficulty as a Policy Layer

Difficulty in Maestro is implemented as a **decision policy**, not a change in model capability.

Difficulty settings influence:
- Information availability
- Consequence severity
- Error tolerance
- Narrative generosity or hostility

This allows the same agents to support casual, tactical, or punishing campaigns without retraining.

---

### 6. Design for Solo Development and Team Scaling

Maestro is intentionally designed to be:
- Fully buildable and maintainable by a single developer
- Easily divisible into modules for a small engineering team

Clear module boundaries allow contributors from different engineering backgrounds to work independently without overlapping responsibilities.

---

### 7. Serve as a Reference Architecture for Agentic Systems

Beyond gameplay, Maestro aims to function as:
- A reference implementation for multi-LLM orchestration
- A practical learning platform for agent design patterns
- A technically defensible example of applied LLM engineering

The project prioritizes architectural clarity and correctness over feature sprawl.

---

## Non-Goals

To keep scope realistic, the following are explicitly out of scope for early versions:

- Real-time graphics engines
- Voice synthesis or speech recognition
- Automated fine-tuning of proprietary models
- Full commercial game deployment

These may be explored later but are not required to fulfill the core vision.

---

## Project Status

Maestro is an active design and development project.  
Early iterations prioritize correctness, modularity, and extensibility over breadth of features.
