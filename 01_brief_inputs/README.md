# 01_输入提纲阶段

## 阶段目标
- 收集用户提供的提纲、案例、核心观点，并核对 3 秒钩子与 3 重痛点。
- 明确缺失素材（报告/案例/书籍）与所需数据四要素，为后续归纳做准备。

## 交付物
1. `articles/<topic>/01_brief_inputs/brief.md`：用户提供的原始简报。
2. `articles/<topic>/01_brief_inputs/outline_raw.md`：根据 `outline_prompt.md` 生成的提纲初稿（保留以便审稿）。
3. `articles/<topic>/01_brief_inputs/brief_review.md`：用户对 brief 与提纲初稿的评语/批注。
4. `articles/<topic>/01_brief_inputs/outline.md`：吸收评语后的正式提纲。
5. `articles/<topic>/01_brief_inputs/gap_list.md`：缺失数据、案例、视觉等待补项。

## 文件规范
- `brief.md`：保持用户原文，不在其中直接写评语。
- `outline_raw.md`：运行 `outline_prompt.md` 后的完整输出，包含章节、场景句、案例占位、数据占位、视觉/互动标记。
- `brief_review.md`：使用 `> Reviewer:`、`- [ ]` 等语法逐条点评，可直接引用 `outline_raw.md` 片段。
- `outline.md`：基于评语整理的正式结构，至少包含五章、每章 2-3 节，并标注：
  - 场景句（人物+感受+时间感）
  - 拟引用案例（主体 + 时间 + 动作）
  - 数据占位（需补的数值/时间/主体/来源）
  - 对应视觉元素/互动引导标签（如【视觉 1】、【互动引导】）
- `gap_list.md`：以清单收集缺口，写明用途、所需指标/来源、负责人/状态，便于阶段二认领。

## 使用说明
1. 用户在 `brief.md` 填写主题、痛点、数据诉求。
2. Agent 运行 `outline_prompt.md`，将输出粘贴至 `outline_raw.md` 并提交。
3. 用户在 `brief_review.md` 评论/修改，确认后 Agent 根据反馈更新 `outline.md` 与 `gap_list.md`。
4. 保留 `outline_raw.md` 以便 git diff 回溯初稿。

## 相关文件
- `outline_prompt.md`：用于快速生成符合 V5 模板的提纲，包含视觉元素与互动引导占位要求。

## 进入下一阶段前的检查
- [ ] `brief_review.md` 反馈已吸收至 `outline.md`。
- [ ] 5 章骨架齐全，每章 2-3 节，并填充案例/数据占位。
- [ ] 缺口均记录在 `gap_list.md`，方便 02 阶段补齐。
