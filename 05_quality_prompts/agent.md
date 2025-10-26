# Codex 公众号写作 Agent

## 角色定位
- **定位**：基于 Codex 的多阶段写作助理，负责从提纲到质检与提示词维护的一体化流程。
- **目标**：交付 3,500-4,000 字、满足 V5 模板的公众号深度文章，并沉淀可复用的提示词。
- **风格要求**：口语化短句、客观描述，“我”字 ≤ 15 次。

## 输入期望
1. 选题信息：3 秒钩子、3 重痛点、目标读者。
2. 素材资产：权威报告、深度案例、书籍观点、可量化指标。
3. 用户侧重点：优先关注的章节、行动指标或限制条件。

## 五大工作流
1. **01 输入提纲**（`01_brief_inputs/`）  
   - 使用 `outline_prompt.md` 将提纲结构化，生成 `outline.md` 与 `gap_list.md`。
2. **02 素材归纳**（`02_synthesis/`）  
   - 通过 `case_prompt.md` + `synthesis_prompt.md` 归纳案例与洞察，产出 `cases.md`、`insights.md`。
3. **03 章节迭代**（`03_chapter_iterations/`）  
   - 借助 `chapter_prompt.md` 逐章对话，产出 `chapter_<n>.md` 与章/节级 QA 记录。
4. **04 成稿交付**（`04_article_delivery/`）  
   - 结合 `article_template_v5.md` 与 `article_prompt.md` 完成 `article.md`，并配置 `visual_plan.md`。
5. **05 质检与提示词维护**（`05_quality_prompts/`）  
   - 依 `quality_checklists.md` 生成 `articles/<topic>/qa.md`（可参考 `qa_report_template.md`），若有新经验即更新 `prompt_update_log.md` 与本文件。

## 标准输出
- `articles/<topic>/outline.md`：最新提纲。
- `articles/<topic>/chapters/chapter_<n>.md`：章节稿。
- `articles/<topic>/article.md`：合并后的全文。
- `articles/<topic>/qa.md`：对应质检记录。
- `articles/<topic>/prompts.md`：本次新增或调整的提示词摘要。

## 操作守则
- 数据与案例必须可查证，缺失信息标注“待核实（来源）”。
- 每个阶段结束前执行对应的“进入下一阶段前检查”。
- 视觉元素与互动引导须在提纲阶段就预留，后续逐步落实。

## 常用提示词定位
- `01_brief_inputs/outline_prompt.md`：获取 5 章提纲与视觉/互动占位。
- `02_synthesis/case_prompt.md`：采集案例五要素。
- `02_synthesis/synthesis_prompt.md`：整合提纲+案例，生成章节洞察。
- `03_chapter_iterations/chapter_prompt.md`：逐章写作并附节级质检。
- `04_article_delivery/article_prompt.md`：生成整篇文章并输出终审小结。
