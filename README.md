# Game Goal

用于起草、审阅和精简游戏开发 Goal 的中文 Skill，覆盖功能范围、玩家体验、美术视听目标、验证证据和停止条件。

## 安装

下载本仓库，将 `SKILL.md`、`agents/` 和 `references/` 放入宿主的 `skills/game-goal/` 目录。Codex 可使用 `$CODEX_HOME/skills/game-goal/`；未自定义时通常为 `~/.codex/skills/game-goal/`。重新打开会话后检查 Skill 是否可用。

## 使用

明确点名调用，例如：

```text
$game-goal 帮我起草一个游戏 MVP 的 Goal，先明确玩法、体验、美术目标和验收证据。
$game-goal 帮我检查这份 Goal，只补关键缺口，保持精简。
$game-goal 帮我精简这份 Goal，保留已确认边界与具体案例。
```

默认关闭隐式调用。此 Skill 用于设计参考与查漏补缺；调用本身不授权开发、修改项目、发布或启动自主循环。宿主的权限、预算和停止规则优先。

## 与 AI 游戏开发框架搭配

[AI 游戏开发框架](https://github.com/Cooperzheng/ai-game-dev-framework)用于在持续开发中保存目标、维护设计与实现，并对照实际体验检查交付。game-goal 用于起草或审阅这些目标，两者可独立使用。

1. 明确调用 game-goal，写清功能范围、玩家体验、美术视听目标和验收证据。
2. 用户确认后，将整体要求归入游戏项目的 `docs/PROJECT.md`，模块要求归入对应的 `docs/modules/模块名/DESIGN.md`；已有等效结构直接沿用。
3. 后续按框架维护设计、实现与验证结果。未确认建议保留为候选或 AI 当前方案；目标调整后更新所属正文，避免维护两份重复的 Goal。

框架不会自动安装或调用本 Skill。起草 Goal 与接入框架均不自动授权开发或发布。

## 内容

- [SKILL.md](SKILL.md)：入口与使用边界。
- [设计参考](references/design-checks.md)：目标、一致性、证据、迭代和停止条件。
- [两份范例](references/examples.md)：首个 MVP 与单模块改进模板。
- [品质线与失败反查](references/quality-bars.md)：完成定义、回归保护、美术与体验检查。
- [调用配置](agents/openai.yaml)：关闭隐式调用。

模板应按项目取舍，未知项保留待定；测试和评分不能替代真实游玩与用户判断。范例不构成品质保证。
