# Optional DESIGN.md Token Module

仅在项目已有或已明确决定建立可执行 Design Tokens 时读取本文件。将适用字段放入 DESIGN.md frontmatter；删除不适用的组，不输出大段 `[TBD]`。

```yaml
---
version: "0.3"
name: "[Design system name]"
status: draft | locked | evolving
surfaceMode: persuade | operate | read | experience
baselineEvidence: none | implementation | design-contract
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
  executableTokens: "[canonical path]"
  consumerFormat: "[CSS variables / TS / DTCG / generator / other]"
  verification: "[command, test or generated artifact]"
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
```

## 使用规则

- 只记录跨页面稳定且实现实际消费的值；
- 优先语义角色，不以具体页面或组件名替代系统 Token；
- 未确认值保持在 UI Brief 或开放问题中，不升级为规范；
- 必须记录唯一来源、消费格式和验证方式；没有实现消费路径时只称设计约定，不称可执行 Token；
- 若 Token 只存在于代码，引用其来源路径，避免在 DESIGN.md 维护第二份真相。
