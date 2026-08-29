# Grill Me for UI

> A design-intelligence router for UI work: interview first, choose the right design capability, then implement and verify within a bounded loop.
>
> 面向 UI 设计工作的 Design Intelligence Router：先访谈与判断，再选择正确能力，最后在有界循环内实施和验证。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## What it does / 它解决什么问题

Most UI agents jump from an underspecified request to code. **Grill Me for UI** keeps the upstream design decisions explicit:

多数 UI Agent 会把模糊需求直接变成代码。**Grill Me for UI** 先把上游设计决策变得可见、可解释、可交接：

- identify the current surface, project scenario, change tier, and refinement depth;
- determine whether the task needs shape, research, critique, polish, layout, hardening, or another focused capability;
- resolve objects, actions, navigation, permissions, and material state transitions before visual styling when the product structure is still uncertain;
- ask one high-impact question at a time, with a recommendation and a clear stop condition;
- use the smallest useful visual probe when words alone cannot resolve a structural, interaction, or Art Direction choice;
- produce a UI Brief, an incremental plan, or an optional `DESIGN.md` when the scope justifies it;
- validate with one discovery pass, one fix batch, and one confirmation pass.

- 判断当前表面、项目场景、变更 Tier 和精修深度；
- 判断任务需要 shape、research、critique、polish、layout、harden 等哪一种能力；
- 在产品结构仍不明确时，先解决对象、动作、导航、权限和关键状态转换；
- 一次只问一个高影响问题，同时给出推荐和停止条件；
- 当文字不足以比较结构、交互或视觉方向时，使用最小可用的 Visual Probe；
- 按范围生成 UI Brief、增量计划，或可选的 `DESIGN.md`；
- 通过一次发现、一次修复和一次确认完成有限验证。

It is an upstream design router, not a style encyclopedia or a UI code generator.

它是上游设计路由器，不是风格百科，也不是 UI 代码生成器。

## Quick start / 快速开始

### Install / 安装

Install the skill with an Agent Skills-compatible CLI:

使用支持 Agent Skills 的 CLI 安装：

```bash
npx skills add https://github.com/linnnn89/grill-me-for-ui --skill grill-me-for-ui
```

For Codex, place `skills/grill-me-for-ui` under `$CODEX_HOME/skills/grill-me-for-ui`. Keep activation opt-in if you do not want every UI task to enter a design interview.

对于 Codex，可将 `skills/grill-me-for-ui` 放到 `$CODEX_HOME/skills/grill-me-for-ui`。如果不希望所有 UI 任务都进入设计访谈，请保持按需启用。

### Invoke / 调用

Use it when the request still contains meaningful design choices:

当需求仍包含重要设计取舍时使用：

```text
/grill-me-for-ui I want to redesign the onboarding flow. Interview me before writing code.
```

```text
/grill-me-for-ui 我想重做 onboarding 流程。先访谈，再写代码。
```

For a small, already-decided implementation, skip the skill and execute the confirmed plan directly.

对于已经明确的单点实现，不需要启动本 Skill，直接执行已确认方案即可。

## The routing model / 路由模型

The router makes four decisions before selecting a playbook:

路由器在选择 Playbook 前先判断四件事：

| Dimension / 维度 | Options / 选项 | Question / 判断问题 |
|---|---|---|
| Surface / 表面 | Persuade · Operate · Read · Experience | What does success mean on this surface? / 当前页面的成功是什么？ |
| Scenario / 场景 | Greenfield · World Replacement · Extension · Refinement | Is there a visual and product baseline to preserve? / 是否存在需要沿用的基线？ |
| Tier / 范围 | T1 new page · T2 new section · T3 micro-tuning | How much of the existing surface changes? / 本次改变多大范围？ |
| Depth / 深度 | Light · Medium · Full structural | Is the direction right, or is the structure failing? / 需要精修还是结构重写？ |

Then it selects one primary action, such as `shape`, `research`, `critique`, `polish`, `bolder`, `quieter`, `distill`, `typeset`, `layout`, `colorize`, `animate`, `delight`, `harden`, `adapt`, `verify`, or `document`.

然后只选择一个主动作，例如 `shape`、`research`、`critique`、`polish`、`bolder`、`quieter`、`distill`、`typeset`、`layout`、`colorize`、`animate`、`delight`、`harden`、`adapt`、`verify` 或 `document`。

### Scenario routing / 场景路由

