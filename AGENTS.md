<!-- WS_STATIC_START adapter=rules-v2 inputs=122ba4e4e7af63f18484c00643769106529498d0969434130d77e81fc255382c -->
<!-- Generated file: do not edit by hand. These rules are maintained in the owner's rule source and re-rendered here. -->

## Article workflow

Goal: using this repository's templates and prompts, write one in-depth WeChat
Official Account article of 3,500 to 4,000 Chinese characters, and push it to
GitHub only after the user confirms "OK".

### 0. Conventions

- All article assets live in `articles/<topic>/`; the key prompts are gathered
  in `brief.md`.
- Writing follows the five-stage process in `README.md` and the style
  constraints in `05_quality_prompts/agent.md`.
- Every stage delivers Markdown files. Create an empty file marked "to be
  filled" first when needed.

### 1. Brief and outline (`01_brief_inputs`)

1. The user updates `articles/<topic>/brief.md` with the topic, pain points,
   cases and the data wanted.
2. Run `01_brief_inputs/outline_prompt.md` to produce a structured outline in
   `outline.md`.
3. Record material gaps in `gap_list.md`, marking visual and interaction
   placeholders.

### 2. Material synthesis (`02_synthesis`)

1. Use `case_prompt.md` and `synthesis_prompt.md` to fill in cases and data,
   written to `cases.md` and `insights.md`.
2. Every data point states four things: the value, the time, the subject, and
   the source. Anything missing stays in `gap_list.md`.

### 3. Chapter iterations (`03_chapter_iterations`)

1. Write chapter by chapter following `chapter_prompt.md`, into
   `chapters/chapter_<n>.md`.
2. After each section, update `chapters/chapter_<n>_qa.md` at once, ticking
   items from `quality_checklists.md`.
3. Confirm adjustments with the user before moving to the next chapter.

### 4. Article delivery (`04_article_delivery`)

1. Assemble the chapters into `article.md`, and update `visual_plan.md` and the
   interaction prompts.
2. Check how often the first person is used, the length range, and that all
   five visual elements are in place.

### 5. Quality checks and prompt maintenance (`05_quality_prompts`)

1. Run the full-text, chapter and section checks in `quality_checklists.md`,
   recording results in `articles/<topic>/qa.md` (see `qa_report_template.md`).
2. Write this round's lessons or prompt changes to `articles/<topic>/prompts.md`,
   and log them in the repository's `prompt_update_log.md`.
3. Move to publishing only when every required item passes or has a
   remediation plan.

### 6. Publishing to GitHub

1. Only after the user confirms both the article and the QA as "OK", commit and
   push the article.
2. If a merge or PR is needed, follow the project's default flow. The QA record
   is never skipped.

### Key checkpoints

- Each chapter has at least one verifiable case and one sourced data set.
- The article has all five chapters, at least three interaction prompts, and
  three action checklists.
- `brief.md` is the single source; after changing it, go back to stage 1 and
  realign.
<!-- WS_STATIC_END -->
