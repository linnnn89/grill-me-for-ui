# Grill Me for UI

一个面向前端 UI 的引导式访谈、Art Direction 与设计迭代 Agent Skill。

它不会在用户只说“做得更高级”时直接生成四个模板方案，而是先判断当前表面是说服、操作、阅读还是体验，再通过前轮访谈建立边界，生成 2–3 个真正不同的方向胶囊，待用户看见方向后进行后轮访谈，最终形成可实现、可验证、可持续迭代的 UI Brief 与可选 DESIGN.md。

## v0.3 的核心能力

- **一次只问一个高影响问题**，避免长问卷；
- **表面模式**：Persuade / Operate / Read / Experience；
- **项目场景**：Greenfield、World Replacement、Extension、Refinement；
- **增量 Tier**：T1 新页面、T2 新 Section、T3 微调；
- **双轮访谈**：先建立产品边界，再在方向胶囊选定后拔具体细节；
- **方向胶囊**：视觉命题、气质、主导概念、七维摘要、资产需求和风险；
- **Art Direction Card**：三个气质词、反形容词、视觉张力和设计风险；
- **七维审美画像**：Form、Color、Type、Space、Material、Motion、Cultural markers；
- **检索式知识加载**：只加载当前问题需要的风格、色彩、组件或动效知识；
- **设计系统策略**：Existing / Official / Curated scaffold / Custom；
- **定向精修动词**：bolder、quieter、distill、typeset、layout、colorize、animate、delight、harden、adapt；
- **有界视觉验证**：一次批量发现、一次修复、一次确认，然后停止；
- **机械检测与专业 Critique 分离**，避免把规则当品味，也避免把机械错误包装成偏好。

## 为什么采用双轮访谈

用户在没有看到任何视觉方向时，通常只能给出“高级、简洁、科技感”一类低信息词。v0.3 将访谈拆成：

```text
前轮：产品、用户、范围、反参考、内容资产、平台
→ 审美研究与 2–3 个方向胶囊
→ 后轮：页面叙事、第一锚点、文案声音、七维视觉细节、状态和小屏
→ UI Brief / DESIGN.md
```

这样把探索发生在 Moodboard 或方向层，而不是先写四套代码再让用户挑。

## 仓库结构

```text
skills/grill-me-for-ui/
├── SKILL.md
└── references/
    ├── design-intelligence-router.md
    ├── aesthetic-research-protocol.md
    ├── iteration-and-refinement.md
    ├── interview-map.md
    ├── taste-calibration.md
    ├── ui-brief-template.md
    ├── design-md-template.md
    ├── visual-critique.md
    └── ui-vocabulary.md

examples/
├── dashboard-session.md
├── editorial-brand-session.md
└── dual-round-music-product-session.md
```

## 默认工作流

### 1. 判断表面模式

| 模式 | 用户成功 |
|---|---|
| Persuade | 理解价值并行动 |
| Operate | 完成任务 |
| Read | 理解信息 |
| Experience | 沉浸于内容或作品 |

模式以当前页面为准，不以公司行业为准。

### 2. 判断项目场景

- **Greenfield**：完整双轮流程；
- **World Replacement**：保留产品真相，替换视觉世界；
- **T1 新页面**：轻量后轮 + 局部锚点 + Review；
- **T2 新 Section**：最小后轮 + 可选草图 + Review；
- **T3 微调**：直接实施 + 定向 Review；
- **Refinement**：先选择 Light polish / Medium restructure / Full rebuild。

### 3. 只加载一个相关 Playbook

主 Skill 负责路由，不把所有风格、配色、组件和动效目录常驻上下文。大型知识库按查询使用，减少首次输入和 Token 消耗。

### 4. 有界验证

```text
Pass 1：桌面 + 移动 + 状态批量发现
→ 一次修复批次
→ Pass 2：确认 P0/P1 和回归
→ 停止
```

## 安装

将 `skills/grill-me-for-ui` 复制到 Agent 的 Skills 目录，例如：

```text
.agents/skills/grill-me-for-ui
.claude/skills/grill-me-for-ui
```

支持 Agent Skills CLI 的环境可尝试：

```bash
npx skills add https://github.com/linnnn89/grill-me-for-ui --skill grill-me-for-ui
```

不同 Agent 的路径和调用方式可能不同，请以对应平台文档为准。

## 使用示例

### 全新产品

```text
/grill-me-for-ui 我想做一个面向独立研究者的数据产品，先不要写代码。
```

### 品牌官网

```text
先做前轮访谈，再给我三个真正不同的方向胶囊。不要只换颜色。
```

### 风格消歧

```text
客户说要“cozy retro but not kitsch”。帮我消歧，并给出两个可实施方向。
```

### 现有项目扩展

```text
读取现有 DESIGN.md。我想新增 /pricing 页面，按 T1 最小路径处理，不要重做全站风格。
```

### UI 精修

```text
这个界面方向没错，但太吵。使用 quieter + layout，保持功能和信息密度。
```

### 模糊反馈

```text
我觉得页面还是很 AI，但说不清原因。先 critique，不要直接重写。
```

### 验证

```text
按有界验证协议检查桌面、移动和关键状态。只做一轮批量修复和一次确认。
```

## 完整会话示例

- [`dashboard-session.md`](examples/dashboard-session.md)：Operate / 数据产品的标准访谈；
- [`editorial-brand-session.md`](examples/editorial-brand-session.md)：Editorial / 文化品牌 Art Direction；
- [`dual-round-music-product-session.md`](examples/dual-round-music-product-session.md)：Experience + Read 的前轮、方向胶囊、后轮与锁定过程。

## 输出

按任务范围可生成：

1. 共享理解摘要；
2. 前轮访谈记录；
3. 审美研究与方向胶囊；
4. Art Direction Card；
5. 页面地图、Section 叙事和用户流程；
6. 七维视觉系统；
7. 设计系统和图标策略；
8. 状态、响应式、可访问性和技术约束；
9. UI Brief；
10. 可选 DESIGN.md；
11. Visual Critique 与验证证据。

T3 微调和单组件任务不会自动制造完整文档。

## 与其他设计 Skill 的关系

本项目不是风格百科、主题注册表、UI 代码生成器或浏览器检测器。它位于这些能力的上游和中间层：

- 用访谈建立用户真正的判断边界；
- 用研究协议选择和转译审美方向；
- 用路由器决定需要哪一种后续能力；
- 用 UI Brief / DESIGN.md 保持跨页面和跨 Agent 一致；
- 用有界 Critique 验证实现，而不无限 polish。

外部 Skill 的大型风格目录、品牌主题和 detector 规则不会直接复制进本仓库。具体来源与借鉴边界见 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

## 版本状态

- **v0.2**：Art Direction、构图语法、视觉系统和 Professional Visual Critique，已合并到 `main`；
- **v0.3**：Design Intelligence Router、双轮访谈、方向胶囊、增量 Tier、定向精修和有界验证，当前通过独立 PR 迭代。

## License

MIT