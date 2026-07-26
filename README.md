# Grill Me for UI

一个面向前端 UI 设计的引导式需求访谈与艺术指导 Agent Skill。

它不会在用户只说“做得更高级”时直接拼装一套模板，而是通过一次一问的对话，明确用户、任务、内容、信息架构和品牌态度，建立 Art Direction，再把构图、排版、色彩、形状、材质、图像、动效、状态和响应式整理成可执行设计契约。

## 核心特点

- **一次只问一个高影响决策**，避免长问卷；
- **每题给出有立场的专业推荐**，而不是无性格折中；
- **先检查现有证据**，不重复询问代码、截图和设计系统中能查明的事实；
- **Art Direction Card**：三个气质词、一个反形容词、视觉命题、张力和设计风险；
- **三项校准旋钮**：`EXPRESSION / MOTION / DENSITY`；
- **一个主导概念，最多两个支持母题**，允许丰富但避免视觉概念互相竞争；
- **构图先于组件**：先确定视觉锚点、视线流、节奏、对比和留白；
- **六层视觉系统**：Typography、Color、Shape、Material & Depth、Imagery、Motion；
- **参考设计三角拆解**：分别提取构图、排版 / 色彩、图像 / 材质 / 动效，避免克隆单一网站；
- **情境化 Anti-Slop**：识别 AI 模板默认值，但不使用跨场景绝对禁令；
- **Professional Visual Critique Loop**：五秒印象、Squint Test、灰度层级、品牌指纹和响应式复核；
- **可选 `DESIGN.md`**：适合多页面、设计系统和跨 Agent 长期迭代。

## 适用范围

- 产品与工作流 UI；
- Dashboard 与数据工具；
- Landing Page 与品牌官网；
- Portfolio 与创意展示；
- Editorial 与内容产品；
- 消费型移动端；
- 社区与娱乐产品；
- 时尚、文化和高端品牌；
- 表单与多步流程；
- 组件系统与完整设计系统；
- 现有 UI 重设计。

受监管或高风险界面可以更克制，但不等于必须做成无辨识度模板。品牌型页面可以更大胆，但不等于堆叠渐变、Bento、毛玻璃和复杂动画。

## 与普通 `/taste` Skill 的区别

`/taste` 类 Skill 通常直接指导前端实现，重点是反模板。本项目更上游：

- 先确定当前项目真正适合什么审美；
- 不默认 Landing Page 的规则适用于所有产品；
- 不把禁用某字体、居中 Hero、三列 Card 或纯黑当作普遍真理；
- 不只负责“避免难看”，还主动建立视觉命题、构图张力和品牌指纹；
- 把审美选择与任务、内容、状态、响应式和可访问性写入同一契约；
- 实施后继续做专业视觉评审。

## 仓库结构

```text
skills/grill-me-for-ui/
├── SKILL.md
└── references/
    ├── interview-map.md
    ├── taste-calibration.md
    ├── visual-critique.md
    ├── ui-brief-template.md
    ├── design-md-template.md
    └── ui-vocabulary.md

examples/
└── dashboard-session.md
```

## 安装

将 `skills/grill-me-for-ui` 复制到 Agent 的 skills 目录，例如：

```text
.agents/skills/grill-me-for-ui
.claude/skills/grill-me-for-ui
```

支持 Agent Skills CLI 的环境可尝试：

```bash
npx skills add https://github.com/linnnn89/grill-me-for-ui --skill grill-me-for-ui
```

不同 Agent 的安装目录和调用方式可能不同，请以对应文档为准。

## 使用示例

```text
/grill-me-for-ui 我想做一个具有强烈文化感的独立杂志官网
```

```text
先不要写代码。为这个 SaaS 首页建立三个真正不同的 Art Direction，再逐项 grill me。
```

```text
检查当前页面和品牌资产，别问能自行查到的事实；只问需要我决定的产品与审美取舍。
```

```text
对这个 Portfolio 做重设计。作品必须是主角，但需要形成可识别的个人设计语言。
```

```text
这个页面不要有通用 AI 模板感。先给出 Design Read、视觉命题和构图方向。
```

```text
实现已经完成，请按 visual-critique 做一次高级 UI 审美复核。
```

## 默认工作流

1. 读取最小必要证据；
2. 判断界面类型、设计自由度和风险；
3. 回放暂定 Design Read；
4. 解决用户、任务、范围和真实内容；
5. 建立 Art Direction Card；
6. 确定一个主导概念和最多两个支持母题；
7. 先确定构图语法，再进入布局与组件；
8. 落地六层视觉系统；
9. 覆盖状态、响应式、可访问性和技术约束；
10. 用户确认后输出 UI Brief，必要时追加 `DESIGN.md`；
11. 视觉稿或实现完成后执行 Professional Visual Critique。

## 默认输出

访谈完成后可输出：

1. 产品背景、用户、任务、范围和真实内容；
2. Art Direction Card；
3. 主导概念、支持母题和品牌指纹；
4. 页面地图、流程和构图语法；
5. 布局、组件、状态和响应式；
6. 排版、色彩、形状、材质、图像、图表与动效规则；
7. 可访问性、内容弹性与技术约束；
8. 可验证的功能与视觉验收标准；
9. 可选 `DESIGN.md`、实现提示词、视觉方向方案或 Critique 报告。

## 设计来源

本项目受以下开源项目与资料启发，并针对 UI 需求访谈与艺术指导重新设计：

- Matt Pocock `grill-me` / `grilling`：一次一问、沿决策树推进、每题给推荐答案；
- VibeHub / `vibe-hub-skill`：自然语言到布局、组件、状态和视觉术语映射；
- Leonxlnx `taste-skill`：Brief Inference、审美旋钮、Anti-Default 和 Pre-Flight；
- Google Labs `design.md` 与 Stitch `taste-design`：持久设计契约、Design Tokens 和语义设计说明；
- 社区 `spec-interview` / `interview-me`：只询问必须由人作出的取舍。

具体版权与许可见 [`ATTRIBUTION.md`](ATTRIBUTION.md)。

## 当前分支重点

本轮优化将 Skill 从“功能完整 + Anti-Slop”进一步提升为真正设计主导：

- Art Direction 提前到布局与组件之前；
- “单一标志性动作”改为“一个主导概念 + 最多两个支持母题”；
- 新增构图语法和六层视觉系统；
- 扩展 Portfolio、Editorial、社区、娱乐、时尚和文化品牌场景；
- 新增专业视觉 Critique Loop 与 P0–P3 问题分级；
- UI Brief 与 `DESIGN.md` 同步记录完整艺术指导，而不只保存 Token。

## License

MIT