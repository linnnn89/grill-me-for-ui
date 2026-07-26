# Optional DESIGN.md Handoff

本模板用于多页面、设计系统、World Replacement、持续扩展或跨 Agent / 跨会话项目。YAML Token 提供准确值，Markdown 解释 Art Direction、来源、使用边界、组件行为和迭代规则。

单个低风险页面、T3 微调或一次性概念稿默认只输出 UI Brief 与 Art Direction Card。

## 生成条件

至少满足一项：

- 多个页面需要保持同一视觉身份；
- 后续由不同 Agent 或开发者实施；
- 项目已有或准备建立 Design Tokens；
- 用户明确要求持久设计规范；
- World Replacement 需要记录迁移基线；
- 后续预计持续新增 T1 / T2 / T3 迭代。

生成前必须确认：

- 主表面模式；
- 选定方向胶囊；
- Art Direction Card；
- 设计系统策略；
- 主要 Token 方向；
- 核心组件状态；
- 明确避免项和内容真实性边界。

## 模板

````markdown
---
version: "0.3"
name: "[Design system name]"
status: draft | locked | evolving
surfaceMode: persuade | operate | read | experience
projectScenario: greenfield | world-replacement | extension | refinement
selectedDirection: "[Direction capsule name]"
expression: [1-10]
motion: [1-10]
density: [1-10]
systemStrategy: existing | official | curated-scaffold | custom
sourceOfTruth:
  productBrief: "[path or TBD]"
  uiBrief: "[path or TBD]"
  visualAnchors: "[path or TBD]"
  currentImplementation: "[path or TBD]"
colors:
  atmosphereBackground: "[CSS color]"
  atmosphereSurface: "[CSS color]"
  atmosphereMuted: "[CSS color]"
  textPrimary: "[CSS color]"
  textSecondary: "[CSS color]"
  border: "[CSS color]"
  actionPrimary: "[CSS color]"
  onActionPrimary: "[CSS color]"
  actionSecondary: "[CSS color or transparent]"
  success: "[CSS color]"
  warning: "[CSS color]"
  error: "[CSS color]"
  info: "[CSS color]"
typography:
  display:
    fontFamily: "[Font family]"
    fontSize: "[dimension or clamp]"
    fontWeight: [number]
    lineHeight: "[number or dimension]"
    letterSpacing: "[dimension]"
  heading:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: "[number or dimension]"
  body:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: "[number or dimension]"
    maxWidth: "[ch or dimension]"
  label:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: "[number or dimension]"
  data:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: "[number or dimension]"
spacing:
  xs: "[dimension]"
  sm: "[dimension]"
  md: "[dimension]"
  lg: "[dimension]"
  xl: "[dimension]"
  section: "[dimension or clamp]"
shape:
  control: "[dimension]"
  surface: "[dimension]"
  overlay: "[dimension]"
  pill: "9999px"
depth:
  surface: "[border / shadow / tonal rule]"
  raised: "[shadow or token]"
  overlay: "[shadow or token]"
motionTokens:
  instant: "[duration]"
  quick: "[duration]"
  standard: "[duration]"
  slow: "[duration]"
  easingStandard: "[easing]"
  easingEnter: "[easing]"
  easingExit: "[easing]"
icons:
  family: "[Icon family]"
  strokeWidth: "[value]"
  defaultSize: "[dimension]"
  fillPolicy: "outline | filled | mixed-by-rule"
breakpoints:
  mobile: "[dimension]"
  tablet: "[dimension]"
  desktop: "[dimension]"
  wide: "[dimension]"
components:
  buttonPrimary:
    background: "{colors.actionPrimary}"
    text: "{colors.onActionPrimary}"
    typography: "{typography.label}"
    radius: "{shape.control}"
    padding: "[dimension]"
  inputDefault:
    background: "{colors.atmosphereSurface}"
    text: "{colors.textPrimary}"
    border: "{colors.border}"
    radius: "{shape.control}"
    padding: "[dimension]"
  surfaceDefault:
    background: "{colors.atmosphereSurface}"
    text: "{colors.textPrimary}"
    radius: "{shape.surface}"
    depth: "{depth.surface}"
---

# [Design system name]

## 0. Contract Status

- **Status:** Draft / Locked / Evolving
- **Last reviewed:**
- **Owner:**
- **Applies to:**
- **Does not apply to:**
- **Current implementation evidence:**

