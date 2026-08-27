# sayelf-build-principles

**A portable build-time Skill for AI coding agents and agent platforms.**

> **先证明值得造，再用最简单的方法把真正需要的东西造好。**  
> Prove it is worth building. Then build only what matters.

Sayelf Build Principles is a pre-development Skill for building **Agents, Skills, Tools, and Systems**. It keeps development from becoming duplicate, overbuilt, cloud-heavy, or difficult to use. The core is platform-neutral and can be loaded by Claude Code, Tencent WorkBuddy / CodeBuddy, Codex, and other hosts that support Markdown-based Skills.

## Core Functions

| Gate / principle | What it enforces |
| --- | --- |
| **Step 0 — Innovation Gate** | Search, compare, distill, find the gap, then decide: `Duplicate`, `Integrate`, `Improve`, `Differentiate`, or `Innovate`. **Improve is the minimum bar for new development.** |
| **01 — Negative Entropy** | Keep only the necessary **objects, functions, and interactions**; remove architecture, functional, and interaction entropy. |
| **02 — Modular / Pluggable** | Keep the Core platform-independent; replace, enable/disable, upgrade, or isolate platform-specific capabilities. |
| **03 — Local-first** | Prefer local rules, parsing, analysis, caching, indexing, deduplication, and state management before cloud or model calls. |
| **04 — Dynamic by State** | Schedule work from state, change rate, and importance instead of fixed brute-force polling. |
| **05 — Intelligent Automation** | Automate discovery through recommendation while keeping `Observation`, `Inference`, `Hypothesis`, and `Fact` distinct. |
| **06 — Evidence-driven Evolution** | Upgrade through `Observe → Challenge → Validate → Canary → Promote`, with versioning, traceability, and rollback. |
| **07 — WebUI as Human Interface** | Build a WebUI only when the real function needs a human-facing visual interface; otherwise do not add one. When present, expose complexity progressively. |
| **Simple-first** | Choose the least complex reliable option that satisfies the real task. |

When a WebUI is justified, the default user path is:

**Open → Input → Execute → Result**

The system may be sophisticated behind the interface. A normal user should not need to understand the architecture, plugins, models, parameters, or logs to complete the core task.

The default path applies when a WebUI is justified. A Skill, Agent, Tool, or System that does not need visual interaction should not create a WebUI; use its simplest suitable interface instead.

## Portable by design

The portable unit is the folder containing this `SKILL.md`. Its frontmatter uses only the common `name` and `description` fields, and its body does not require a specific model, tool API, shell, hook, environment variable, or vendor command.

Use the same folder through the host's supported Skill mechanism:

- **Claude Code:** place it at `.claude/skills/sayelf-build-principles/` for a project Skill or `~/.claude/skills/sayelf-build-principles/` for a personal Skill.
- **Tencent CodeBuddy Code:** place it at `.codebuddy/skills/sayelf-build-principles/` or `~/.codebuddy/skills/sayelf-build-principles/`.
- **Tencent WorkBuddy and other hosts:** import or install the folder through the host's Skill management or marketplace surface.

If a host requires a wrapper, add only the host-specific invocation or packaging metadata and keep this `SKILL.md` as the single source of truth. `AGENTS.md` is an optional concise adapter for hosts that read project-level `AGENTS.md`; it is not required for portability.

---

## Step 0 — Innovation Gate

Before writing a new Agent, Skill, Tool, System, or major feature, search GitHub and the open-source ecosystem:

**Search → Compare → Distill → Gap Analysis → Differentiate → Decide**

Then make exactly one decision:

| Decision | Meaning | Default action |
| --- | --- | --- |
| `Duplicate` | A mature solution already solves the need with no meaningful difference. | Reuse it; do not build a duplicate. |
| `Integrate` | Existing capabilities solve the parts; the missing value is composition or an interface. | Connect them; do not rewrite them. |
| `Improve` | An existing solution has a specific, measurable weakness or opportunity. | Build only the smallest verifiable improvement. |
| `Differentiate` | Similar solutions exist, but the proposed mechanism or workflow is materially different. | Build a focused MVP around that difference. |
| `Innovate` | No effective matching solution was found. | Validate the original hypothesis before expanding it. |

No self-built replacement is justified without a measurable improvement, meaningful differentiation, or validated innovation. Subjective claims such as “better” are not enough; state the dimension to improve, such as local control, token use, latency, cost, dependencies, evidence quality, compatibility, reliability, or usability.

## The seven principles

### 01 — Negative Entropy

Retain only what is necessary to complete the real task and close its evidence loop: **Object + Function + Interaction**.

- **Architecture Entropy:** remove unnecessary objects, state, modules, dependencies, and abstractions.
- **Functional Entropy:** remove features that do not move a real task toward a result.
- **Interaction Entropy:** hide technical complexity the user does not need to understand or operate.

### 02 — Modular / Pluggable

Keep the Core independent from specific platforms. Platform, collector, analyzer, model, storage, publisher, and similar capabilities should be replaceable, independently enabled or disabled, upgradeable, and isolated when appropriate.

### 03 — Local-first

Prefer local execution for deterministic rules, transcription, frame extraction, metrics, parsing, caching, indexing, deduplication, and state management. Use cloud services or large models when local capability is insufficient or the evidence justifies the cost.

**Less Token · Less Cloud · Less Latency · Less Cost · More Control**

### 04 — Dynamic by State

Do not use fixed brute-force polling as the default. Select the next check from:

**State → Change Rate → Importance → Next Check**

Increase frequency for fast-changing important content, reduce it for stable content, sleep when nothing changes, and wake on important changes.

### 05 — Intelligent Automation

Automation may discover, collect, process, compare, detect, hypothesize, and recommend. It must preserve the epistemic boundary:

**Observation → Inference → Hypothesis → Fact**

An unverified hypothesis must never be presented or promoted as fact.

### 06 — Evidence-driven Evolution

Collection may be time- or state-driven, but capability upgrades must be evidence-driven:

**Observe → Challenge → Validate → Canary → Promote**

Every promotion should be **versioned, traceable, and rollbackable**. If it cannot be validated, it does not get promoted.

### 07 — WebUI as Human Interface

First decide whether the real function needs a human-facing visual interface. Build a WebUI only when it materially improves task completion, visibility, control, or evidence for the target users. If it is not needed, do not build one.

When a WebUI is justified, it is the system's human execution interface. The visible workflow should follow:

**Input → Processing → Evidence → State → Decision → Action → Outcome**

Keep the ordinary path to **Open → Input → Execute → Result**. Put evidence, plugins, models, parameters, logs, and developer controls behind progressive disclosure such as advanced settings or Developer Mode.

## Simple-first

When several approaches can satisfy the real task, evaluate them in this order:

**Existing Capability → Native Solution → Lightweight Tool → Mature Dependency → Complex Framework → Custom Complex Technology**

Complexity is allowed only when simpler options have been tested or ruled out by evidence.

## One rule

> **Don't build because you can. Build because the evidence says you should.**

## Use this Skill

Read [SKILL.md](SKILL.md) before developing or materially changing an Agent, Skill, Tool, or System. [AGENTS.md](AGENTS.md) provides an optional concise project-level gate for hosts that support that convention.
