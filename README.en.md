# Game Goal

[简体中文](README.md) | English

A Chinese-language skill for turning game ideas and playtest feedback into executable goals with quality criteria, evidence, authorization, stopping conditions, and retention. Drafting requires user confirmation before implementation; it does not authorize publishing.

## Install and use

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

For manual installation, copy only `skills/game-goal/` into your host's skill directory. Keep repository documentation outside the installation. Existing installations can retain their location; multiple hosts may share one copy through directory links.

Use it to draft, review, or condense a long-running game development goal, not for ordinary plans or small fixes. Verify execution mechanisms and host capabilities when starting the task.

## Three core documents

- [Entry point and goal outline](skills/game-goal/SKILL.md): scope, workflow, confirmation, and results.
- [Quality and acceptance](skills/game-goal/references/quality-bars.md): standards, regression protection, evidence, and cleanup between iterations.
- [Orchestration and execution](skills/game-goal/references/orchestration.md): L0–L3, authorization, budgets, stopping conditions, and a compact execution template.

Includes `agents/openai.yaml` for invocation policy. Read references as needed. A goal handed to another session must include all applicable agreements. Passing tests, higher scores, or an exhausted budget do not establish quality acceptance.

## Lessons and changes

[Lessons and changes](docs/lessons.md) records anonymized problems, decisions, and limitations for maintainers. Update the relevant entry alongside skill changes; merge recurring issues into existing entries rather than appending a new log each time. Keep these records outside the installed skill. They are not a second source of rules. See [repository maintenance rules](AGENTS.md).

The [AI game development framework](https://github.com/Cooperzheng/ai-game-dev-framework) maintains project design, implementation, and verification records; this skill drafts and reviews goals. They can be used independently.

## License

[MIT](LICENSE). Copyright (c) 2026 Cooperzheng.
