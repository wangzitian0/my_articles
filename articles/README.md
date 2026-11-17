# articles 目录规范

所有文章资产需存放在 `articles/<topic_slug>/` 结构中，全部文件采用 Markdown，并按照工作流编号拆分为 `01`-`05` 五个子目录。

## 顶层结构
1. `<topic_slug>/README.md`：记录主题信息、目录结构、提示词索引。
2. `<topic_slug>/01_brief_inputs/`：brief、outline、gap_list 及对应 review 文件。
3. `<topic_slug>/02_synthesis/`：案例矩阵、洞察摘要与 review 文件。
4. `<topic_slug>/03_chapter_iterations/`：segments、chapters/stage_<round>、章级 QA。
5. `<topic_slug>/04_article_delivery/`：article、visual_plan 及 review 文件。
6. `<topic_slug>/05_quality_prompts/`：qa、prompts 与 review 文件。

## 必备文件（每阶段）
| 阶段 | 正式文件 | Review 文件（可选） | 说明 |
| --- | --- | --- | --- |
| 01 | `brief.md` / `outline_raw.md` / `outline.md` / `gap_list.md` | `brief_review.md` | 提纲生成与缺口登记 |
| 02 | `cases.md` / `insights.md` | `cases_review.md` / `insights_review.md` | 素材归纳与命题确认 |
| 03 | `segments/segment_<n>.md` / `chapters/stage_<round>/chapter_<n>.md` / `chapter_<n>_qa.md` | `segment_<n>_review.md` / `chapter_<n>_review.md` | 段落骨架 + 章节草稿 + 章级 QA |
| 04 | `article.md` / `visual_plan.md` | `article_review.md` / `visual_plan_review.md` | 全文合稿与视觉计划 |
| 05 | `qa.md` / `prompts.md` | `qa_review.md` / `prompts_review.md` | 质检结果与提示词更新 |

## 使用建议
- 按阶段 README 的“进入下一阶段前检查”执行，review 文件保留在仓库中方便 git diff。
- 若某文件暂未产出，请建立同名 Markdown 并写明“待补充”，避免缺少占位。
- 历史版本建议通过 Git 分支或 Tag 管理，无需额外拷贝目录。
