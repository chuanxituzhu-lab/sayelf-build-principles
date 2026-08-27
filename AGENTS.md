# AGENTS.md

This is an optional project-level adapter for hosts that read `AGENTS.md`. The portable source of truth is [SKILL.md](SKILL.md); load it through the host's supported Skill mechanism before creating or materially changing an Agent, Skill, Tool, System, major feature, automation boundary, dependency, or WebUI workflow.

Project-level hard gates:

1. Run **Step 0 — Innovation Gate**: search, compare, distill, identify the gap, and classify the idea as `Duplicate`, `Integrate`, `Improve`, `Differentiate`, or `Innovate`.
2. `Improve` is the minimum threshold for new self-built functionality. Without a measurable improvement, meaningful differentiator, or validated innovation, reuse or integrate instead.
3. Complete the **Build Decision Record** in `SKILL.md` before coding. Define the real task, success evidence, minimum Core, boundaries, state behavior, epistemic labels, evolution/rollback, simplest implementation, and what is not being built.
4. Apply the seven principles: negative entropy across architecture/function/interaction; modular and pluggable boundaries; local-first execution; state-driven work; evidence-bounded automation; evidence-driven evolution; and WebUI as the human interface.
5. Keep the ordinary user path **Open → Input → Execute → Result**. Put technical complexity behind progressive disclosure.
6. Keep changes minimal and verify the stated success measure before declaring completion. Report residual risk and untested behavior.

Do not expand this file with the full Skill. Update `SKILL.md` when the executable development protocol changes; keep this file limited to host-level enforcement.
