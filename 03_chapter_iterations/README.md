# 03_章节迭代阶段

## 阶段目标
- 与用户逐章对话，确认每章的逻辑、案例、数据与语气。
- 输出可直接粘贴到正文的章节草稿，并附节级质检结果。

## 交付物
1. `articles/<topic>/03_chapter_iterations/segments/segment_<n>.md`：每章段落骨架。
2. `articles/<topic>/03_chapter_iterations/segments/segment_<n>_review.md`：用户对段落骨架的评语。
3. `articles/<topic>/03_chapter_iterations/chapters/stage_<round>/chapter_<n>.md`：扩写后的章节草稿。
4. `articles/<topic>/03_chapter_iterations/chapters/stage_<round>/chapter_<n>_review.md`：章节草稿的审稿副本（可选）。
5. `articles/<topic>/03_chapter_iterations/chapters/stage_<round>/chapter_<n>_qa.md`：该章节的质检记录。

## 文件规范
- `segments/segment_<n>.md`：按节列出方文山开头、案例、数据、结尾要点，便于讨论结构；保持 200 字以内。
- `segments/segment_<n>_review.md`：用户批注/打勾，可直接替换段落或提出疑问。
- `chapters/stage_<round>/chapter_<n>.md` 建议包含：
  - 章级简述（50 字内）
  - 每节的方文山式开头 + 案例描述 + 数据引用 + 刘震云式结尾
  - 视觉或互动提示（如“【视觉 3：书单卡片】”）
- `chapter_<n>_qa.md`：使用表格或 checklist 记录节级通过情况（场景感/案例/数据/视觉/备注），未完成项要写整改计划。

## 使用说明
1. 基于 `outline.md` 先生成 `segments/segment_<n>.md`，提交供用户在 `segment_<n>_review.md` 评语。
2. 用户确认后再使用 `chapter_prompt.md` 扩写为 `chapters/stage_<round>/chapter_<n>.md`。
3. 每节写完即在 `chapter_<n>_qa.md` 勾选节级清单；必要时创建 `chapter_<n>_review.md` 让用户直接改稿。
4. 迭代结束后，将确认的要点同步回 `02_synthesis/insights.md` 以保持一致。

## 相关文件
- `chapter_prompt.md`：逐章迭代提示词模板。
- `../05_quality_prompts/quality_checklists.md`：章级与节级质检列表。

## 进入下一阶段前的检查
- [ ] 所有 `segment_*_review.md`、`chapter_*_review.md` 中的意见已处理。
- [ ] 当前章全部节在 `chapter_<n>_qa.md` 中通过或给出整改计划。
- [ ] 视觉元素与互动引导已落位或注明“待插图”，并确认“我”字计数仍在 15 次以内。