```text
Greenfield / World Replacement
  → first-round interview
  → interaction and IA when product structure is consequentially unclear
  → research only when it can change the direction
  → 2–3 genuinely different direction capsules
  → visual probe only when words are insufficient for selection
  → second-round detail interview

Extension T1/T2 or most Refinement
  → core cheatsheet
  → local decision or bounded change plan

Explicit polish, targeted action, audit, hardening, or adaptation
  → iteration-and-refinement playbook

Implemented UI with visual evidence
  → bounded visual critique
  → task walkthrough for complex Operate or multi-step flows
```

```text
Greenfield / World Replacement：完整双轮访谈；产品结构仍不清楚时先完成 Interaction / IA，必要时研究，再进入方向胶囊和细节确认。

Extension T1/T2 或多数 Refinement：优先使用轻量 Cheatsheet，形成局部决定或修改边界。

已明确的 polish、定向动作、audit、harden 或 adapt：进入迭代与精修 Playbook。

已有实现且需要视觉证据：进入有界 Visual Critique；复杂 Operate 或多步骤流程按需追加 Task Walkthrough。
```

## Why the interview is two-round / 为什么是双轮访谈

Users can rarely specify a useful visual system before seeing any direction. The first round therefore establishes product truth and constraints; only after direction capsules exist does the second round ask about visual detail.

用户在没有看到视觉方向前，通常只能说“高级、简洁、科技感”。因此前轮先锁定产品目标、用户、内容资产、约束和反参考；看到方向胶囊后，后轮才确认页面叙事、第一锚点、文案声音、色彩、排版、状态和动效。

```text
Round 1: product, users, content, constraints, anti-references
    → research when ambiguity is consequential
    → 2–3 differentiated direction capsules
Round 2: narrative, first anchor, voice, visual system, states, motion
    → UI Brief / DESIGN.md when the scope warrants a durable handoff
```

方向胶囊必须在视觉命题、信息结构、内容依赖、资产要求、技术复杂度和风险上产生真实差异，而不是只替换颜色。

## Progressive disclosure / 渐进披露

The runtime path is intentionally small:

运行时路径刻意保持轻量：

1. Load `SKILL.md` and classify the task.
2. Load one primary playbook for the current stage.
3. Load a deep appendix only when the lightweight path hits its trigger condition.
4. Load output templates only for a durable handoff.
5. Stop when the next decision is no longer blocked.

1. 先读取 `SKILL.md` 并完成分类；
2. 当前阶段只加载一个主 Playbook；
3. 轻量路径命中触发条件后才追加 deep 附录；
4. 只有需要持久交接时才加载输出模板；
5. 下一步不再存在阻塞性决定时停止。

This keeps the high-frequency Extension and Refinement paths short while preserving full research and interview depth for genuinely new or replacement projects.

这样可以让高频的 Extension 和 Refinement 保持短路径，同时为真正的新项目或视觉世界替换保留完整访谈与研究深度。

## Reference map / 参考文件

| File / 文件 | Role / 用途 |
|---|---|
| [`SKILL.md`](skills/grill-me-for-ui/SKILL.md) | Main router, stop rules, loading discipline / 主路由、停止规则和加载纪律 |
| [`design-intelligence-router.md`](skills/grill-me-for-ui/references/design-intelligence-router.md) | Surface, scenario, tier, and boundary definitions / 分类与边界定义 |
| [`core-cheatsheet.md`](skills/grill-me-for-ui/references/core-cheatsheet.md) | Lightweight Extension and Refinement diagnosis / 轻量增量与精修诊断 |
| [`interaction-and-information-architecture.md`](skills/grill-me-for-ui/references/interaction-and-information-architecture.md) | Objects, actions, navigation, state transitions, and continuity / 对象、动作、导航、状态转换与上下文连续性 |
| [`interview-map.md`](skills/grill-me-for-ui/references/interview-map.md) | Two-round interview and direction capsules / 双轮访谈与方向胶囊 |
| [`aesthetic-research-protocol.md`](skills/grill-me-for-ui/references/aesthetic-research-protocol.md) | Style disambiguation and reference analysis / 风格消歧与参考分析 |
| [`visual-probes.md`](skills/grill-me-for-ui/references/visual-probes.md) | Lowest-useful-fidelity decision evidence / 最低有效保真度的视觉决策证据 |
| [`taste-calibration.md`](skills/grill-me-for-ui/references/taste-calibration.md) | Art Direction Card and visual system decisions / Art Direction Card 与视觉系统决策 |
| [`iteration-and-refinement.md`](skills/grill-me-for-ui/references/iteration-and-refinement.md) | Targeted actions, diagnosis, and bounded iteration / 定向动作、诊断和有界迭代 |
| [`visual-critique.md`](skills/grill-me-for-ui/references/visual-critique.md) | Mechanical checks and design judgment / 机械检查与设计判断 |
| [`ui-brief-template.md`](skills/grill-me-for-ui/references/ui-brief-template.md) | Durable UI decision handoff / 持久化 UI 决策交接 |
| [`design-md-template.md`](skills/grill-me-for-ui/references/design-md-template.md) | Long-term design contract / 长期设计契约 |

