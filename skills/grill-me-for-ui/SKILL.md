---
name: grill-me-for-ui
description: 通过一次一问的设计访谈与确定性路由，把模糊 UI 需求、页面重设计、参考图或现有界面反馈收敛为可执行的 Art Direction、UI Brief、增量计划或视觉评审。适用于用户明确要求“grill me for UI”“先访谈再设计”，或新页面、重大视觉替换、增量扩展、现有 UI 精修、审美研究和实施后验证仍存在重要设计取舍的场景。不要用于需求完整的单点样式修改、纯代码 Bug，或用户明确要求执行已经确认的实现计划。
---

# Grill Me for UI

先判断任务需要哪一种设计能力，再读取一份最相关的参考。不要把每个 UI 请求都跑成完整设计流程。

## 不可违反的行为

1. 一次只问一个会改变方案的高影响问题。
2. 先检查代码、截图、设计稿、真实内容、现有 UI Brief / DESIGN.md 和已确认决定，再提问。
3. 只询问必须由用户决定的产品优先级、品牌态度和主观边界；技术事实由 Agent 调查。
4. 每题说明影响并给出有立场的推荐；先描述可观察效果，再使用术语。
5. 先目标与内容，后 Art Direction；先方向与构图，后组件和细节。
6. 用户未确认设计基线前，不大规模实施或改写设计文件。
7. 使用真实内容和资产；不编造指标、客户、评价、奖项或品牌声明。
8. 一个主导概念，最多两个支持母题。
9. 用户可随时采用推荐、跳过、回退、结束访谈或缩小范围。
10. 验证默认只有 Pass 1、一个 Fix batch 和 Pass 2；没有视觉证据时不声称通过。

## 0. Fast Exit

需求完整、低风险且没有设计取舍的单点修改，例如明确的 Token、尺寸或样式参数，不进入 Router Trace，不加载参考文件，也不访谈。直接按现有系统实施并做一次定向 Review。

纯代码 Bug 或已经确认的实现计划同样退出本 Skill。用户明确调用本 Skill 时，可以简短说明采用短路径，但不要强制完整流程。

## 1. 读取最小证据

只检查当前表面和本次变更需要的资产：

- 当前页面、组件、路由和主要状态；
- 真实文案、数据、图像、图标和作品；
- UI Brief、DESIGN.md、Token、组件库和主题；
- 设备、平台、性能、无障碍与时间边界；
- 当前对话已经确认的决定。

不要因为缺少 DESIGN.md 就把已有产品当作 Greenfield。现有实现也可以构成设计基线。

## 2. 输出 Router Trace

在第一题或执行动作前，用 3–6 行记录：

```text
Surface：[Persuade / Operate / Read / Experience]
Baseline：[无可复用基线 / 现有实现 / 现有设计契约]
Scenario：[Greenfield / World Replacement / Extension / Refinement]
Scope：[全局或受影响表面；适用时 T1 / T2 / T3]
Depth / Action：[适用时重写深度；一个主动作 + 最多一个支持动作]
Reference / Stop：[本轮读取文件；本阶段停止条件]
```

证据不足时写“待检查 / 待确认”，不要为了填满 Trace 猜测 Surface 或 Scenario。用户纠正上游判断后再继续。

### Surface

- **Persuade**：用户理解价值并行动；
- **Operate**：用户高效、安全地完成任务；
- **Read**：用户理解、定位并保留信息；
- **Experience**：内容或作品本身成为体验。

以当前表面的主要成功结果为准。只能有一个主模式，可记录一个次模式。

### Scenario precedence

按以下顺序判断：

1. 没有可复用实现、视觉语言或设计契约，才是 **Greenfield**。
2. 已有基线，但用户明确授权放弃现有视觉身份，是 **World Replacement**。
3. 继续现有视觉身份并新增页面、Section 或组件，是 **Extension**。
4. 继续现有视觉身份并改善已有界面，是 **Refinement**。

缺少书面契约但已有一致实现时，先从相关实现恢复最小基线，再进入 Extension 或 Refinement。不要自动重跑 Greenfield。

### Scope and depth

Extension 按变更规模记录：

- **T1**：新路由或独立页面组；
- **T2**：已有页面的新主要 Section；
- **T3**：Token、单组件、状态或动效参数。

World Replacement 仍要记录受影响表面；局部替换可同时标记 T1 / T2。

Refinement 另选重写深度：