说明哪些章节已经由用户确认，哪些来自项目证据、公开参考、专业推断或暂定默认。

## 1. Product Truth

- **产品 / 服务：**
- **主要用户：**
- **核心任务：**
- **表面模式：** Persuade / Operate / Read / Experience
- **成功结果：**
- **任务频率：**
- **错误代价与信任要求：**
- **真实内容和资产：**
- **禁止编造：**

产品真相优先于视觉偏好。任何新页面不得偷偷改变业务规则、数据含义或用户承诺。

## 2. Selected Direction

- **方向胶囊名称：**
- **选择原因：**
- **排除方向：**
- **从其他方向借用的唯一维度（可选）：**

### Art Direction Card

- **三个气质词：**
- **反形容词：**
- **视觉命题：**
- **主要张力：**
- **主导表达媒介：**
- **主导概念：**
- **支持母题 1：**
- **支持母题 2：**
- **设计风险：**
- **EXPRESSION / MOTION / DENSITY：**

## 3. Research & Provenance

### Reference triangle

| 参考 | 借鉴维度 | 不借鉴 | 来源 |
|---|---|---|---|
| 构图 |  |  |  |
| 排版 / 色彩 |  |  |  |
| 图像 / 材质 / 动效 |  |  |  |

### Aesthetic semantics

- **Canonical aesthetic / family（若适用）：**
- **Cultural markers：**
- **Connotations：**
- **Non-negotiables：**
- **Cultural / ethical risks：**
- **常见误读：**

参考是研究输入，不是复制规格。知名品牌主题或设计系统必须说明借用维度并去除专属识别元素。

## 4. Composition Grammar

- **Anchor：** 第一视觉锚点；
- **Flow：** 视线和操作如何移动；
- **Rhythm：** 密疏、大小、长短和停顿；
- **Contrast：** 主要视觉张力；
- **Breathing：** 留白如何分组和聚焦；
- **Edge：** 出血、裁切、页面边缘和容器；
- **Grid：**
- **允许的一次破格：**
- **Section 防重复规则：**

每个新页面必须说明如何继承这套语法，而不是仅复用颜色。

## 5. Visual System

### Form

- 主要几何或有机语言；
- 控件、内容和图像之间的形态关系；
- Pill、圆形、直角或切角的使用边界。

### Color

说明：

- Atmosphere、Action、Semantic 三层职责；
- 中性色的色温和明度；
- 强调色稀缺规则；
- 状态色与品牌色如何避免混用；
- 深色、高对比和打印模式。

### Typography

说明：

- Display、Heading、Body、Label、Data 的角色；
- 字号比例、字重、颜色和间距；
- 标题断行和最大行数；
- 正文阅读宽度；
- 数字、单位和表格对齐；
- CJK、拉丁、i18n 和回退策略；
- 字体授权和加载方式。

### Space

- 容器、网格和对齐逻辑；
- 页面和 Section 间距；
- 信息密度；
- 宽屏使用和窄屏重构；
- 哪些元素必须同时可见。

### Material & Depth

- 主要材质逻辑；
- 层级通过空间、边框、色块、阴影、透明或纹理表达；
- Card 的正当使用条件；
- Overlay、背景 Dim 和焦点层级；
- Reduced transparency / 低性能回退。

### Imagery / Illustration / Data Visualization

- 摄影、插画、产品画面、作品或数据谁是主角；
- 裁切、镜头、比例、色调和品质要求；
- 图标家族、线宽、填充和尺寸；
- 图表类型、颜色、标注和替代信息；
- 素材缺失时的替代方案。

### Motion

- 状态反馈；
- 空间解释；
- 叙事编排；
- 环境运动；
- 进入、退出、打断和双向性；
- 时长与缓动；
- Reduced motion；
- 技术阶梯与回退。

## 6. Design System Strategy

- **策略：** Existing / Official / Curated scaffold / Custom
- **主系统：**
- **选择原因：**
- **允许偏离：**
- **必须复用组件：**
- **允许新增组件：**
- **禁止混用的系统：**
- **Scaffold 借用维度：**
- **必须去除的品牌专属元素：**
- **图标策略：**

若使用成熟主题，必须检查组件代码中的状态、阴影、边框和交互，不仅复制 `globals.css`。

## 7. Surface Briefs

每个主要页面或表面建立简短子契约：

