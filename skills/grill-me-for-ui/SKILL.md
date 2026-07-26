---
name: grill-me-for-ui
description: 通过一次一问的设计访谈与确定性路由，把模糊 UI 需求、页面重设计、参考图或现有界面反馈收敛为可执行的 Art Direction、UI Brief、增量计划或视觉评审。适用于用户明确要求“grill me for UI”“先访谈再设计”，或新页面、重大视觉替换、增量扩展、现有 UI 精修、审美研究和实施后验证仍存在重要设计取舍的场景。不要用于需求完整的单点样式修改、纯代码 Bug，或用户明确要求执行已经确认的实现计划。
---

# Grill Me for UI

先判断任务需要哪一种设计能力，再读取一份最相关的参考。不要把每个 UI 请求都跑成完整设计流程。

## 不可违反的行为

1. 一次只问一个会改变方案的高影响问题；先检查现有证据，只问必须由用户决定的取舍。
2. 每题说明影响并给出有立场的推荐；先目标与内容，后 Art Direction、构图和细节。
3. 用户未确认设计基线前，不大规模实施或改写设计文件。
4. 使用真实内容和资产；不编造指标、客户、评价、奖项或品牌声明。
5. 一个主导概念，最多两个支持母题。
6. 用户可采用推荐、跳过、回退、结束访谈或缩小范围。
7. 每阶段只加载一份首要 Playbook；输出阶段只按触发条件追加模板模块。
8. 验证只有 Pass 1、一个 Fix batch 和 Pass 2；没有视觉证据时不声称通过。

## 0. Fast Exit

需求完整、低风险且没有设计取舍的单点修改，例如明确的 Token、尺寸或样式参数，不进入 Router Trace，不加载参考文件，也不访谈。直接按现有系统实施并做一次定向 Review。

纯代码 Bug 或已经确认的实现计划同样退出本 Skill。用户明确调用本 Skill 时，可以简短说明采用短路径，但不要强制完整流程。

## 1. 读取最小证据

只检查当前表面需要的页面、状态、真实内容、设计资产与已确认决定；增量任务优先读取相关 UI Brief、DESIGN.md、Token 和组件，不扫描整个仓库。

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
| 已有方向的页面或 Section 扩展 | shape | `references/interview-map.md` | 局部 Brief 或增量计划 |
| 现有 UI 诊断或精修 | critique / polish / targeted action | `references/iteration-and-refinement.md` | 诊断、重写深度、修改范围 |
| 机械质量与生产边界 | audit / harden / adapt | `references/iteration-and-refinement.md` | 可验证问题或加固计划 |
| 实施后证据确认 | verify | `references/visual-critique.md` | 两轮内的验证结论 |
| 从现有实现提炼长期契约 | document | `references/design-md-template.md` | 可选 DESIGN.md |

`critique` 是设计判断，`audit` 是机械检查，`verify` 是实施后的证据确认。`polish` 适用于综合完成度；问题已经定位时，改用 bolder、quieter、distill、typeset、layout、colorize、animate、delight、harden 或 adapt。

每阶段只加载表中一份首要 Playbook。现有项目证据和按触发条件追加的输出模板不算第二份 Playbook；后续阶段可以换参考，但不要同时读取两个内容重叠的 Playbook。

## 4. 路径护栏

- Greenfield / World Replacement 读取 `interview-map.md`；只有风格含糊或外部参考会改变方向时才进入 research。
- World Replacement 先锁定产品真相、保留行为、废弃范围、迁移风险和前后对照标准。
- Extension 先回放相关旧契约；T1/T2 只做局部访谈，T3 目标明确时直接实施，不重做全站研究。
- Refinement 先声明核心失败、重写深度和一个主动作；方向错误时停止精修并请求 World Replacement 授权。
- Verify 只读取 `visual-critique.md`，Pass 2 后停止。

## 5. 结束与交付

Surface、Scenario、范围、主动作及成功结果明确，且剩余未知不会显著改变下一阶段时停止。高风险 Operate 还需锁定权限、失败与恢复；World Replacement 还需锁定迁移和回退边界。不要因为“还能继续提问”延长访谈。

先给不超过 12 行的共享理解和最多 3 个非阻塞问题。用户确认后：

- 使用 `references/ui-brief-template.md` 生成核心 Brief；只有复杂流程、状态、技术或验证要求才追加 `references/ui-brief-implementation-module.md`；
- 仅多页面、设计系统、World Replacement、持续扩展或跨 Agent 项目使用 `references/design-md-template.md`；项目已有或已明确决定建立可执行 Token 时才追加 `references/design-token-template.md`；
- 只有用户继续要求时进入视觉稿、Figma、实现或代码。

复杂任务同时满足多个条件时，按核心 Brief → Implementation Module → DESIGN.md → Token Module 顺序追加，不回载此前 Playbook。

用户中途结束时生成部分 Brief，并标明未确认分支。

## 仅在需要时追加

- `references/design-intelligence-router.md`：基础分类仍有歧义；
- `references/taste-calibration.md`：需要完整 Art Direction、构图或视觉系统；
- `references/ui-vocabulary.md`：用户描述与 UI 术语存在歧义；
- `references/ui-brief-implementation-module.md`：复杂流程、组件状态、响应式、技术与验证；
- `references/design-token-template.md`：项目已有或已明确决定建立可执行 Design Tokens。
