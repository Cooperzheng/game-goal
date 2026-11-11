# Game Goal

简体中文 | [English](README.en.md)

帮你把游戏需求、试玩反馈和想看到的东西讲清楚，写成一页 Goal 交给 AI 长时间执行。它不规定 AI 怎么做：Goal 写要什么、关心什么、谁来判、不能动什么、何时停，实现与验证方法授权给执行者。起草后由你确认，不自动授权开发或发布。

## 安装与使用

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

手动安装时，只复制 `skills/game-goal/` 到宿主的 Skill 目录；不要把仓库外层文档放进去。已有安装按原位置更新，多个宿主可通过目录链接共用一份。

明确要求起草、审阅或精简 Goal 时使用；普通方案、反馈处理与小修改不触发。也可以直接说“用 game-goal 整理这些反馈”。执行方式与宿主能力在任务开始时核实。

## 内容

只有一份 [SKILL.md](skills/game-goal/SKILL.md)，附带 `agents/openai.yaml` 调用配置。判断一句话该不该写进 Goal：执行者不问你就没法知道的，写；执行者自己能判断好的，不写。观感和手感由你判，硬指标由测试判；怎么实现、测多少、拍多少交给执行者。

## 痛点与演变

[痛点与改变](docs/lessons.md)记录实际遇到的问题、规则调整及局限，面向维护者，不属于 Skill，也不是第二份规则来源。每次调整 Skill 同步维护相关条目，同类问题合并更新，不逐次追加记录，也不把记录放回 Skill。具体见 [仓库维护约定](AGENTS.md)。

[AI 游戏开发框架](https://github.com/Cooperzheng/ai-game-dev-framework)负责项目设计、实现和验证记录；本 Skill 负责起草与审阅 Goal，两者可独立使用。已有项目结构直接沿用。

## 许可

[MIT](LICENSE)。Copyright (c) 2026 Cooperzheng。
