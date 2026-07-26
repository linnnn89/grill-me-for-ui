# Attribution

`grill-me-for-ui` 是独立编写的前端 UI 需求访谈、Art Direction 与设计迭代 Skill。它受到以下开源项目和公开资料启发，但没有捆绑或复制这些项目的代码、风格数据库、组件注册表、图片、脚本或大段原文。

本项目吸收的是可复用的方法论，并根据“引导式问答 + 持久设计契约 + 最小上下文路由”的目标重新组织和独立撰写。

## Matt Pocock — skills

- Repository: https://github.com/mattpocock/skills
- Relevant skills: `grill-me`, `grilling`, `grill-with-docs`
- License: MIT
- Copyright: Matt Pocock

采用的思想包括：一次只问一个问题；沿决策树解决依赖；每个问题提供推荐答案；能够从环境或代码中查明的事实应由 Agent 自行检查。

## VibeHub / vibe-hub-skill

- Website: https://vibe-hub.org
- Repository: https://github.com/oil-oil/vibe-hub-skill
- License: MIT
- Copyright: oil-oil

采用的思想包括：从自然语言描述中识别前端术语；把页面拆解为布局、组件、状态、视觉与交互概念；先解释可观察结果，再使用专业术语。

本仓库没有复制 VibeHub 的课程数据、解析脚本或术语数据库。

## Taste Skill

- Repository: https://github.com/Leonxlnx/taste-skill
- Website: https://www.tasteskill.dev
- Relevant skill: `design-taste-frontend`
- License: MIT
- Copyright: Leonxlnx and contributors

采用的思想包括：设计前进行 Brief Inference；用视觉表达度、动效和密度描述方向；识别常见 AI 设计默认值；重设计采用 Audit-First；实施前后设置 Pre-Flight。

本项目没有照搬其字体、颜色、Hero、Card 或动画禁令，而是将这些规则改造成必须结合表面模式、受众、任务风险和品牌约束判断的情境化提醒。

## Google Labs — DESIGN.md

- Repository: https://github.com/google-labs-code/design.md
- Specification: https://stitch.withgoogle.com/docs/design-md/specification
- License: Apache-2.0
- Copyright: Google LLC and contributors

采用的思想包括：用 YAML Design Tokens 提供准确值，用 Markdown 解释设计意图；将视觉身份沉淀为多个 Agent 和多次迭代可复用的设计契约；验证 Token 引用、对比度和文档结构。

本仓库中的 `design-md-template.md` 为独立编写的可选模板。Google `DESIGN.md` 仍处于可能变化的阶段，使用时应核对其最新公开规范。

## Google Labs — Stitch Skills / taste-design

- Repository: https://github.com/google-labs-code/stitch-skills
- Relevant skill: `plugins/stitch-utilities/skills/taste-design`
- License: Apache-2.0
- Copyright: Google LLC and contributors

采用的思想包括：把视觉气氛、颜色角色、排版架构、组件状态、布局、动效与反模式组织为语义化设计说明。

本项目明确不采用其中跨场景禁止字体、颜色、构图或强制持续动画等绝对规则。

# v0.3 Design Intelligence 参考

## UI UX Pro Max

- Repository: https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- License: MIT
- Copyright: Next Level Builder

采用的思想包括：将产品类型、风格、配色、排版、页面模式、图表和反模式作为可检索的多个知识域；对候选结果进行匹配与排序；先形成设计系统方向，再进入实现。

本仓库没有复制其 UI 风格目录、行业规则、配色、字体、图表数据库、搜索脚本或推理数据。v0.3 只吸收“按域检索、候选排序、知识按需加载”的架构思想，并规定数据库结果不得替代专业判断。

## Impeccable

- Repository: https://github.com/pbakaus/impeccable
- Website: https://impeccable.style
- License: Apache-2.0
- Copyright: Paul Bakaus and contributors

采用的思想包括：

- 按用户在当前表面的成功方式区分 Persuade、Operate、Read 与 Experience；
- 区分 Refinement 与视觉世界替换；
- 用 `critique / audit / polish / bolder / quieter / distill / typeset / layout` 等工作动词路由不同任务；
- 将持久产品上下文与表面设计约束分开；
- 自动检测与 LLM 设计判断分工；
- 用有限截图和修复批次控制验证成本。

本仓库没有复制其命令实现、Detector 规则、CLI、Hooks、浏览器扩展或 Playbook 原文。相关路由和有界验证流程均为独立重写。

## UI Aesthetics Skill

- Repository: https://github.com/kasonye/ui-aesthetics-skill
- Copyright: Repository author and contributors
- License status: 截至 2026-07-26，本次核查未在仓库根目录找到可直接读取的 `LICENSE` 文件

