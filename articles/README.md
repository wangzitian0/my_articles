# articles 目录规范

所有文章资产需存放在 `articles/<topic_slug>/` 结构中，全部文件使用 Markdown。

## 层级说明
1. `<topic_slug>/README.md`：记录文章主题、目标读者、创建人、最近更新时间。
2. `<topic_slug>/` 直接包含本次创作所需的全部 Markdown 文件。

## 目录标准文件
| 文件 | 说明 |
| --- | --- |
| `outline.md` | 由 01 阶段输出的章节提纲与视觉/互动占位 |
| `gap_list.md` | 素材缺口记录（报告/数据/案例） |
| `cases.md` | 案例矩阵与数据来源列表 |
| `insights.md` | 归纳后的关键观点与待确认事项 |
| `chapters/chapter_<n>.md` | 03 阶段产物，每章一文件 |
| `chapters/chapter_<n>_qa.md` | 章/节级质检记录 |
| `visual_plan.md` | 视觉与互动素材清单 |
| `article.md` | 04 阶段合并后的全文草稿 |
| `qa.md` | 05 阶段的全文质检报告 |
| `prompts.md` | 本次迭代新增/调整的提示词摘要 |
| `brief.md`（可选） | 汇总主题提示词、情绪、关键论据 |

## 使用建议
- 若要保留历史版本，请直接依赖 Git 分支或 Tag，而非额外的子目录。
- 若某文件暂未产出，请建立同名 Markdown 并写明“待补充”，避免缺少占位。
