---
name: sayelf-build-principles
description: Apply evidence-first, simple-first build gates when creating or materially changing a Codex or AI coding Agent, Skill, Tool, System, or its human-facing WebUI.
metadata:
  short-description: Build only what evidence justifies
---

# Sayelf Build Principles

Use this Skill before creating or materially changing an **Agent, Skill, Tool, System, or major feature**. It is a build-time decision and execution protocol, not a business framework or a prescribed technology stack.

## Trigger conditions

Activate when the request involves any of the following:

- a new Agent, Skill, Tool, System, product, or major capability;
- a new architecture, dependency, integration, plugin boundary, automation loop, or model/cloud service;
- a new or materially changed WebUI workflow;
- a proposal to replace, rebuild, or expand an existing solution.

For a small, local change with no new capability or design decision, apply the relevant principles proportionally and do not manufacture a large decision record.

## Hard stop before coding

Do not write implementation code until the Step 0 decision and the required pre-coding output are complete. If the request is a duplicate with no measurable improvement, stop and recommend reuse. If existing capabilities cover the need through composition, stop and recommend integration.

## Step 0 — Innovation Gate

Search GitHub, the open-source ecosystem, and the current workspace before proposing a new core implementation. Follow this sequence:

**Search → Compare → Distill → Gap Analysis → Differentiate → Decide**

Classify the proposal as exactly one of these:

| Decision | Test | Allowed action |
| --- | --- | --- |
| **Duplicate** | A mature solution already solves the real task without a meaningful gap. | Reuse; do not build a duplicate. |
| **Integrate** | Existing parts solve the need and only composition or an interface is missing. | Connect; do not rewrite the parts. |
| **Improve** | An existing solution has a specific, measurable weakness or opportunity. | Build the smallest verifiable optimization. |
| **Differentiate** | Similar solutions exist, but the proposed mechanism or workflow is materially different. | Build a focused MVP around the difference. |
| **Innovate** | No effective matching solution was found. | Validate the original hypothesis before expanding it. |

**Improve is the minimum self-development threshold.** “Better”, “more intelligent”, or “more complete” is not evidence. Name at least one measurable difference: local control, token use, latency, cost, dependency count, compatibility, reliability, evidence quality, automation boundary, or usability.

## Seven principles

### 01 — Negative Entropy

Keep only the **Object + Function + Interaction** required for the real task and its evidence loop.

- **Architecture Entropy:** remove unnecessary objects, state, modules, dependencies, and abstractions.
- **Functional Entropy:** remove features that do not move a real task toward a result.
- **Interaction Entropy:** remove user-facing complexity that does not help the user complete the task.

The default user path is **Open → Input → Execute → Result**. Complex internals may remain behind the interface; ordinary users should not need to understand them.

### 02 — Modular / Pluggable

Keep the Core platform-independent. Make platform, collector, analyzer, model, storage, publisher, and similar capabilities replaceable, independently enabled or disabled, upgradeable, and isolated where useful.

### 03 — Local-first

Prefer local execution for deterministic rules, parsing, transcription, frame extraction, metrics, caching, indexing, deduplication, and state management. Add cloud or model dependencies only when local capability is insufficient or evidence justifies them.

### 04 — Dynamic by State

Do not default to fixed brute-force polling. Choose the next check from **State → Change Rate → Importance → Next Check**. Increase frequency for fast-changing important content, reduce it for stable content, sleep when unchanged, and wake on important change.

### 05 — Intelligent Automation

Automation may **Discover → Collect → Process → Compare → Detect → Hypothesize → Recommend**, but it must keep **Observation → Inference → Hypothesis → Fact** distinct. Never promote an unverified hypothesis to fact.

### 06 — Evidence-driven Evolution

Capability upgrades follow **Observe → Challenge → Validate → Canary → Promote**. Promotions are **versioned, traceable, and rollbackable**. No validation means no promotion.

### 07 — WebUI as Human Interface

Treat WebUI as the human execution interface, not decoration. Make the user-facing chain **Input → Processing → Evidence → State → Decision → Action → Outcome**, while preserving **Open → Input → Execute → Result** as the ordinary path. Progressively disclose evidence, plugins, models, parameters, logs, and developer controls.

## Simple-first constraint

Choose the least complex reliable option that satisfies the real task, in this order:

**Existing Capability → Native Solution → Lightweight Tool → Mature Dependency → Complex Framework → Custom Complex Technology**

Increase complexity only after simpler options are tested or ruled out with evidence. Do not add speculative features, dependencies, abstractions, or architecture.

## Mandatory Development Sequence

1. **Discover:** run Step 0 and record the comparison, gap, and decision.
2. **Specify:** define the real user task, success measure, and evidence needed to call it complete.
3. **Reduce:** remove unnecessary architecture, functions, and interactions.
4. **Select:** choose the simplest reliable implementation and state what is deliberately not being built.
5. **Bound:** define the minimum Core and isolate optional or platform-specific capabilities as plugins where needed.
6. **Localize:** decide what runs locally and justify every cloud or model boundary.
7. **Model state:** define state, change signals, importance, and next-check behavior instead of fixed polling.
8. **Bound automation:** label observations, inferences, hypotheses, and facts; identify the validation evidence.
9. **Design the human path:** make WebUI follow Open → Input → Execute → Result; hide advanced controls behind progressive disclosure.
10. **Build the minimum slice:** implement only the smallest path that can produce the stated result.
11. **Verify and evolve:** run focused checks, record evidence, and promote changes only through validation, canary, versioning, and rollback readiness.

## Required Output Before Coding

Before implementation, provide a concise **Build Decision Record** in the task plan, issue, design note, or equivalent working record. It must contain:

```text
Idea / real task:
Closest existing projects or capabilities:
Step 0 decision: Duplicate | Integrate | Improve | Differentiate | Innovate
Measurable improvement or differentiator:
Success measure and required evidence:
Minimum Core:
Plugin boundaries (if any):
Local-first boundary:
State, change signals, and next-check rule:
Observation / inference / hypothesis / fact boundary:
Evolution, validation, canary, version, and rollback plan:
Default WebUI path: Open → Input → Execute → Result
Simplest reliable implementation:
Explicitly not building:
```

If a field is not applicable, write `N/A` with a reason. A missing measurable improvement or differentiator is a stop signal for new self-built functionality.

## Completion gate

Do not report completion until the implementation has a focused verification tied to the stated success measure. Report any untested behavior, unresolved evidence gap, or rollback limitation explicitly.
