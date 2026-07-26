# Optional DESIGN.md Handoff

本模板用于多页面、设计系统、重设计或预计跨 Agent / 跨会话迭代的项目。它参考 Google Labs `DESIGN.md` alpha 思路：YAML Token 提供准确值，Markdown 说明艺术指导、使用边界和视觉系统关系。

单个低风险页面或组件默认只输出 UI Brief 与 Art Direction Card，不额外制造文档。

## 生成条件

至少满足一项：

- 多个页面需要保持同一视觉身份；
- 后续由不同 Agent 或开发者实施；
- 项目已有或准备建立 Design Tokens；
- 用户明确要求持久设计规范；
- 重设计需要记录旧系统到新系统的迁移基线；
- 项目依赖明确的摄影、插画、数据图形或动效系统。

生成前必须已确认：

- Art Direction Card；
- 主导概念和支持母题；
- 构图语法；
- 主要 Token 方向；
- 核心组件状态；
- 明确避免项；
- 内容与素材边界。

## 模板

````markdown
---
version: alpha
name: [Design system name]
description: [One-sentence purpose and visual thesis]
colors:
  atmosphere-background: "[CSS color]"
  atmosphere-surface: "[CSS color]"
  atmosphere-surface-muted: "[CSS color]"
  text-primary: "[CSS color]"
  text-secondary: "[CSS color]"
  border-subtle: "[CSS color]"
  action-primary: "[CSS color]"
  on-action-primary: "[CSS color]"
  action-secondary: "[CSS color or TBD]"
  success: "[CSS color]"
  warning: "[CSS color]"
  error: "[CSS color]"
  info: "[CSS color]"
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
shape:
  radius-sm: "[dimension]"
  radius-md: "[dimension]"
  radius-lg: "[dimension]"
  radius-full: "9999px"
spacing:
  xs: "[dimension]"
  sm: "[dimension]"
  md: "[dimension]"
  lg: "[dimension]"
  xl: "[dimension]"
  section-sm: "[dimension]"
  section-lg: "[dimension]"
layout:
  container-max: "[dimension]"
  grid-columns: [number]
  grid-gutter: "[dimension]"
  reading-width: "[dimension]"
motion:
  instant: "[duration]"
  standard: "[duration]"
  narrative: "[duration]"
  easing-standard: "[CSS easing]"
  easing-emphasized: "[CSS easing]"
components:
  button-primary:
    backgroundColor: "{colors.action-primary}"
    textColor: "{colors.on-action-primary}"
    typography: "{typography.label-sm}"
    rounded: "{shape.radius-md}"
    padding: "[dimension]"
  input-default:
    backgroundColor: "{colors.atmosphere-surface}"
    textColor: "{colors.text-primary}"
    rounded: "{shape.radius-md}"
    padding: "[dimension]"
  card-default:
    backgroundColor: "{colors.atmosphere-surface}"
    textColor: "{colors.text-primary}"
    rounded: "{shape.radius-lg}"
    padding: "[dimension]"
---

# [Design system name]

## 1. Art Direction Card

- **Surface type:** [product / dashboard / landing / editorial / portfolio / mobile / system]
- **Audience and task:**
- **Three character words:**
- **Anti-word:**
- **Visual thesis:**
- **Primary tension:**
- **Primary expressive medium:**
- **EXPRESSION:** [1–10 + rationale]
- **MOTION:** [1–10 + rationale]
- **DENSITY:** [1–10 + rationale]
- **Main design risk:**

Describe the intended emotional response and what must remain visually subordinate.

## 2. Dominant Concept & Motifs

- **Dominant concept:**
- **Why it fits the product and audience:**
- **How it is perceived in five seconds:**
- **Supporting motif 1:**
- **Supporting motif 2:**
- **Elements that must stay quiet:**
- **Mobile translation:**
- **Brand fingerprint without logo:**

Do not introduce additional competing concepts without revising this document.

## 3. Composition Grammar

Document:

- First visual anchor;
- Secondary path and reading flow;
- Grid and alignment logic;
- Scale contrast;
- Density and breathing rhythm;
- Section variation rules;
- Allowed intentional rupture;
- Edge, bleed and crop behavior;
- What information must remain visible together.

## 4. Color Architecture

Explain by role:

### Atmosphere

- Background temperature;
- Neutral hierarchy;
- Surface relationships;
- Dark mode behavior.

### Action

- Primary and secondary action colors;
- Brand accent range;
- Scarcity and emphasis rules.

### Semantic

- Success, warning, error, information and data categories;
- How meaning survives without color;
- Contrast boundaries and banned combinations.

Multiple accents are allowed only when their roles are explicit and stable.

## 5. Typography Voice

Document:

- Intended typographic character;
- Display, heading, body, label, metadata and mono roles;
- Hierarchy through size, weight, width, color and spacing;
- Heading line-break principles;
- Maximum reading width and paragraph rhythm;
- Number alignment, units and tabular figures;
- CJK / Latin mixing, localization and fallback;
- When a second type family is justified;
- Project-specific anti-patterns.

Do not treat font selection alone as typography design.

## 6. Shape Language

