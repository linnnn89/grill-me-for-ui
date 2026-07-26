# Grill Me for UI

一个面向前端 UI 设计的引导式需求访谈 Agent Skill。

它不会在用户只说“做得现代一点”时立刻生成页面，而是通过一次一问的对话，逐步明确产品目标、目标用户、信息层级、页面结构、组件、状态、视觉方向、响应式、可访问性与技术约束，再输出可执行的 UI Brief。v0.2 进一步加入 Design Read、审美校准和可选 `DESIGN.md` 交付。

## 核心特点

- **一次只问一个决策问题**，避免把长问卷倾倒给用户；
- **每题附推荐答案与取舍说明**，用户可以接受、修改或自定义；
- **先检查现有代码、截图、设计系统和项目文档**，不询问能够自行查明的事实；
- **先做 Design Read**：判断界面类型、受众、任务、信任要求和品牌表达空间；
- **三项审美旋钮**：视觉表达度、动效强度和信息密度；
- **单一标志性设计动作**：避免同时堆叠多个流行效果；
- **情境化 Anti-Slop 审核**：识别 AI 模板默认值，但不使用跨场景绝对禁令；
- **按任务动态分支**：产品 UI、Dashboard、营销页、Portfolio、内容页、移动端、组件和重设计走不同问题树；
- **跳过无关分支**：小改动使用快速模式，完整页面或产品使用标准或深度模式；
- **先达成共享理解，再实施**；访谈结束后生成结构化 UI Brief 和验收标准；
- **可选 Google DESIGN.md 风格交付**：适合多页面、设计系统和跨 Agent 长期迭代。

## 与普通 `/taste` Skill 的区别

`/taste` 类 Skill 通常直接指导设计或编码，重点是避免模板化前端。本项目位于更上游：

- 先通过访谈确定什么审美适合当前产品；
- 不默认 Landing Page 的审美规则同样适合 Dashboard、医疗或公共服务；
- 把外部 Skill 的“禁用字体、禁用居中 Hero、必须强动效”等规则降级为待验证的偏差提醒；
- 将审美选择与业务任务、状态、可访问性和真实内容一起写入设计契约。

## 仓库结构

```text
skills/grill-me-for-ui/
├── SKILL.md
└── references/
    ├── interview-map.md
    ├── taste-calibration.md
    ├── ui-brief-template.md
    ├── design-md-template.md
    └── ui-vocabulary.md

examples/
└── dashboard-session.md
```

## 安装

将 `skills/grill-me-for-ui` 目录复制到所用 Agent 的 skills 目录，例如：

```text
.agents/skills/grill-me-for-ui
.claude/skills/grill-me-for-ui
```

支持 Agent Skills CLI 的环境可尝试：

```bash
npx skills add https://github.com/linnnn89/grill-me-for-ui --skill grill-me-for-ui
```

不同 Agent 的安装目录和调用方式可能不同，请以该 Agent 的 Skill 文档为准。

## 使用示例

```text
/grill-me-for-ui 我想做一个医学科研数据 Dashboard
```

```text
先不要写代码。针对这个登录流程 grill me，直到 UI 需求足够明确。
```

```text
检查当前页面和代码，别问能自行查到的事实；只问需要我决定的 UI 取舍。
```

```text
对这个现有首页做重设计访谈。保留业务功能，但重新梳理视觉层级、品牌辨识度和移动端体验。
```

```text
这个页面不要有通用 AI 模板感。先给出 Design Read，再逐项 grill me。
```

## 默认工作流

1. 读取最小必要证据；
2. 判断界面类型与设计风险；
3. 回放当前理解并给出暂定 Design Read；
4. 自动选择快速、标准或深度模式；
5. 一次解决一个高影响决策；
6. 校准 `EXPRESSION / MOTION / DENSITY`；
7. 确定一个视觉主张和最多一个标志性设计动作；
8. 覆盖状态、响应式、可访问性和技术约束；
9. 执行情境化 Anti-Slop Pre-Flight；
10. 用户确认后输出 UI Brief，必要时追加 `DESIGN.md`。

## 默认输出

访谈完成并经用户确认后，Skill 可输出：

1. 产品背景、目标用户与主要任务；
2. 范围、非目标与必须保留项；
3. 页面清单、信息架构和核心流程；
4. 布局、响应式与组件清单；
5. 加载、空、错误、成功、权限和破坏性状态；
6. Design Read、三项审美旋钮、视觉主张和标志性动作；
7. 排版、颜色、形状、深度、图像和动效规则；
8. 可访问性、内容弹性与技术约束；
9. Anti-Slop Pre-Flight；
10. 可验证的验收标准、风险和决策记录；
11. 可选 `DESIGN.md`、实现提示词或后续设计交付。

## 设计来源

本项目受以下开源项目与资料启发，并针对“UI 需求访谈”重新设计：

- Matt Pocock 的 `grill-me` / `grilling`：一次一问、沿决策树推进、每题给推荐答案；
- VibeHub 与 `vibe-hub-skill`：把自然语言映射为准确的布局、组件、状态和视觉术语；
- Leonxlnx `taste-skill`：Brief Inference、三项审美旋钮、Anti-Default 与 Pre-Flight 思路；
- Google Labs `design.md` 与 Stitch `taste-design`：持久设计契约、Design Tokens 和语义设计说明；
- 社区 `spec-interview` / `interview-me`：只询问必须由人作出的取舍，在足够清晰时生成规格。

具体版权与许可说明见 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

## 版本状态

当前分支目标为 **v0.2 taste calibration**：

- 已加入 Design Read；
- 已加入 `EXPRESSION / MOTION / DENSITY`；
- 已加入视觉主张、标志性设计动作和情境化 Anti-Slop Gate；
- 已加入可选 Google `DESIGN.md` 风格交付；
- 已强化真实数据、假内容和跨场景绝对规则的边界。

后续可通过小型 PR 继续补充：

- Landing、移动端和重设计的完整会话示例；
- UI Brief / DESIGN.md 自动生成脚本；
- 截图驱动的视觉 QA 与 Before / After 验收；
- Dashboard、医疗、数据密集型 UI 专用问题树；
- 与 Figma、Stitch 和浏览器验证的协作流程。

## License

MIT