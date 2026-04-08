# tacit-mining

**Let AI truly understand you.** A Claude Code skill that extracts your tacit knowledge through structured dialogue.

> "We know more than we can tell." — Michael Polanyi, 1966

你给 AI 写了几千字的提示词，但它还是不懂你。问题不在 AI，在于你最重要的判断标准——你自己也说不清楚。

`tacit-mining` 基于 Polanyi 隐性知识理论和认知科学方法（CDM、Laddering、Repertory Grid），用结构化对话从你的**行为**中反推出你说不出来的判断标准。

## 它能做什么

不问"你的标准是什么"，而是问"上次你做了什么"。

```
你：改了三遍开头，每次都"不对"，但说不清哪不对
AI：你改 Glasswing 那篇时，看到原始开头的第一反应是什么？
你：铺垫太长了，开头应该直接吸引人
AI：给你两个标题，A 悬念式，B 直给结论式，你选哪个？
你：B。大众看够了悬念，有营销味道
AI：所以你的规则是"吸引力靠内容本身，不靠信息差套路"？
你：对，但内容确实炸裂时可以酌情用悬念
```

**提取结果**：从"不要标题党"4 个字 → 变成 3 句话带边界条件的精确规则。

## 五个挖掘域

| 域 | 挖什么 |
|---|---|
| **writing** | 写作品味：什么开头好、什么是"AI味"、怎么算写透 |
| **topic** | 选题直觉：为什么一看就知道要写、优先级怎么排 |
| **product** | 产品判断：什么产品值得关注、机会怎么判断 |
| **aesthetic** | 视觉审美：封面、排版、配图的偏好 |
| **audience** | 读者感知：读者是谁、怎么和读者沟通 |

## 四种提取方法

1. **关键事件法**（CDM）：回忆具体案例，逐点深挖决策
2. **对比逼近**（Repertory Grid）：A vs B，选择暴露标准
3. **反事实追问**：如果变量 X 改变，判断会变吗？
4. **Laddering 追问**：从表面 → 后果 → 价值观，一层层爬

## 安装

把 `tacit-mining` 文件夹复制到你的 Claude Code skills 目录：

```bash
# macOS / Linux
cp -r tacit-mining ~/.claude/skills/

# 或者直接 clone
git clone https://github.com/xiaohuailabs/tacit-mining.git ~/.claude/skills/tacit-mining
```

## 使用

在 Claude Code 对话中：

```
挖隐性知识
```

或者更具体：

```
聊聊我的写作品味
深度访谈
了解我
```

### 对话节奏

- 每轮只问一个问题，等你回答
- 可能追问 1-2 次
- 用一句话复述提炼的规则
- 你确认或纠正
- 5-8 轮一组，不拖太长

### 存储格式

每条提炼的隐性知识自动存为碎片文件：

```markdown
---
name: tacit_writing_opening
description: 开头直给+吸引力靠内容本身
type: user
domain: writing
confidence: confirmed
---

## 表现（Behavior）
改稿时把铺垫式开头删掉，A/B对比中选了直接给结论。

## 规则（Rule）
吸引力必须来自内容本身的分量，不能靠信息差套路。

## 边界（Boundary）
内容本身确实很炸裂时，可以酌情使用情绪化表达。

## 原话（Verbatim）
> "大众已经看够了会厌烦，而且很有营销味道"
```

## 理论基础

- **Michael Polanyi**《The Tacit Dimension》(1966) — 隐性知识理论
- **Gary Klein** CDM 关键决策法 — NASA/军方验证的专家知识提取
- **George Kelly** Repertory Grid — 对比法提取隐含维度
- **Dreyfus** 五阶段模型 — 专家越专业越说不清

## 实战效果

首次 8 轮对话，提取了 8 条 confirmed 规则，覆盖写作、选题、产品判断三个域。从"不要标题党"到"默认直给结论式，悬念看场合，内容撑得起才用"——信息量差了 10 倍。

## 文件结构

```
tacit-mining/
└── SKILL.md    # 技能定义（方法库 + 流程 + 存储格式）
```

存储目录（自动创建）：

```
memory/tacit/
├── map.md                      # 隐性知识地图（索引）
├── tacit_writing_opening.md    # 写作：开头规则
├── tacit_topic_selection.md    # 选题：瞬间判断公式
└── ...
```

## License

MIT

---

*Built with Claude Code. Inspired by a 60-year-old theory that turned out to be exactly what AI needs.*