Document:

- Dominant geometry;
- Radius scale and role;
- Button, input, card, tag and image relationships;
- Brand-specific silhouette or cut;
- Icon stroke, fill and visual weight;
- When pills, circles, sharp corners or irregular forms are justified.

## 7. Material & Depth

Choose a primary material logic:

- Flat / editorial;
- Bordered / structural;
- Tonal / layered;
- Shadow / spatial;
- Transparent / atmospheric;
- Paper / textured.

Explain:

- Surface hierarchy;
- When Card containers are justified;
- Border, shadow and overlay rules;
- Blur, transparency and texture limits;
- Shadow hue, blur and spread;
- Reduced-transparency fallback;
- Which materials must never compete on the same surface.

## 8. Imagery & Illustration

Document:

- Subject matter;
- Camera distance, viewpoint and lens character;
- Lighting and color treatment;
- Crop ratios and focal-point rules;
- Person gaze and movement direction;
- Image role: evidence, emotion, narrative or decoration;
- Illustration geometry, perspective, line and texture;
- Relationship between illustration and iconography;
- Fallback strategy when asset quality is insufficient;
- Licensing and provenance requirements.

## 9. Iconography

Document:

- Icon family;
- Stroke / fill style;
- Optical size and visual weight;
- Label requirements;
- Allowed exceptions;
- Rules preventing mixed icon languages.

## 10. Data Visualization

When applicable, document:

- User comparison task;
- Preferred chart families;
- Color encoding roles;
- Grid, labels, legends and annotation density;
- Uncertainty and missingness display;
- Non-color alternatives;
- Responsive behavior;
- Decorative charts that should not be added.

## 11. Layout & Responsive Transformation

Document:

- Container, grid and alignment;
- Main page compositions;
- Navigation patterns;
- Density and vertical rhythm;
- Desktop, tablet and mobile anchors;
- What collapses, reorders, transforms or moves to another surface;
- How the dominant concept survives on small screens;
- Table, chart and full-bleed image strategy;
- Viewport-specific exceptions.

Responsive design is not a universal single-column conversion.

## 12. Components

For each core component describe:

- Purpose and visual priority;
- Variants and sizes;
- Relationship to the dominant concept;
- Hover, Active, Focus, Disabled, Loading, Empty and Error states;
- Content-length and localization boundaries;
- Mobile behavior;
- Components that should not be substituted casually;
- Conditions under which Card, Badge, Chip, Tooltip and Eyebrow are appropriate.

## 13. Motion & Time

### Immediate feedback

- Press, Hover, Focus and Validation;

### Spatial explanation

- Expand, collapse, switch, list-to-detail and navigation;

### Narrative choreography

- Page entry, scroll and section transitions;

### Ambient motion

- Whether it exists, why, and how it stops;

### Constraints

- Duration tiers;
- Easing roles;
- Stagger logic;
- High-frequency interaction limits;
- reduced motion;
- Low-performance device fallback;
- Allowed animated properties.

## 14. Content & Asset Truth

- Real content sources;
- Allowed placeholders;
- Prohibited invented metrics, customers, testimonials and awards;
- AI-generated content disclosure;
- Asset quality threshold;
- Extreme-content cases to test.

## 15. Accessibility

- Contrast;
- Focus and keyboard order;
- Labels and errors;
- Non-color state communication;
- Touch targets;
- Zoom and localization;
- Image and chart alternatives;
- Motion reduction;
- Audience- or regulation-specific requirements.

## 16. Do's and Don'ts

### Do

- [Project-specific rule]
- [Project-specific rule]

### Don't

- [Most likely generic default]
- [Competing visual concept]
- [Known inconsistency or accessibility failure]
- [Unverified content, fake data or unsupported claim]

## 17. Visual Critique Protocol

After design or implementation, evaluate:

- Five-second impression;
- Thumbnail / Squint Test;
- Grayscale hierarchy;
- Composition and eye flow;
- Brand fingerprint;
- Typography;
- Color, shape, material and depth;
- Imagery, iconography and data visualization;
- Motion;
- Responsive views;
- Real and extreme content.

Classify findings as P0 direction, P1 structure, P2 finish or P3 preference.
````

## 输出原则

- 不确定值使用 `[TBD]`，不要伪造 Token；
- YAML 提供规范值，正文解释意图、角色和边界；
- Token 名称优先使用语义角色；
- 只记录真正需要跨页面稳定的组件和规则；
- 不把 UI Brief 中未确认的假设升级为规范；
- 每项注明来自用户确认、项目证据、专业推断或暂定默认；
- `DESIGN.md` 必须表达艺术指导，不应退化成颜色和圆角清单。

## 可选验证

若环境允许，可使用 Google `@google/design.md` CLI 检查结构、Token 引用和对比度。该格式目前为 alpha，应记录工具版本，并避免把可能变化的规范写成不可逆依赖。

Windows / PowerShell 中，若带点命令名与文件关联冲突，可尝试官方无点别名：

```powershell
npx -p @google/design.md designmd lint DESIGN.md
```

只有用户要求或项目已采用该工具时才执行，不为简单页面自动安装依赖。