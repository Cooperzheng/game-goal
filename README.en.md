# Game Goal

[简体中文](README.md) | English

A Chinese-language skill for drafting, reviewing, and condensing game development goals. It turns playtest feedback or game ideas into a goal for long-running AI execution, covering feature scope, player experience, audiovisual quality, acceptance evidence, stopping conditions, and the run's orchestration level (L0–L3), authorization, and retention.

It works with hosts that support [Agent Skills](https://agentskills.io). Claude Code and Codex have dedicated execution appendices; other hosts fall back to a generic appendix. The skill and its references are written in Chinese; this page is an English introduction.

## Install

With the Skills CLI:

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

Or download this repository and copy `SKILL.md`, `agents/`, and `references/` into your host's skill directory, keeping the folder name `game-goal`:

- Codex: `~/.agents/skills/game-goal/` (some versions also read `$CODEX_HOME/skills/game-goal/`).
- Claude Code: `~/.claude/skills/game-goal/`, or `.claude/skills/game-goal/` inside a project.
- Other hosts: their skill directory.

If you use several hosts, keep one copy and link the other locations to it. Keep `LICENSE` with redistributed copies. Start a new session and check that the skill is available.

## Use

The skill triggers when you explicitly ask to draft, review, or condense a goal (a task document for a long-running AI execution); you don't need to name it, and you can also invoke it by name. Plain plans, feedback handling, and small changes don't trigger it; when the AI judges that something should be done through a goal, it says so first and then drafts the goal for you to review.

```text
Turn this playtest feedback into a goal: 1. The dash feels sluggish. 2. The boss stage is too hard.
$game-goal Draft a goal for a game MVP, covering gameplay, player experience, visual quality, and acceptance evidence.
/game-goal Review this goal. Address only important gaps and keep it concise.
```

Drafting reuses existing diagnosis and investigates only gaps that affect the goal or its feasibility. It presents a draft once scope, expected results, protected behaviors, and acceptance are clear enough to judge; implementation details are marked for verification during execution. References are read as needed and reused within the same conversation when unchanged. The goal briefly lists the host, level, usage, retention, and key choices to confirm. No files are edited or orchestration started before confirmation. Each goal ends with a results table (item, feedback number, status, evidence, gap), reused at delivery. Host permissions, budgets, and stopping rules take precedence.

To use it only when named:

- Codex: set `allow_implicit_invocation` to `false` in `agents/openai.yaml`.
- Claude Code: set `"skillOverrides": {"game-goal": "name-only"}` in settings (only the name is listed, so asking for game-goal by name still works), or `"user-invocable-only"` (only `/game-goal` works).

## Orchestration levels

| Level | Allowed orchestration |
|---|---|
| L0 | Main session only |
| L1 | Plus subagents: read-only reviewers, research, independent modules with disjoint files (default) |
| L2 | Plus scripted orchestration for listed scenarios, such as review panels, broad research, and batch checks |
| L3 | Plus session-wide autonomous orchestration, only for research, audit, or final acceptance, with user approval |

Each goal briefly states the recommended level, enabled mechanisms, their purposes, limits, and expected usage; unused mechanisms are grouped together. Level tradeoffs are explained only for complex plans, and detailed terms appear once in the goal. A plain "confirm" runs at L1 at most; L2 and L3 take effect only when the reply names the level. When the host lacks a capability, the goal states the actual level, what is lost, and how it compensates. By default, coupled visual systems (lighting, materials, post-processing, effects, scene art) are changed sequentially by the main session only.

Independent reviews, including blind reviews, have no separate default cap on cumulative reviewer assignments, review orchestration runs, or rounds per item. They operate within the confirmed overall budget. Two consecutive iterations with no verifiable improvement on the same gap pause only the affected module and its dependencies; independent work continues. Concurrency and per-round limits remain. A hard review quota is set only when the user explicitly requests one, with capacity reserved for final acceptance.

For quality goals, visuals are the core of acceptance: an item must first pass visual acceptance (normal gameplay view, side by side with references, cheap-look checklist cleared, independent review and user confirmation). Functional checks are only the entry condition, and an item that fails visual acceptance is never marked done because its features work or the budget ran out.

Collect only enough evidence to judge acceptance. Reuse valid evidence and keep only the current candidate's evidence, necessary comparisons, and key failure samples; record only necessary clips for items named in the goal. Agree on the run's temporary directory and cleanup scope when confirming the goal, then remove superseded artifacts during execution. Keep evidence still needed for acceptance, referenced results, or unresolved issues. Long-term archives follow project acceptance rules, defaulting to `dev-history/`; do not archive every iteration. Isolated working copies are used only as needed and removed at the end of the round.

## What a goal should make clear

- What the player can do, and what is outside the scope.
- How the core play experience should feel.
- What visual and audio quality should look and sound like, with relevant references.
- What evidence supports acceptance, and which judgments need a user playtest.
- Which verified behaviors must be preserved, and when stalled work should pause.

Adapt the references to the project. Keep unknowns provisional. Passing tests or receiving a favorable score does not establish that a game is enjoyable or meets its quality targets.

## Pair with AI Game Dev Framework

[AI Game Dev Framework](https://github.com/Cooperzheng/ai-game-dev-framework) maintains goals, design, implementation, and verification during ongoing development. Both tools work independently.

1. Use game-goal, automatically or by name, to draft or review the desired result.
2. After user confirmation, put project-wide requirements in the game's `docs/PROJECT.md` and module requirements in the corresponding `docs/modules/<module>/DESIGN.md`. Reuse equivalent existing structures.
3. Maintain changes in those documents through the framework. Keep unconfirmed suggestions as candidates or current AI proposals, and avoid maintaining duplicate Goal documents.

The framework itself does not install or invoke this skill. Neither drafting goals nor adopting the framework authorizes development or publication.

## Contents

- [SKILL.md](SKILL.md): when to use it, process, and output.
- [Orchestration levels and authorization](references/orchestration.md): levels, fallbacks, restricted areas, authorization clauses, and template.
- Host appendices: [Claude Code](references/host-claude-code.md), [Codex](references/host-codex.md), [other hosts](references/host-generic.md).
- [Design checks](references/design-checks.md): goals, consistency, evidence, iteration, and stopping conditions.
- [Examples](references/examples.md): playtest feedback batch, first MVP, and module improvement templates.
- [Quality bars](references/quality-bars.md): completion criteria, regression protection, visuals, and experience checks.
- [Codex configuration](agents/openai.yaml): implicit invocation switch.

Host appendices record the version they were verified against; after a host update, recheck them with the list at the end of each appendix.

## License

[MIT](LICENSE). Copyright (c) 2026 Cooperzheng.
