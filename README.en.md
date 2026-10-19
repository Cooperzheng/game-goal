# Game Goal

[简体中文](README.md) | English

A Chinese-language skill for drafting, reviewing, and refining game development goals. It helps define feature scope, player experience, audiovisual quality, acceptance evidence, and stopping conditions before committing to implementation.

Use it for a first MVP, a focused module improvement, or a review of an existing goal. It is independent of game engine and genre. The skill and its reference documents are currently written in Chinese; this page provides an English introduction.

## Install

With the Skills CLI:

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

Or download this repository and copy `SKILL.md`, `agents/`, and `references/` into your host's `skills/game-goal/` directory. For Codex, use `$CODEX_HOME/skills/game-goal/`, usually `~/.codex/skills/game-goal/` when not customized. Keep `LICENSE` with redistributed copies. Start a new session and check that the skill is available.

## Use

Invoke the skill explicitly:

```text
$game-goal Draft a goal for a game MVP, covering gameplay, player experience, visual quality, and acceptance evidence.
$game-goal Review this goal. Address only important gaps and keep it concise.
$game-goal Shorten this goal while preserving confirmed boundaries and concrete examples.
```

The Codex configuration disables implicit invocation. Other hosts may handle invocation differently; explicitly request the skill and check the host's behavior. Invoking it does not authorize development, project edits, publication, or autonomous loops. Host permissions, budgets, and stopping rules take precedence.

## What a goal should make clear

- What the player can do, and what is outside the scope.
- How the core play experience should feel.
- What visual and audio quality should look and sound like, with relevant references.
- What evidence supports acceptance, and which judgments need a user playtest.
- Which verified behaviors must be preserved, and when stalled work should pause.

Adapt the references to the project. Keep unknowns provisional. Passing tests or receiving a favorable score does not establish that a game is enjoyable or meets its quality targets.

## Pair with AI Game Dev Framework

[AI Game Dev Framework](https://github.com/Cooperzheng/ai-game-dev-framework) maintains goals, design, implementation, and verification during ongoing development. Both tools work independently.

1. Explicitly invoke game-goal to draft or review the desired result.
2. After user confirmation, put project-wide requirements in the game's `docs/PROJECT.md` and module requirements in the corresponding `docs/modules/<module>/DESIGN.md`. Reuse equivalent existing structures.
3. Maintain changes in those documents through the framework. Keep unconfirmed suggestions as candidates or current AI proposals, and avoid maintaining duplicate Goal documents.

The framework does not automatically install or invoke this skill. Neither drafting goals nor adopting the framework authorizes development or publication.

## Contents

- [SKILL.md](SKILL.md): entry point and invocation boundaries.
- [Design checks](references/design-checks.md): goals, consistency, evidence, iteration, and stopping conditions.
- [Examples](references/examples.md): first MVP and module improvement templates.
- [Quality bars](references/quality-bars.md): completion criteria, regression protection, visuals, and experience checks.
- [Codex configuration](agents/openai.yaml): disables implicit invocation.

## License

[MIT](LICENSE). Copyright (c) 2026 Cooperzheng.
