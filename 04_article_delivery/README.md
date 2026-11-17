# 04_成稿交付阶段

## 阶段目标
- 将已确认的章节草稿合并为 3,500-4,000 字的公众号文章。
- 确认视觉元素、互动引导、行动清单全部到位。

## 交付物
1. `articles/<topic>/04_article_delivery/article.md`：最终全文草稿。
2. `articles/<topic>/04_article_delivery/article_review.md`：供用户批注的全文副本。
3. `articles/<topic>/04_article_delivery/visual_plan.md`：图表/时间轴/书单/流程图/行动清单的具体素材或备注。
4. `articles/<topic>/04_article_delivery/visual_plan_review.md`：视觉计划的评审版（可选）。

## 文件规范
- `article.md` 应包含：
  - 标题 + 5 章章节名（各章标注字数或“约 xxx 字”）
  - 每节按“开头场景 → 案例 → 数据 → 结语”展开，并内联“【视觉/互动】”标签
  - 章尾或文末加“终审小结”，逐项勾选质量清单
- `article_review.md`：保留同版全文，用户可直接编辑或用引用块指出修改建议。
- `visual_plan.md` 采用表格描述 `序号/类型/位置/数据源/执行要点/状态`，明确设计需用的原始数据与格式。
- `visual_plan_review.md`：供运营/设计批注。

## 使用说明
1. 先参考 `article_template_v5.md` 确认整体结构与字数分配。
2. 使用 `article_prompt.md` 生成首稿，输入包括章节草稿、案例矩阵、质检记录，保存至 `article.md` 并复制到 `article_review.md`。
3. 提交 `article_review.md` 让用户批注，确认后同步修改回 `article.md`。
4. 将视觉素材与互动话术同步到 `visual_plan.md`，若用户需要审稿则在 `visual_plan_review.md` 留位。
5. 完成后运行 `../05_quality_prompts/quality_checklists.md` 中全文检查项。

## 相关文件
- `article_template_v5.md`：写作与排版的详细规范。
- `article_prompt.md`：用于生成整篇文章的提示词。

## 进入下一阶段前的检查
- [ ] `article_review.md`、`visual_plan_review.md` 中反馈已处理。
- [ ] 全文 5 章顺序完整，每章 2-4 节；“我”字使用 ≤ 15 次。
- [ ] 行动清单含指标、触发条件、操作、检查节奏。
