# GM Running Copy

一个用于将 TRPG 模组整理成主持人备团材料和可编辑主持工作副本的 Codex Skill。

这个项目面向需要从 `.docx` 或 `.pdf` 模组全文中备团的主持人。它会先帮助主持人理解模组，再根据需要把模组转化成一份实用的工作副本：包含内联主持提示、线索支持、场景流程、时间与局势展示、NPC/地点卡，以及风险分析。

当前设计尤其贴近中文 TRPG 模组备团工作流，适用于 CoC、D&D、永远的后日谈 / Nechronica，以及其他以模组或剧本为核心的桌面角色扮演游戏。

## 项目一句话介绍

把 TRPG 模组转化为主持人可直接使用的总览、分析文件和带有内联备团提示的可编辑工作副本。

## 这个 Skill 能做什么

`gm-running-copy` 支持三种主要工作流：

1. **快速读懂**
   - 从主持人视角快速理解模组。
   - 生成总览、阅读指南、场景流程、线索矩阵、NPC/地点卡、时间展示和风险地图。

2. **主持工作副本**
   - 保留原始模组。
   - 创建一份可编辑的主持增强版。
   - 在原文附近插入主持用内联标记和备团提示。

3. **参考已有备团笔记**
   - 比较原模组和用户已有的备团版本。
   - 推断用户的备团风格。
   - 按同样风格继续处理后续内容。

## 仓库结构

```text
gm-running-copy/
  SKILL.md
  agents/
    openai.yaml
  references/
    experience-focus.md
    marker-style.md
    output-templates.md
    personalization.md
    time-and-state.md

docs/
  gm-running-copy-skill-design.md
  gm-running-copy-SKILL-draft.md

README.md
README.en.md
```

关键文件：

- `gm-running-copy/SKILL.md`：Codex Skill 的主入口。
- `gm-running-copy/references/output-templates.md`：输出文件模板和编号阅读顺序。
- `gm-running-copy/references/time-and-state.md`：时间线、时钟和局势面板设计。
- `gm-running-copy/references/marker-style.md`：内联主持标记说明。
- `gm-running-copy/references/experience-focus.md`：以“模组承诺的桌面体验”为中心的分析方法。
- `gm-running-copy/references/personalization.md`：根据用户个人备团风格进行调整的规则。
- `README.en.md`：英文版 README。

## 安装方式

将 `gm-running-copy` 文件夹复制到你的 Codex skills 目录中。

Windows 上通常是：

```text
C:\Users\<你的用户名>\.codex\skills\gm-running-copy
```

然后重新打开 Codex 会话，或刷新 skill 发现。之后可以通过下面的方式调用：

```text
$gm-running-copy
```

示例提示词：

```text
使用 $gm-running-copy 帮我备这个 TRPG 模组，生成主持总览、场景流程、线索矩阵，并在需要时创建主持工作副本。
```

## 推荐用法

### 快速读懂模组

适合刚拿到模组，还不想立刻改原文的时候。

```text
使用 $gm-running-copy 快速读懂这个模组。先不要改原文，只生成带编号的 analysis 文件。
```

这个模式会帮助你回答：

- 这个模组讲什么？
- 真相是什么？
- 玩家会怎么推进？
- 哪些 NPC、地点、线索最重要？
- 哪里可能卡团？
- 哪些原文段落必须亲自细读？

### 生成主持工作副本

适合已经决定要跑这个模组，希望把原文整理成临场可用版本的时候。

```text
使用 $gm-running-copy 帮我备这个模组。请保留原文备份，创建主持增强版，并在原文附近插入【NC处理】【线索】【信息控制】【偏航处理】等内联标记。
```

### 参考已有备团风格

适合你有“原模组 + 自己改过的备团笔记”的情况。

```text
使用 $gm-running-copy。第一个文件是原模组，第二个文件是我的备团笔记。请先比较我的改法，学习我的备团风格，再按同样风格继续处理新章节。
```

## Analysis 文件阅读顺序

`02-analysis/` 里的文件会带编号，方便主持人按顺序消费：

