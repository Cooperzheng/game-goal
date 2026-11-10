# Game Goal

[简体中文](README.md) | English

A Chinese-language skill for turning game ideas and playtest feedback into a one-page executable goal: what to build, what good looks like, who judges it, the boundaries and when to stop. Drafting requires user confirmation before implementation; it does not authorize publishing.

## Install and use

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

For manual installation, copy only `skills/game-goal/` into your host's skill directory. Keep repository documentation outside the installation. Existing installations can retain their location; multiple hosts may share one copy through directory links.

Use it to draft, review, or condense a long-running game development goal, not for ordinary plans or small fixes. Verify execution mechanisms and host capabilities when starting the task.

## Contents

A single [SKILL.md](skills/game-goal/SKILL.md) plus `agents/openai.yaml` for invocation policy. A goal states only what the executor cannot know: the intended product, the approved red lines, the boundaries, and when to come back to the user. Each item names its judge: hard metrics for tests and telemetry, the user for look and feel. Few test runs and few captures; the executor decides the form and number of captures. One total time cap; stop when the bar is met, the cap is reached, or work is stuck.

## Lessons and changes

[Lessons and changes](docs/lessons.md) records anonymized problems, decisions, and limitations for maintainers. Update the relevant entry alongside skill changes; merge recurring issues into existing entries rather than appending a new log each time. Keep these records outside the installed skill. They are not a second source of rules. See [repository maintenance rules](AGENTS.md).

The [AI game development framework](https://github.com/Cooperzheng/ai-game-dev-framework) maintains project design, implementation, and verification records; this skill drafts and reviews goals. They can be used independently.

## License

[MIT](LICENSE). Copyright (c) 2026 Cooperzheng.
