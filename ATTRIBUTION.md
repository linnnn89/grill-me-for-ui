# Attribution

`grill-me-for-ui` 是独立编写的前端 UI 需求访谈 Skill，设计上受到以下项目和资料启发。

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

采用的思想包括：从用户的自然语言描述中识别前端术语；把页面拆解为布局、组件、状态、视觉与交互概念；先解释可观察结果，再使用专业术语。

## Taste Skill

- Repository: https://github.com/Leonxlnx/taste-skill
- Website: https://www.tasteskill.dev
- Relevant skill: `design-taste-frontend`
- License: MIT
- Copyright: Leonxlnx and contributors

采用的思想包括：在设计前进行 Brief Inference；用视觉表达度、动效和密度描述设计方向；识别常见 AI 设计默认值；重设计采用 Audit-First；实施前后进行 Pre-Flight 检查。

本项目没有照搬其字体、颜色、Hero、Card 或动画禁令，而是将这些规则改造成需要结合界面类型、受众、任务风险和品牌约束验证的情境化判断。

## Google Labs — DESIGN.md

- Repository: https://github.com/google-labs-code/design.md
- Specification: https://stitch.withgoogle.com/docs/design-md/specification
- License: Apache-2.0
- Copyright: Google LLC and contributors

采用的思想包括：用 YAML Design Tokens 提供准确值，用 Markdown 说明设计意图；将视觉身份沉淀为可供多个 Agent 和多次迭代复用的持久设计契约；对 Token 引用、对比度和结构进行验证。

本仓库中的 `design-md-template.md` 是根据公开规范独立编写的可选交付模板。Google `DESIGN.md` 当前为 alpha，使用时应以其最新公开规范为准。

## Google Labs — Stitch Skills / taste-design

- Repository: https://github.com/google-labs-code/stitch-skills
- Relevant skill: `plugins/stitch-utilities/skills/taste-design`
- License: Apache-2.0
- Copyright: Google LLC and contributors

采用的思想包括：把视觉气氛、颜色角色、排版架构、组件状态、布局、动效与反模式组织为语义化设计说明。

本项目明确不采用其中“所有活动组件永久循环动画”“所有移动端多列无例外单列”“跨场景禁止某字体、颜色或构图”等绝对规则，而将其作为反思 AI 默认偏差的参考。

## Community interview skills

还参考了社区中的 `spec-interview` 与 `interview-me` 类 Skill 所体现的通用方法：

- 只询问必须由人类判断的取舍；
- 不询问 Agent 能通过项目、文档或工具自行确定的事实；
- 在需求足够明确时生成结构化规格；
- 明确目标、非目标、边界情况和验收标准。

本仓库未捆绑上述项目的代码、脚本、课程数据或术语数据库。若未来直接复制或修改其较大段内容，应同时保留相应项目的版权与许可声明。