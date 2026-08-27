# AGENTS.md

This is an optional project-level adapter for hosts that read `AGENTS.md`. The portable source of truth is [SKILL.md](SKILL.md); load it through the host's supported Skill mechanism before creating or materially changing an Agent, Skill, Tool, System, major feature, automation boundary, dependency, or WebUI workflow.

Project-level hard gates:

1. Run **Step 0 — Innovation Gate**: search, compare, distill, identify the gap, and classify the idea as `Duplicate`, `Integrate`, `Improve`, `Differentiate`, or `Innovate`.
2. `Improve` is the minimum threshold for new self-built functionality. Without a measurable improvement, meaningful differentiator, or validated innovation, reuse or integrate instead.
3. Complete the **Build Decision Record** in `SKILL.md` before coding. Define the real task, success evidence, minimum Core, boundaries, state behavior, epistemic labels, evolution/rollback, simplest implementation, and what is not being built.
4. Apply the eight principles: negative entropy across architecture/function/interaction; modular and pluggable boundaries; local-first execution; state-driven work; evidence-bounded automation; evidence-driven evolution; WebUI as the human interface when the real function requires it; and local/sensitive data sovereignty.
5. Keep local, internal, sensitive, restricted, and unknown data inside the local trust boundary. Never upload it to GitHub or any public network, including through commits, pushes, repositories, pull requests, issues, releases, packages, websites, screenshots, logs, archives, metadata, or quoted content. Credentials and secrets must never be uploaded.
6. Before GitHub or public-network publication, allow only content explicitly classified `Public` after reviewing the staged diff and every release artifact. Missing classification or leak evidence blocks transfer; encoding, compression, screenshots, or transformation cannot bypass the gate.
7. Decide whether a WebUI is needed before building one. If needed, keep the ordinary user path **Open → Input → Execute → Result** and put technical complexity behind progressive disclosure; if not needed, do not create one.
8. Keep changes minimal and verify the stated success measure before declaring completion. Report residual risk and untested behavior.

Do not expand this file with the full Skill. Update `SKILL.md` when the executable development protocol changes; keep this file limited to host-level enforcement.
