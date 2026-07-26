# Optional DESIGN.md Handoff

本模板用于多页面、设计系统、重设计或预计跨 Agent / 跨会话迭代的项目。它参考 Google Labs `DESIGN.md` alpha 规范：YAML Token 提供准确值，Markdown 说明解释设计意图和使用边界。

单个低风险页面或组件默认只输出 UI Brief，不额外制造文档。

## 生成条件

至少满足一项时考虑生成：

- 多个页面需要保持视觉一致；
- 后续会由不同 Agent 或开发者实施；
- 项目已有或准备建立 Design Tokens；
- 用户明确要求持久设计规范；
- 重设计需要记录旧系统到新系统的迁移基线。

生成前必须已经确认：Design Read、视觉主张、主要 Token 方向、核心组件状态和明确避免项。

## 模板

```markdown
---
version: alpha
name: [Design system name]
description: [One-sentence purpose and visual thesis]
colors:
  primary: "[CSS color]"
  on-primary: "[CSS color]"
  secondary: "[CSS color]"
  on-secondary: "[CSS color]"
  background: "[CSS color]"
  surface: "[CSS color]"
  surface-muted: "[CSS color]"
  text-primary: "[CSS color]"
  text-secondary: "[CSS color]"
  border: "[CSS color]"
  success: "[CSS color]"
  warning: "[CSS color]"
  error: "[CSS color]"
typography:
  display-lg:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: [number or dimension]
    letterSpacing: "[dimension]"
  heading-md:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: [number or dimension]
  body-md:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: [number or dimension]
  label-sm:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: [number or dimension]
  mono-md:
    fontFamily: "[Font family]"
    fontSize: "[dimension]"
    fontWeight: [number]
    lineHeight: [number or dimension]
rounded:
  sm: "[dimension]"
  md: "[dimension]"
  lg: "[dimension]"
  full: "9999px"
spacing:
  xs: "[dimension]"
  sm: "[dimension]"
  md: "[dimension]"
  lg: "[dimension]"
  xl: "[dimension]"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.md}"
    padding: "[dimension]"
  button-primary-hover:
    backgroundColor: "[CSS color or token reference]"
  input-default:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text-primary}"
    rounded: "{rounded.md}"
    padding: "[dimension]"
  card-default:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text-primary}"
    rounded: "{rounded.lg}"
    padding: "[dimension]"
---

# [Design system name]

## Overview

- **Design Read:** [surface, audience, task, trust and brand constraints]
- **Visual thesis:** [one executable sentence]
- **EXPRESSION:** [1–10 and rationale]
- **MOTION:** [1–10 and rationale]
- **DENSITY:** [1–10 and rationale]
- **Signature move:** [one main memorable device, or explicitly none]

Explain the intended emotional response, product context, and what should remain visually subordinate.

## Colors

Explain each color by functional role rather than appearance alone:

- Which color controls primary actions;
- How semantic colors differ from brand accents;
- Which surfaces create hierarchy;
- Dark mode or high-contrast behavior;
- Banned combinations and contrast boundaries.

## Typography

Document:

- Display, heading, body, label and mono roles;
- Hierarchy through size, weight, color and spacing;
- Maximum reading width and number alignment;
- Long text, CJK, localization and fallback strategy;
- Context-specific rules rather than universal font bans.

## Layout

Document:

- Grid, container width and alignment logic;
- Main page composition and navigation pattern;
- Information density and vertical rhythm;
- Breakpoints and small-screen transformation;
- What remains visible together and what may collapse or move.

## Elevation & Depth

Explain how hierarchy is expressed:

- Border, tonal surface, shadow, overlay or whitespace;
- When Card containers are justified;
- Overlay stacking and background dimming;
- Shadow color, blur and spread if used;
- Reduced-transparency fallback when applicable.

## Shapes

Document:

- Radius scale and consistency rule;
- Button, input, card, chip and modal shape relationships;
- Icon stroke or fill style;
- Where pills, circles or sharp corners are functionally justified.

## Components

For each core component describe:

- Purpose and visual priority;
- Variants and sizes;
- Hover, Active, Focus, Disabled, Loading and Error states;
- Content-length and localization boundaries;
- Mobile behavior;
- Components that should not be substituted casually.

## Do's and Don'ts

### Do

- [Project-specific rule]
- [Project-specific rule]

### Don't

- [Most likely template default for this project]
- [Known inconsistency or accessibility failure]
- [Unverified content, fake data or unsupported brand claim]
```

## 输出原则

- 不确定值使用 `[TBD]`，不要伪造精确 Token；
- YAML Token 是规范值，正文解释为什么和何时使用；
- 颜色命名优先语义角色，避免只用 `blue-1`、`gray-2`；
- 组件 Token 只覆盖真正需要跨页面稳定的核心组件；
- 不把 UI Brief 中尚未确认的假设悄悄升级为设计规范；
- 在 UI Brief 的决策记录中标明每项是“用户确认 / 证据推断 / 暂定默认”。

## 可选验证

若环境允许，可使用 Google `@google/design.md` CLI 检查结构、Token 引用和对比度。该格式目前为 alpha，应记录工具版本，并避免把可能变化的规范写死为项目不可逆依赖。

Windows / PowerShell 环境中，若 `npx @google/design.md` 因 `.md` 命令名与文件关联冲突无输出，可使用官方提供的无点别名调用方式：

```powershell
npx -p @google/design.md designmd lint DESIGN.md
```

只有用户要求或项目已采用该工具时才执行，不要为了一个简单页面自动安装依赖。