Deep references are loaded only when the corresponding playbook says they are needed. Examples are for human reading and offline evaluation; normal runtime does not load them.

Deep 文件只在对应 Playbook 明确需要时加载。Examples 仅供人类阅读和离线评估，正常运行时不加载。

## Example prompts / 使用示例

```text
New product / 新产品
I am building a data product for independent researchers. Interview me before writing code.

Existing extension / 现有项目扩展
Read the existing DESIGN.md. Add a /pricing page as T1. Preserve the current visual world.

Targeted refinement / 定向精修
The direction is right but the page is too noisy. Use quieter + layout and keep the information density.

Ambiguous feedback / 模糊反馈
The page still feels AI-generated, but I cannot explain why. Critique first; do not rewrite yet.

Verification / 验证
Run the bounded visual verification protocol across desktop, mobile, and key states.
```

```text
全新产品：我想做一个面向独立研究者的数据产品。先访谈，再写代码。

现有项目扩展：读取现有 DESIGN.md，新增 /pricing 页面，按 T1 处理并保持当前视觉世界。

定向精修：方向没错，但页面太吵。使用 quieter + layout，保持信息密度。

模糊反馈：页面还是很像 AI 生成的，但我说不清原因。先 critique，不要重写。

验证：按有界协议检查桌面、移动端和关键状态。
```

See the [`examples/`](examples/) directory for complete sessions:

完整会话见 [`examples/`](examples/)：

- [`dashboard-session.md`](examples/dashboard-session.md) — Operate / data product / 数据产品；
- [`editorial-brand-session.md`](examples/editorial-brand-session.md) — editorial brand direction / 文化品牌方向；
- [`dual-round-music-product-session.md`](examples/dual-round-music-product-session.md) — full two-round flow / 完整双轮流程。

## What it produces / 输出内容

Depending on scope, the skill can produce:

根据任务范围，可生成：

- a shared-understanding trace and assumptions / 共享理解摘要与假设；
- an interview record and direction capsules / 访谈记录与方向胶囊；
- an Art Direction Card and seven-dimension visual system / Art Direction Card 与七维视觉系统；
- an Interaction / IA Card and material state-transition model / Interaction / IA Card 与关键状态转换模型；
- a minimal visual probe when text cannot resolve a choice / 文字不足以完成选择时的最小视觉探针；
- a page narrative, component, state, responsive, and accessibility plan / 页面叙事、组件、状态、响应式和可访问性计划；
- a UI Brief or incremental implementation plan / UI Brief 或增量实施计划；
- an optional `DESIGN.md` long-term contract / 可选的 `DESIGN.md` 长期契约；
- bounded critique evidence and a final stop decision / 有界 Critique 证据与最终停止决定。

Small T3 changes and confirmed implementation tasks should not manufacture a full design document.

小型 T3 修改和已确认的实现任务不应强行生成完整设计文档。

## Scope and attribution / 边界与归属

This project is responsible for upstream design discovery, direction selection, routing, and bounded verification. It does not copy external style databases, prompt libraries, CLIs, detectors, or code-generation templates.

本项目负责上游设计探索、方向选择、能力路由和有界验证。不复制外部风格数据库、Prompt 库、CLI、Detector 或代码生成模板。

Methodological influences and boundaries are documented in [`ATTRIBUTION.md`](ATTRIBUTION.md).

方法论来源与借鉴边界见 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

## Project status / 项目状态

Current release line: **v0.5 — interaction structure and visual-evidence bridge**.

当前版本线：**v0.5 — 交互结构与视觉证据桥梁**。

- v0.2: Art Direction, composition grammar, visual critique, and basic UI Brief / Art Direction、构图语法、视觉 Critique 与基础 UI Brief；
- v0.3: router taxonomy, two-round interviews, direction capsules, refinement actions, and bounded verification / 路由分类、双轮访谈、方向胶囊、精修动作与有界验证；
- v0.4: slim main router, lightweight cheatsheet, and on-demand deep references / 精简主路由、轻量 Cheatsheet 与按需 deep 参考文件。
- v0.5: interaction and information architecture, minimum-fidelity visual probes, richer state handoff, and task walkthroughs / 交互与信息架构、最低有效保真度视觉探针、更完整的状态交接与任务走查。

## License / 许可证

[MIT](LICENSE)
