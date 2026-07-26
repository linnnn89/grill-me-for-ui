# Grill Me for UI

一个面向前端 UI 设计的引导式需求访谈 Agent Skill。

它不会在用户只说“做得现代一点”时立刻生成页面，而是先通过一次一问的对话，逐步明确产品目标、目标用户、信息层级、页面结构、组件、状态、视觉方向、响应式、可访问性与技术约束，再输出可执行的 UI brief。

## 核心特点

- **一次只问一个决策问题**，避免把长问卷一次性倾倒给用户。
- **每题附推荐答案与取舍说明**，用户可以接受、修改或自定义。
- **先检查现有代码、截图、设计系统和项目文档**，不询问能够自行查明的事实。
- **按任务动态分支**：落地页、Dashboard、表单流程、内容页、独立组件和重设计走不同问题树。
- **跳过无关分支**：小改动使用快速模式，完整页面或产品使用标准或深度模式。
- **先达成共享理解，再实施**；访谈结束后生成结构化 UI brief 和验收标准。

## 仓库结构

```text
skills/grill-me-for-ui/
├── SKILL.md
└── references/
    ├── interview-map.md
    ├── ui-brief-template.md
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
对这个现有首页做重设计访谈，保留业务功能，但重新梳理视觉层级和移动端体验。
```

## 默认输出

访谈完成并经用户确认后，Skill 输出：

1. 产品背景、目标用户与主要任务
2. 范围和非目标
3. 页面清单与信息架构
4. 核心用户流程
5. 布局与组件清单
6. 加载、空、错误、成功、权限和破坏性操作状态
7. 视觉与交互规则
8. 响应式与可访问性要求
9. 技术约束
10. 可验证的验收标准与遗留问题

## 设计来源

本项目受以下开源项目与资料启发，并针对前端 UI 需求访谈重新设计：

- Matt Pocock 的 `grill-me` / `grilling`：一次一问、遍历决策树、每题给推荐答案。
- VibeHub 与 `vibe-hub-skill`：将用户的自然语言需求映射为准确的前端组件、布局、状态和视觉术语。
- 社区中的 `spec-interview` / `interview-me`：聚焦必须由人作出的取舍，并在达到实现所需清晰度后生成规格。

具体版权与许可说明见 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

## 版本状态

当前为 **v0.1 初始框架**。适合后续通过小型 PR 逐步补充：

- 不同页面类型的专用问题树
- 更多真实会话与反例
- 自动生成或更新 `UI_BRIEF.md`
- 与 Figma、浏览器截图和现有设计系统的协作流程
- 面向移动端、数据密集型应用和无障碍设计的扩展

## License

MIT
