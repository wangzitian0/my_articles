# Codex 公众号工作流仓库

本仓库将公众号深度文章创作拆分为 5 个工作流阶段，并提供相应的模板、提示词与质检工具。所有文章资产统一存放在 `articles/<topic>/` 中，全部为 Markdown。

## 目录结构
- `01_brief_inputs/`：输入提纲阶段（生成提纲、缺口清单）。
  - `README.md`：阶段目标、交付物、检查项。
  - `outline_prompt.md`：结构化提纲提示词。
- `02_synthesis/`：素材归纳阶段（案例矩阵、洞察摘要）。
  - `README.md`、`case_prompt.md`、`synthesis_prompt.md`。
- `03_chapter_iterations/`：逐章迭代阶段（章节草稿与 QA）。
  - `README.md`、`chapter_prompt.md`。
- `04_article_delivery/`：成稿交付阶段（全文合成、视觉规划）。
  - `README.md`、`article_template_v5.md`、`article_prompt.md`。
- `05_quality_prompts/`：质检与提示词维护。
  - `README.md`、`quality_checklists.md`、`qa_report_template.md`、`prompt_update_guide.md`、`prompt_update_log.md`、`agent.md`。
- `articles/`：文章资产目录，含结构说明与示例。
- `AGENTS.md`：整体 Agent 流程，含“确认 OK 后提交 GitHub”的操作手册。

## 工作流概览
1. **提纲输入**：收集选题、提纲、痛点，标记视觉/互动占位与素材缺口（目录：`01_brief_inputs/`）。
2. **素材归纳**：补齐案例与数据四要素，产出 `cases.md` 与 `insights.md`（目录：`02_synthesis/`）。
3. **章节迭代**：与用户逐章对话，生成 `chapter_<n>.md` 和对应 QA（目录：`03_chapter_iterations/`）。
4. **全文交付**：基于模板合成 3,500-4,000 字正文，完成视觉计划（目录：`04_article_delivery/`）。
5. **质检与提示词更新**：运行全文/章节/节级质检，更新提示词与 Agent 说明（目录：`05_quality_prompts/`）。

## 文章目录规范
参考 `articles/README.md`，所有文章均以 `articles/<topic>/` 存放：
`outline.md` → `cases.md` → `insights.md` → `chapters/` → `article.md` → `qa.md` → `prompts.md`。示例见 `articles/sample_topic/`。

## 使用建议
1. 每完成一个阶段，务必在阶段 README 的检查项全部打勾后再进入下一步。
2. 质检不通过时，返回相应阶段调整，并在 `prompt_update_log.md` 记录经验。
3. 新文章请先在 `articles/` 中创建主题文件夹与 README，再开新版本目录记录全过程。