- **Light polish**：保留信息架构和视觉身份；
- **Medium restructure**：可调整分组、布局和组件层级，保留产品逻辑与视觉身份；
- **Full structural rebuild**：可重建构图、页面结构和实现，但仍保留现有视觉身份。

如果视觉身份本身错误，不属于 Full structural rebuild，改走 World Replacement。

需要更多边界案例时才读取 `references/design-intelligence-router.md`。

## 3. 选择最小路径

| 意图 | 主动作 | 首要参考 | 最小结果 |
|---|---|---|---|
| 模糊需求或新方向 | shape / direct | `references/interview-map.md` | 共享理解、方向选择、UI Brief |
| 风格词含糊或需要外部参考 | research | `references/aesthetic-research-protocol.md` | 2–3 个方向胶囊 |
| 已有方向的页面或 Section 扩展 | shape | 旧契约 + `references/interview-map.md` | 局部 Brief 或增量计划 |
| 现有 UI 诊断或精修 | critique / polish / targeted action | `references/iteration-and-refinement.md` | 诊断、重写深度、修改范围 |
| 机械质量与生产边界 | audit / harden / adapt | `references/iteration-and-refinement.md` | 可验证问题或加固计划 |
| 实施后证据确认 | verify | `references/visual-critique.md` | 两轮内的验证结论 |
| 从现有实现提炼长期契约 | document | `references/design-md-template.md` | 可选 DESIGN.md |

`critique` 是设计判断，`audit` 是机械检查，`verify` 是实施后的证据确认。`polish` 适用于综合完成度；问题已经定位时，改用 bolder、quieter、distill、typeset、layout、colorize、animate、delight、harden 或 adapt。

每阶段只加载表中一份首要参考。后续阶段可以换参考，但不要同时读取两个内容重叠的 Playbook。

## 4. 路径规则

### Greenfield / World Replacement

```text
前轮：任务、用户、范围、保留项、反参考、内容资产和约束
→ 必要时研究
→ 2–3 个真正不同的方向胶囊
→ 用户选择主方向
→ 后轮：页面叙事、第一锚点、文案、视觉边界、状态和小屏
→ UI Brief；满足生成条件时才追加 DESIGN.md
```

World Replacement 必须先锁定产品真相、保留行为、废弃范围、迁移风险和前后对照标准。

### Extension

先回放旧契约的主导概念、Token、组件、视觉锚点和允许偏离范围。

- T1：轻量后轮 + 局部锚点；
- T2：最小后轮 + 必要时一个草图；
- T3：目标明确时直接实施 + 定向 Review。

不要重新研究全站方向。

### Refinement

先声明核心失败、重写深度和一个主动作。方向正确时不重跑前轮；方向错误时停止精修，提议 World Replacement 并等待授权。

### Verify

只读取 `references/visual-critique.md`：

```text
Pass 1：桌面 + 移动 + 状态批量发现
→ 一个 Fix batch
→ Pass 2：确认 P0/P1、机械检查和回归
→ 停止
```

## 5. 结束与交付

当以下条件成立时结束当前阶段：

- Surface、Scenario、范围和主动作明确；
- 主要用户、任务、真实资产与成功结果明确；
- 选定方向足以排除主要替代方案，或现有方向明确继续；
- 剩余未知不会显著改变下一阶段；
- 后续可以通过实现或有界验证继续收敛。

先给不超过 12 行的共享理解和最多 3 个非阻塞问题。用户确认后：

- 使用 `references/ui-brief-template.md` 生成按范围裁剪的 UI Brief；
- 仅多页面、设计系统、World Replacement、持续扩展或跨 Agent 项目使用 `references/design-md-template.md`；
- 只有用户继续要求时进入视觉稿、Figma、实现或代码。

用户中途结束时生成部分 Brief，并标明未确认分支。

## 按需参考

- `references/design-intelligence-router.md`：场景边界、动作选择和疑难路由；
- `references/interview-map.md`：前轮、方向选择、后轮和增量问题树；
- `references/aesthetic-research-protocol.md`：风格消歧、七维研究和方向胶囊；
- `references/iteration-and-refinement.md`：重写深度、定向精修和生产加固；
- `references/taste-calibration.md`：Art Direction、构图语法和视觉系统；
- `references/ui-brief-template.md`：按范围裁剪的 UI Brief；
- `references/design-md-template.md`：可选长期设计契约；
- `references/visual-critique.md`：实施后的唯一验证协议；
- `references/ui-vocabulary.md`：仅在用户描述与 UI 术语存在歧义时读取。
