# Game Goal

简体中文 | [English](README.en.md)

把游戏想法或试玩反馈整理成可执行、可验收的 Goal：目标与品质、证据、执行授权、停止条件及留存。起草后由用户确认，不自动授权开发或发布。

## 安装与使用

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

手动安装时，只复制 `skills/game-goal/` 到宿主的 Skill 目录；不要把仓库外层文档放进去。已有安装按原位置更新，多个宿主可通过目录链接共用一份。

明确要求起草、审阅或精简 Goal 时使用；普通方案、反馈处理与小修改不触发。也可以直接说“用 game-goal 整理这些反馈”。执行方式与宿主能力在任务开始时核实。

## 三份核心文档

- [入口与 Goal 骨架](skills/game-goal/SKILL.md)：边界、流程、确认与结果表。
- [品质与验收](skills/game-goal/references/quality-bars.md)：成品标准、回归保护、证据与过程清理。
- [编排与执行](skills/game-goal/references/orchestration.md)：L0–L3、授权、预算、停止条件与执行模板。

附带 `agents/openai.yaml` 调用配置。附录按任务读取；独立执行的 Goal 写全适用约定，不要求执行者另找 Skill。功能检查、评分与预算用尽都不能代替品质验收。

## 痛点与演变

[痛点与改变](docs/lessons.md)记录实际遇到的问题、规则调整及局限，面向维护者，不属于 Skill，也不是第二份规则来源。每次调整 Skill 同步维护相关条目，同类问题合并更新，不逐次追加记录，也不把记录放回 Skill。具体见 [仓库维护约定](AGENTS.md)。

[AI 游戏开发框架](https://github.com/Cooperzheng/ai-game-dev-framework)负责项目设计、实现和验证记录；本 Skill 负责起草与审阅 Goal，两者可独立使用。已有项目结构直接沿用。

## 许可

[MIT](LICENSE)。Copyright (c) 2026 Cooperzheng。
