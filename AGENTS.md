# Codex 公众号创作 Agent 流程

> 目标：基于仓库现有模板与提示词，完成一篇 3,500-4,000 字的公众号深度文章，并在用户确认“OK”之后提交到 GitHub。

## 0. 前置约定
- 文章资产全部放在 `articles/<topic>/`，关键提示词集中于 `brief.md`。
- 写作遵循 `README.md` 的五阶段流程与 `05_quality_prompts/agent.md` 的风格约束。
- 每个阶段的交付文件均为 Markdown，必要时先创建空文件并写“待补充”。

## 1. 输入提纲阶段（01_brief_inputs）
1. 用户更新 `articles/<topic>/brief.md`，说明主题、痛点、案例、数据诉求。
2. 运行 `01_brief_inputs/outline_prompt.md`，生成结构化提纲，落到 `outline.md`。
3. 同步记录素材缺口到 `gap_list.md`，标注视觉/互动占位。

## 2. 素材归纳阶段（02_synthesis）
1. 用 `case_prompt.md`/`synthesis_prompt.md` 补齐案例与数据，写入 `cases.md`、`insights.md`。
2. 数据必须注明四要素（数值、时间、主体、来源）；缺失项继续留在 `gap_list.md`。

## 3. 章节迭代阶段（03_chapter_iterations）
1. 依据 `chapter_prompt.md` 逐章写作，将产物放入 `chapters/chapter_<n>.md`。
2. 每节写完立即更新 `chapters/chapter_<n>_qa.md`，引用 `quality_checklists.md` 勾项。
3. 与用户对话确认调整后再进入下一章。

## 4. 成稿交付阶段（04_article_delivery）
1. 汇总章节至 `article.md`，同时更新 `visual_plan.md` 和互动引导位置。
2. 核查“我”字计数、字数区间、视觉元素五处是否全部落地。

## 5. 质检与提示词维护阶段（05_quality_prompts）
1. 运行 `quality_checklists.md` 的全文/章节/节级检查，记录到 `articles/<topic>/qa.md`（可参考 `qa_report_template.md`）。
2. 将本次经验或提示词调整写入 `articles/<topic>/prompts.md`，并在仓库 `prompt_update_log.md` 留痕。
3. 只有当所有必需项通过或给出整改计划时，才进入提交环节。

## 6. 提交到 GitHub
1. 用户确认文章与 QA 均“OK”后，执行：  
   ```bash
   git add .
   git commit -m "feat: publish <topic> article"
   git push origin main
   ```
2. 若需合并或开 PR，遵循项目默认流程；不可跳过质检记录。

## 关键检查点
- 每章至少 1 个可查证案例 + 1 组有来源的数据。
- 全文 5 章结构完整，互动引导 ≥ 3，行动清单 3 份。
- `brief.md` 是唯一来源，若修改后需回到阶段 1 重新对齐。
