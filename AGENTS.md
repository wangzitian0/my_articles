<!-- WS_STATIC_START adapter=rules-v2 inputs=fd4f3afe72f59c6e8e3fc218891ed27338569e7f988e1d0842465f1dcd9910d8 -->
<!-- Generated file: do not edit by hand. These rules are maintained in the owner's rule source and re-rendered here. -->

## Production reservation

The single definition of the production reservation. Other tiers, skills and gates point here.

- **Only a production change returns to the owner.** A production change alters what production runs or stores. Examples: a deploy, promote or apply to production; a production secret write; a manual production data write or deletion. Also a production DNS, route or host change, and a release that cannot be recalled. Code that reaches production with no later owner approval, for example on a schedule, counts too. Each Repo tier names its production paths.
- **Approval:** the owner approves the exact commit SHA or release tag of each production change, and is present when it runs. A "deploy" reply covers only the release that it names. Immediately before a production dispatch, get a live reply from the owner.
- **Self-guard:** an edit that removes, narrows or redefines the production reservation needs the owner's approval of its head SHA. This includes an edit that makes fewer production runs wait for the owner. Examples: the owner-approval check of a deploy path, a production job classification, the settings of a production environment. It also includes an edit that removes or weakens a pin of this section or its dev_env pin test. The same holds for the required check that runs the test.
- **Everything else is the agent's:** in a repository that the owner owns, every merge, staging and canary deploy, and release tag. Also rule text, skills, gate code, data and tests, required-check workflows and release code. Before you merge gate or release code, a read-only reviewer that did not write it checks the head. The review states whether the gate gets stricter, stays equal or gets looser. A looser edit in the self-guard list follows the self-guard.
- **Every other hold is a defect:** a rule, skill, label or gate exit code that holds non-production work for the owner. Do the work, then fix the hold. The dev_env check `ws_owner_scope` fails on it.

## Article workflow

Goal: using this repository's templates and prompts, write one in-depth WeChat
Official Account article of 3,500 to 4,000 Chinese characters. A push of the
article to GitHub is this repository's production release.

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
3. Continue to the next chapter. Ask the user about a chapter only when its business
   intent is unclear.

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

1. Commit as you work. Push the article, which is the production release, only
   after the user confirms the article and the QA as "OK".
2. If a merge or PR is needed, follow the project's default flow. The QA record
   is never skipped.

### Key checkpoints

- Each chapter has at least one verifiable case and one sourced data set.
- The article has all five chapters, at least three interaction prompts, and
  three action checklists.
- `brief.md` is the single source; after changing it, go back to stage 1 and
  realign.
<!-- WS_STATIC_END -->
