# 02_素材归纳阶段

## 阶段目标
- 将输入的提纲、案例、核心观点进行归纳，输出可执行的章节陈述。
- 补齐案例五要素与数据四要素，并将缺口反馈给用户。

## 交付物
1. `articles/<topic>/02_synthesis/cases.md`：表格化案例矩阵。
2. `articles/<topic>/02_synthesis/cases_review.md`：用户评语/补写案例的空间。
3. `articles/<topic>/02_synthesis/insights.md`：章节命题与数据引用。
4. `articles/<topic>/02_synthesis/insights_review.md`：用户评语/提问。

## 文件规范
- `cases.md` 推荐使用表格，列包含 `编号/主体/时间/动作/数据/结果/来源`，并保持数值写法为“数值 + 时间 + 主体 + 来源”，方便复制进章节。
- `cases_review.md`：用户可在此修正文案、补充来源或用勾选确认。
- `insights.md` 以章为单位列出 2-3 个命题，每条内容包含：
  - 场景句（≤20 字）
  - 对应案例编号
  - 数据引用（含四要素）
  - 待核事项/下一步问题
  - “我”字累计（若有第一人称）
- `insights_review.md`：保留用户提问/批注；Agent 同步处理后在正文打勾或回复。

## 使用说明
1. 先用 `case_prompt.md` 收集/补写详细案例。
2. 将输出整理进 `cases.md`，同步提交供用户在 `cases_review.md` 审阅。
3. 通过 `synthesis_prompt.md` 生成章节洞察，写入 `insights.md`；用户在 `insights_review.md` 留言。
4. Agent 根据评语更新正式文档，并打勾待办；保留 review 文件以便 diff。

## 相关文件
- `case_prompt.md`：标准化案例采集模板。
- `synthesis_prompt.md`：将提纲+案例+观点汇整为章节摘要的提示词。

## 进入下一阶段前的检查
- [ ] `cases_review.md`、`insights_review.md` 中的反馈已处理。
- [ ] 每个案例具备主体、时间、动作、数据、结果，并注明来源。
- [ ] `insights.md` 写清每章命题、数据引用与待确认事项。