```markdown
### [Surface name]
- **Mode：** Persuade / Operate / Read / Experience
- **Tier：** Existing / T1 / T2 / T3
- **Task：**
- **First anchor：**
- **Narrative / flow：**
- **Primary action：**
- **Specific content：**
- **Inherited rules：**
- **Allowed deviation：**
- **States：**
- **Mobile transformation：**
```

表面模式可以不同，但仍必须属于同一总体系统。

## 8. Components & States

对核心组件说明：

- 目的与视觉优先级；
- 变体和尺寸；
- Default、Hover、Active、Pressed、Selected、Focus、Disabled、Loading、Error；
- Selected 与 Pressed 的区别；
- 内容长度和 i18n 边界；
- 移动端行为；
- 哪些组件不能随意替换。

默认状态保持安静，为交互和语义状态保留强调空间。

## 9. Responsive & Platform

- 主要视口；
- 移动端第一屏；
- 导航与主要动作变化；
- 表格、图表、画布和媒体策略；
- Hover 到触控转换；
- iOS / Android / Web / TV 原生预期；
- 安全区、键盘和输入；
- 主导概念在小屏如何继续表达。

## 10. Accessibility, Content & Performance

- 对比度、键盘、Focus 和语义结构；
- Label、错误和恢复路径；
- 非颜色状态表达；
- 长文本、极端数据和 200% 缩放；
- i18n 和 RTL；
- 图像和图表替代信息；
- 性能预算；
- 媒体、3D、Canvas 和 Shader 回退；
- Reduced motion / transparency。

## 11. Do / Don't

### Do

- [项目特定的积极规则]
- [项目特定的积极规则]

### Don't

- [最可能出现的模板化默认]
- [已知不一致或可访问性失败]
- [未经验证的内容、假数据或品牌声明]
- [不允许混入的视觉世界]

不要复制外部 Skill 的全局字体、颜色和布局禁令。这里只记录当前项目有证据支持的规则。

## 12. Iteration Policy

### Change tiers

- **T1 新页面：** 轻量后轮 + 局部锚点 + Review；
- **T2 新 Section：** 最小后轮 + 可选草图 + Review；
- **T3 微调：** 直接实施 + 定向 Review。

### World replacement

只有用户明确授权改变主导视觉世界时进入。记录废弃 Token、迁移策略和前后对照标准。

### Refinement actions

允许按需使用：bolder、quieter、distill、typeset、layout、colorize、animate、delight、harden、adapt。

一次迭代只设一个主动作和最多一个支持动作。

## 13. Verification Contract

### Mechanical checks

- 对比度、Focus、Label、alt；
- Overflow、点击目标、资源失败；
- 关键视口和状态；
- Reduced motion；
- 性能和媒体回退。

### Design critique

- 五秒印象；
- Squint / 灰度；
- 构图、节奏和品牌指纹；
- 排版、色彩、材质、图像和动效；
- 小屏和真实内容。

### Bounded passes

```text
Pass 1 批量发现
→ 一次修复批次
→ Pass 2 确认
→ 停止
```

没有视觉证据时不得声称已经验证。

## 14. Decision Log

| 日期 | Surface | Tier / Action | 决策 | 原因 | 来源 | 影响章节 |
|---|---|---|---|---|---|---|
|  |  |  |  |  | 用户 / 项目 / 公开参考 / 专业推断 |  |

## 15. Open Questions

### Blocking

- 无 / 

### Non-blocking

- 
````

## 输出原则

- 不确定值使用 `[TBD]`，不伪造 Token；
- YAML 提供规范值，正文解释意图、来源和边界；
- Token 名称优先使用语义角色；
- 只记录真正需要跨页面稳定的规则；
- 不把 UI Brief 未确认的假设升级为规范；
- 每项标明用户确认、项目证据、公开参考、专业推断或暂定默认；
- DESIGN.md 必须表达 Art Direction 和迭代治理，不应退化为颜色与圆角清单；
- 大型外部风格目录和研究数据不直接复制进项目，只保留选定方向需要的结论与来源。

## 可选验证

若项目采用 Google `@google/design.md` 或其他 Token 检查工具，可验证结构、引用和对比度。记录工具版本，不把 alpha 规范写成不可逆依赖。

只有用户要求或项目已采用该工具时才执行，不为简单页面自动安装依赖。