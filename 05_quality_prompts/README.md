# 05_质检与提示词维护阶段

## 阶段目标
- 对全文、章节、节级进行质检，确保全部清单项通过。
- 根据复盘结果更新提示词与 Agent 设定，形成正向循环。

## 交付物
1. `articles/<topic>/05_quality_prompts/qa.md`：记录全文/章节/节级检查状态与待修事项。
2. `articles/<topic>/05_quality_prompts/qa_review.md`：用户对质检记录的反馈（可选）。
3. `articles/<topic>/05_quality_prompts/prompts.md`：总结本次提示词/流程调整。
4. `articles/<topic>/05_quality_prompts/prompts_review.md`：用户对提示词改动的确认。
5. `prompt_update_log.md`：仓库级提示词变更日志。

## 文件规范
- `qa.md` 建议包含：
  - 全文级总结（状态 + 说明）
  - 章节级表格（章节/通过情况/待改问题/负责人）
  - 小节级表格（章节-小节/通过情况/备注）
  - 结论区列出下一步措施与提示词更新情况
- `qa_review.md`：用户可对质检项进行确认或补充整改说明。
- `prompts.md` 在每次迭代后记录：
  - 影响到的阶段（Outline/Chapter/Article/QA 等）
  - 新增/调整的提示词要点
  - 与 `prompt_update_log.md` 关联的说明
- `prompts_review.md`：用于用户确认或补写建议。

## 使用说明
1. 使用 `quality_checklists.md` 逐项打勾，并在 `articles/.../05_quality_prompts/qa.md` 中记录结果。
2. 若需要审稿，将 `qa.md` 复制到 `qa_review.md` 供用户补充，确认后同步更新正式文件。
3. 当质检暴露新的需求时，更新 `prompts.md` 并在 `prompts_review.md` 标注给用户确认；最终变更写入仓库级 `prompt_update_log.md`。
4. `agent.md` 按需同步最新流程说明。

## 相关文件
- `quality_checklists.md`：自上而下的质检标准。
- `agent.md`：Codex 写作 Agent 的角色设定与全流程职责。
- `prompt_update_guide.md`：如何在质检后总结经验并回写提示词。

## 完成标准
- [ ] 用户在 `qa_review.md`、`prompts_review.md` 的反馈已处理或说明。
- [ ] 所有质检项均通过或列出整改计划。
- [ ] 提示词与 Agent 描述已根据最新流程更新。
- [ ] 重要经验沉淀在 `prompt_update_log.md`，便于下次复用。