仅采用公开 README 与 SKILL 中可概括的方法论：严格控制用户授权范围；先修层级和构图再做装饰；用灰度检查结构；区分 Generation、Review、Refactor 与 Component / State / Depth 精修；保持默认状态安静；区分 Light polish、Medium restructure 与 Full rebuild。

由于本次未确认仓库许可证，本项目没有复制其原文、参考文件、适配器或任何实现内容，只以通用设计原则的形式独立表述。

## Aesthetic Frontend Skills

- Repository: https://github.com/alexiseverage/aesthetic-frontend-skills
- Website: https://aesthetic-design.art
- Relevant skills: `aesthetic-literacy`, `aesthetic-application`
- License: MIT
- Copyright: Alexis Everage and contributors

采用的思想包括：先识别和消歧审美，再把已确认的方向应用到前端；用 palette、type、texture / material、shape / form、motion、spatial conventions 与 cultural markers 描述风格；记录非谈判项、文化含义和反模式。

本仓库没有复制其 100+ 审美条目、Canonical Slug 索引、知识库、CSS Token 或验证脚本。`aesthetic-research-protocol.md` 是面向本项目工作流独立编写的研究协议。

## Cinematic UI

- Repository: https://github.com/akseolabs-seo/cinematic-ui
- License: MIT
- Copyright: Repository author and contributors

采用的思想包括：把导演和具体影片作为研究输入而不是网页规格；先提取全站视觉语法，再定义每页 Scene Thesis、Signature Composition 与 Shared System；将电影中的镜头、光线、节奏、材质和转场转译为空间、排版和动效。

本仓库没有复制导演数据库、影片资料、Hero / Section / Interaction 数据库、设计 DNA、图片或输出模板。电影研究仅作为 Persuade / Experience 表面的可选路径，并附带版权和素材边界。

## Beautiful UI

- Repository: https://github.com/Kainiko943/beautiful-ui
- Copyright: Repository author and contributors
- License status: 截至 2026-07-26，本次核查未在仓库根目录找到可直接读取的 `LICENSE` 文件

仅采用公开 README 和质量标准中可概括的方法论：先选择视觉方向，再定义设计系统与平台适配；状态、无障碍和响应式属于设计本身；媒体和 3D 技术按复杂度阶梯选择；交付需要桌面、移动和截图等视觉证据；未验证时不能声称完成。

由于本次未确认仓库许可证，本项目没有复制其技能文本、平台适配器、质量 Rubric、脚本、示例或媒体技术配方，只独立实现“技术阶梯”和“证据门禁”的通用概念。

## AI Frontend Design Kit

- Repository: https://github.com/kkunkunya/ai-frontend-design-kit
- License: MIT
- Copyright: Kunkun and contributors

采用的思想包括：约束先于生成；前轮访谈建立产品边界，视觉方向出现后进行后轮访谈；在代码之前完成 Moodboard / 视觉锚点；用 Form、Color、Typography、Layout / Space、Material、Motion 进行多维研究；对增量任务区分 T1 新页面、T2 新 Section 与 T3 微调；设计契约持续回写。

本仓库没有复制其 Obsidian 知识快照、15 段 Kun 格式、技能实现、Prompt、图像工作流或硬禁令。v0.3 的双轮访谈、七维研究和 Tier 路由均为独立重写，并继续保持“一次只问一个问题”的本项目交互原则。

## Better Design

- Repository: https://github.com/marvkr/better-design
- Website: https://better-design.com
- License: MIT
- Copyright: Repository author and contributors

采用的思想包括：将设计原则和 Review 规则按需加载；使用语义 Token 和真实组件实现而不是模糊 Vibe；根据项目匹配 Existing / Official / Curated Scaffold / Custom 设计系统；统一图标家族；组件细节不仅存在于全局颜色，也存在于状态、阴影、边框和交互代码中。

本仓库没有复制其 MCP Server、API、品牌主题、shadcn Registry、组件代码、CSS Token 或 Review 数据。知名品牌系统在本项目中只能作为 Scaffold，不能替代当前产品的 Art Direction，也不能复制其品牌识别元素。

## Community interview skills

还参考了社区中 `spec-interview` 与 `interview-me` 类 Skill 的通用方法：

- 只询问必须由人类判断的取舍；
- 不询问 Agent 能从项目、文档或工具自行确定的事实；
- 需求足够明确时生成结构化规格；
- 明确目标、非目标、边界情况和验收标准。

## 使用边界

- 用户提供的 Stars 排名与数量仅用于发现候选仓库；本项目没有将其作为质量、流行度或当前状态的稳定事实。
- 本仓库不会将上述项目合并为一个大型常驻知识库；只将经过筛选的方法写入按需加载的参考文件。
- 外部项目的名称、品牌和链接仅用于来源说明，不表示其作者认可或参与本项目。
- 若未来直接复制、修改或分发任何外部项目的实质性内容，应重新核对当时的许可证并保留相应版权和许可声明。