# Design Intelligence Router

仅在主 Skill 的基础分类仍有歧义时读取本文件。它只负责确定 Surface、Baseline、Scenario、Scope、Depth / Action 和下一阶段；不包含访谈、研究或设计系统手册。

## 一、先判断表面模式，而不是产品类别

同一个产品可以拥有不同表面。开发者工具的官网仍是说服界面，时尚品牌的帮助中心仍是阅读界面。

| 模式 | 用户成功的定义 | 典型表面 | 设计优先级 |
|---|---|---|---|
| **Persuade · 说服** | 用户理解价值并采取行动 | Landing、定价、活动页、品牌官网 | 注意力、叙事、信任、转化 |
| **Operate · 操作** | 用户高效完成任务 | App、Dashboard、后台、编辑器、设置 | 扫读、反馈、一致、错误恢复 |
| **Read · 阅读** | 用户理解并保留信息 | 文档、文章、指南、新闻、更新日志 | 结构、行长、节奏、导航、搜索 |
| **Experience · 体验** | 内容或作品本身成为体验 | Portfolio、画廊、互动展示、文化品牌 | 作品优先、沉浸、节奏、记忆 |

模式以当前表面为准，不以公司所属行业为准。一个页面只能有一个主模式；可以记录一个次模式，但不能用它为互相冲突的设计目标辩护。

## 二、按优先级判断场景、范围与深度

这些字段不是同一个维度。先判断现有基线与视觉关系，再记录变更范围；只有 Refinement 需要选择重写深度。

### 1. 基线

检查现有实现、截图、Token、组件和文档，而不是只检查是否存在 UI Brief / DESIGN.md：

- **无可复用基线**：没有稳定实现、视觉语言或设计契约；
- **现有实现**：界面已经表达出可识别且相对一致的方向，即使没有书面契约；
- **现有设计契约**：已有可作为来源的 UI Brief、DESIGN.md 或同等规范。

缺少书面契约不等于 Greenfield。已有一致实现时，只从相关实现恢复本次表面的最小基线；若用户目标是沉淀契约，完成 Trace 后再把下一阶段路由为 `document`。

### 2. 场景优先级

按顺序选择：

#### A. Greenfield · 全新方向

只有在没有可复用实现、视觉语言或设计契约时使用。

```text
前轮访谈
→ 必要时审美研究
→ 方向胶囊
→ 后轮访谈
→ 锁定 Art Direction 与设计契约
```

#### B. World Replacement · 视觉世界替换

已有基线，但用户明确授权放弃旧视觉身份。产品真相、功能、内容和平台约束继续保留。

必须明确：

- 哪些功能、文案、数据和行为必须保留；
- 旧系统是实现证据、迁移来源还是反参考；
- 哪些 Token、组件和资产被废弃；
- 受影响表面、迁移风险和前后对照标准。

不要把旧系统和新方向折中成“稍微换皮”。如果用户没有授权替换视觉身份，不进入本场景。

#### C. Extension · 增量扩展

继续现有视觉身份，并新增页面、Section 或组件。现有基线可以来自实现或书面契约。

先读取相关旧资产，再按范围分级：

| Tier | 范围 | 默认路径 |
|---|---|---|
| **T1 新页面** | 新路由或独立页面组 | 轻量后轮 → 局部视觉锚点 → 实施 → Review |
| **T2 新 Section** | 已有页面新增一个主要区块 | 最小后轮 → 必要时一个草图 → 实施 → Review |
| **T3 微调** | Token、单组件、状态或动效参数 | 直接实施 → 定向 Review → 回写契约 |

若一个请求跨 Tier，拆成连续范围。World Replacement 若只影响局部表面，也可以同时记录 T1 / T2。

#### D. Refinement · 现有界面精修

继续现有视觉身份，并改善已有界面。另选重写深度：

- **Light polish**：保留信息架构，只调整层级、间距、排版、状态和视觉一致性；
- **Medium restructure**：允许重新分组、改变布局和组件层级，保留产品逻辑与视觉身份；
- **Full structural rebuild**：允许重建构图、页面结构和实现，但仍保留现有视觉身份。

如果视觉身份本身错误，停止 Refinement，提议 World Replacement 并等待用户授权。

## 三、选择工作动词

用户不需要记住命令名。Agent 选择一个主动作，必要时附带一个支持动作。

| 家族 | 动作 | 使用时机 | 首要参考 | 结束结果 |
|---|---|---|---|---|
| 定义 | **shape / direct** | 在代码前澄清产品、流程或艺术指导 | 对象、动作、导航或状态不清时用 `interaction-and-information-architecture.md`；Greenfield / World Replacement 用 `interview-map.md`；Extension 用 `core-cheatsheet.md` | 共享理解、Interaction / IA Card、方向或 UI Brief |
| 研究 | **research** | 外部证据会改变交互模式或审美方向 | 交互模式证据回到 `interaction-and-information-architecture.md`；风格与文化语义用 `aesthetic-research-protocol.md` | 可解释的模式选择或 2–3 个方向胶囊 |
| 沉淀 | **document** | 从现有实现提炼长期设计规则 | `design-md-template.md` | 可选 DESIGN.md |
| 诊断 | **critique** | 判断“为什么不对” | 常规定位用 `core-cheatsheet.md`；结构性诊断用 `iteration-and-refinement.md` | 设计判断与重写深度 |
| 检查 | **audit** | 检查可访问性、响应式、性能与机械错误 | `iteration-and-refinement.md` | 可验证问题清单 |
| 综合精修 | **polish** | 交付前整体完成度不足但问题不单一 | `iteration-and-refinement.md` | 有界精修计划 |
| 定向精修 | **bolder / quieter / distill / typeset / layout / colorize / animate / delight** | 问题已经定位 | `iteration-and-refinement.md` | 单一目标修改 |
| 生产加固 | **harden / adapt** | 状态、内容极值、设备或平台边界不足 | `iteration-and-refinement.md` | 加固或适配计划 |
| 证据确认 | **verify** | 实施完成后证明结果 | `visual-critique.md` | 两轮内的验证结论 |

`critique` 是专业设计判断，`audit` 是机械与生产检查，`verify` 是实施后的证据确认。不要互换。

一次迭代只设一个主动作，最多附带一个支持动作，例如 `layout + quieter`。每阶段只读取表中一份首要参考；后续阶段可以换参考，但不要同时加载内容重叠的 Playbook。

Visual Probe 不是新动作。它是在结构、交互或方向仍难以通过文字选择时使用的最小证据阶段；读取 `visual-probes.md` 后回到原主动作。

## 四、完成 Trace

分类完成必须满足：

- Surface 有一个主模式；
- Baseline 有项目证据；
- Scenario 按 Greenfield → World Replacement → Extension → Refinement 优先级成立；
- Scope / Tier 或 Refinement depth 明确；
- 一个主动作和最多一个支持动作不冲突；
- 下一阶段 Playbook 与停止条件明确。

需要用户决定时，将对应字段标为 `USER_DECISION_REQUIRED`，不得读取任何下游 reference；只问一个能够区分分类的问题并结束本轮。证据已经充分时，输出 Trace 后进入下一内部阶段；不要再次解释访谈、研究或设计系统知识。
