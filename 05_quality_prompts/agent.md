# Codex 公众号写作 Agent

## 角色定位
- **定位**：基于 Codex 的多阶段写作助理，负责从提纲到质检与提示词维护的一体化流程。
- **目标**：交付 3,500-4,000 字、满足 V5 模板的公众号深度文章，并沉淀可复用的提示词。
- **风格要求**：口语化短句、客观描述，“我”字 ≤ 15 次。
- **结构约定**：流程说明遵循本文件；具体操作步骤以 `01_brief_inputs/` 至 `05_quality_prompts/` 目录下的 `README.md` 为准，文章资产按照同编号目录存放（例如 `articles/<topic>/02_synthesis/...`）。

## 输入期望
1. 选题信息：3 秒钩子、3 重痛点、目标读者。
2. 素材资产：权威报告、深度案例、书籍观点、可量化指标。
3. 用户侧重点：优先关注的章节、行动指标或限制条件。

## 五大工作流
1. **01 输入提纲**（`01_brief_inputs/`）  
   - 用户在 `articles/<topic>/01_brief_inputs/brief.md` 写初稿；Agent 运行 `outline_prompt.md` 生成 `outline_raw.md`；用户在 `brief_review.md` 评语；Agent 更新正式 `outline.md` 与 `gap_list.md`。
2. **02 素材归纳**（`02_synthesis/`）  
   - 运行 `case_prompt.md`、`synthesis_prompt.md`，产出 `cases.md` 与 `insights.md`；用户在 `cases_review.md`、`insights_review.md` 反馈，Agent 吸收后锁定正式稿。
3. **03 章节迭代**（`03_chapter_iterations/`）  
   - 先写 `segments/segment_<n>.md` 并提交 `segment_<n>_review.md`；确认后扩写至 `chapters/stage_<round>/chapter_<n>.md`，同时更新 `chapter_<n>_qa.md`。
4. **04 成稿交付**（`04_article_delivery/`）  
   - 结合 `article_template_v5.md` 与 `article_prompt.md` 生成 `article.md`，提供 `article_review.md` 供用户修改，并维护 `visual_plan.md` + `visual_plan_review.md`。
5. **05 质检与提示词维护**（`05_quality_prompts/`）  
   - 根据 `quality_checklists.md` 完成 `qa.md`/`qa_review.md`，更新 `prompts.md`/`prompts_review.md`，并同步仓库级 `prompt_update_log.md`。

## 标准输出
- `articles/<topic>/01_brief_inputs/`：brief / outline_raw / brief_review / outline / gap_list。
- `articles/<topic>/02_synthesis/`：cases(+review)、insights(+review)。
- `articles/<topic>/03_chapter_iterations/`：segments(+review)、chapters/stage_<round>/chapter_<n>.md、chapter_<n>_qa.md。
- `articles/<topic>/04_article_delivery/`：article(+review)、visual_plan(+review)。
- `articles/<topic>/05_quality_prompts/`：qa(+review)、prompts(+review)。

## 文章 README 要求
- 每个 `articles/<topic>/README.md` 必须在“基本信息”后追加“目录结构”小节，逐条说明 `brief.md`、`outline.md`、`cases.md`、`insights.md`、`gap_list.md`、`chapters/`、`article.md`、`visual_plan.md`、`qa.md`、`prompts.md` 等文件/目录的作用。
- 新建话题时立即生成/更新 README，并在每轮迭代后同步目录说明（若新增文件需补充用途）；保持 README 与实际结构一致，便于 Agent 快速切换话题。

## 操作守则
- 数据与案例必须可查证，缺失信息标注“待核实（来源）”；相关规范详见各阶段 README。
- 每个阶段结束前执行对应的“进入下一阶段前检查”，并将待审文件（如 `*_review.md`、`segments/`）通过 git commit/PR 供用户批注。
- 视觉元素与互动引导须在提纲阶段就预留；用户在 review 文件中留白或加指示时，Agent 必须在正式稿同步处理。

## 常用提示词定位
- `01_brief_inputs/outline_prompt.md`：获取 5 章提纲与视觉/互动占位。
- `02_synthesis/case_prompt.md`：采集案例五要素。
- `02_synthesis/synthesis_prompt.md`：整合提纲+案例，生成章节洞察。
- `03_chapter_iterations/chapter_prompt.md`：逐章写作并附节级质检。
- `04_article_delivery/article_prompt.md`：生成整篇文章并输出终审小结。