```text
01-GM-Brief.md
02-Reading-Guide.md
03-Scene-Flow.md
04-Timeline.md
05-Situation-Board.md
06-Clue-Matrix.md
07-NPC-Cards.md
08-Location-Cards.md
09-Risk-Map.md
```

不是每个模组都需要所有文件。如果某个文件不适合当前模组，可以跳过，但后续编号保持不变。

例如：如果一个氛围型模组不需要 `05-Situation-Board.md`，那么不要把 `06-Clue-Matrix.md` 改名为 `05-Clue-Matrix.md`。这样可以保持固定的阅读习惯。

推荐消费顺序：

1. `01-GM-Brief.md`：先建立全局理解。
2. `02-Reading-Guide.md`：知道原文哪些地方要细读。
3. `03-Scene-Flow.md`：理解模组实际如何推进。
4. `04-Timeline.md` / `05-Situation-Board.md`：掌握时间、局势和角色位置。
5. `06-Clue-Matrix.md`：检查线索链。
6. `07-NPC-Cards.md`：理解 NPC 的目标、秘密和反应。
7. `08-Location-Cards.md`：理解地点如何运行。
8. `09-Risk-Map.md`：决定哪些地方需要改稿或加强。

临场跑团时，则通常以主持增强版原文为主，辅以 `05-Situation-Board.md`、`06-Clue-Matrix.md` 和 `07-NPC-Cards.md` 速查。

## 内联主持标记

本 skill 使用便于搜索的中文全角标记：

```text
【NC处理】
【可朗读】
【信息控制】
【线索】
【共创】
【机制提示】
【偏航处理】
【删改建议】
【节奏提示】
【伏笔回收】
```

可选标记包括：

```text
【战斗调整】
【难度提示】
【安全工具】
【玩家提醒】
【开场准备】
【结局处理】
【改编方向】
```

这些标记的目标不是把原文洗成模板，而是把主持人真正需要的判断、提醒和临场工具放到最接近使用位置的地方。

## 设计理念

这个 skill 不是单纯的模组总结器，也不是自动魔改器。

它采用两阶段思路：

1. **先读懂模组。**
2. **只有在用户需要时，才改造成主持工作副本。**

它也避免根据系统做刻板判断。

CoC 模组不一定只是线索工程；D&D 模组不一定只是遭遇平衡；一个情感或演出型模组可能更需要顺序、情绪和舞台支持，而不是严格时间卡点。

因此，skill 会根据模组承诺的桌面体验选择备团工具，例如：

- 调查结构
- 战斗冒险
- 情感戏剧
- 恐怖悬疑
- 沙盒与阵营
- 演出 / 高潮场景
- 严格时钟、相对时钟、顺序轨道或背景真相时间线

## 时间展示策略

不同模组需要不同形式的时间管理。

严格、多地点、多 NPC 行动的调查模组适合：

```text
Strict Clock + Situation Board + Backstory Timeline
```

氛围轻松、重点在场景顺序和情绪递进的模组适合：

```text
Sequence Track + Backstory Timeline
```

如果模组中有大量离屏 NPC 行动、地点状态变化和时间差分，就生成 `05-Situation-Board.md`。

如果模组只需要保证事情按顺序发生，就不要强行生成复杂局势面板。

## 当前限制

- 本仓库提供的是 Codex Skill 指令和参考文档，不是独立应用程序。
- DOCX / PDF 抽取、渲染和编辑依赖宿主 Codex 环境中的文档工具。
- 当前版本没有包含确定性辅助脚本。
- 生成的主持工作副本仍应由主持人在跑团前亲自审阅。
- 对受版权保护的商业模组，使用者应自行确保其处理、复制和分享方式符合授权要求。

## 发布前建议

如果要进一步完善公开发布版本，可以考虑增加：

- `LICENSE` 文件。
- 使用非版权样例模组制作的输入/输出示例。
- Quick Read 和 Running Copy 两种模式的演示。
- 多个真实模组测试后的版本标签。
- 自动化脚本，用于创建标准输出目录或辅助提取 DOCX 段落结构。

## 状态

实验性但可用。

这个 skill 已围绕真实 TRPG 备团需求进行设计，并针对严格时间线模组、氛围/演出型模组、以及用户已有备团笔记工作流做过迭代。
