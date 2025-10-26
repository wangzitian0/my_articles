# 05_质检与提示词维护阶段

## 阶段目标
- 对全文、章节、节级进行质检，确保全部清单项通过。
- 根据复盘结果更新提示词与 Agent 设定，形成正向循环。

## 交付物
1. `articles/<topic>/qa.md`：记录全文/章节/节级检查状态与待修事项。
2. `articles/<topic>/prompts.md`：总结本次提示词/流程调整。
3. `prompt_update_log.md`：在仓库内沉淀可复用经验。

## 使用说明
1. 使用 `quality_checklists.md` 逐项打勾，并在 `articles/.../qa.md` 中记录结果。
2. 当质检暴露新的需求时，更新对应阶段的提示词，并在 `prompt_update_log.md` 中留档。
3. `agent.md` 需随流程变化保持最新，便于快速上手。

## 相关文件
- `quality_checklists.md`：自上而下的质检标准。
- `agent.md`：Codex 写作 Agent 的角色设定与全流程职责。
- `prompt_update_guide.md`：如何在质检后总结经验并回写提示词。

## 完成标准
- [ ] 所有质检项均通过或列出整改计划。
- [ ] 提示词与 Agent 描述已根据最新流程更新。
- [ ] 重要经验沉淀在 `prompt_update_log.md`，便于下次复用。
