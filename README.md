# Game Goal

简体中文 | [English](README.en.md)

把游戏想法或试玩反馈整理成一页能执行的 Goal：做什么、怎么算好、谁来判断、边界与何时停。起草后由用户确认，不自动授权开发或发布。

## 安装与使用

```sh
npx skills add Cooperzheng/game-goal --skill game-goal
```

手动安装时，只复制 `skills/game-goal/` 到宿主的 Skill 目录；不要把仓库外层文档放进去。已有安装按原位置更新，多个宿主可通过目录链接共用一份。

明确要求起草、审阅或精简 Goal 时使用；普通方案、反馈处理与小修改不触发。也可以直接说“用 game-goal 整理这些反馈”。执行方式与宿主能力在任务开始时核实。

## 内容

只有一份 [SKILL.md](skills/game-goal/SKILL.md)，附带 `agents/openai.yaml` 调用配置。Goal 只写执行者无从知道的事：想要的成品、已认可的红线、边界、何时找用户。每项写明谁来判：硬指标由测试和遥测判，观感和手感由用户判；少测少拍，截图录屏的形式和数量由执行者定；只写总工时，达标、到上限或卡住就停。

## 痛点与演变

[痛点与改变](docs/lessons.md)记录实际遇到的问题、规则调整及局限，面向维护者，不属于 Skill，也不是第二份规则来源。每次调整 Skill 同步维护相关条目，同类问题合并更新，不逐次追加记录，也不把记录放回 Skill。具体见 [仓库维护约定](AGENTS.md)。

[AI 游戏开发框架](https://github.com/Cooperzheng/ai-game-dev-framework)负责项目设计、实现和验证记录；本 Skill 负责起草与审阅 Goal，两者可独立使用。已有项目结构直接沿用。

## 许可

[MIT](LICENSE)。Copyright (c) 2026 Cooperzheng。
