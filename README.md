# bdn-style

A Claude skill that edits, rewrites, and quality-checks copy so it matches Bangor Daily News style **and** BDN story standards — while keeping every fact, name, number, and quote true to the original draft. Think of it as a copy desk that not only fixes style and grammar but also checks whether a story actually does its job: Does it have a real nut graf? Is the lede overloaded? Is attribution buried? Are there redundant or off-topic sections that should be cut?

## What it does

- Classifies the story type (breaking, enterprise, profile, explainer, investigation, project).
- Applies BDN language/usage rules and newsroom story standards.
- Runs mandatory structure checks: nut graf, attribution, repeated words, redundant sections, "in other business" pileups, and overloaded ledes.
- Writes and critiques headlines and decks against BDN headline rules.
- Returns the edited draft plus structured flags so an editor can see exactly what's wrong and why.

## Inputs

- A draft, passage, headline, or deck to edit or check (pasted in or referenced).
- Optionally, the desired deliverable: full rewrite, line edit, headline/deck options, or style-only QA.
- Optional project-specific instructions, which override the defaults (the override is noted in the output).

## Outputs

- **Edited Draft** — the revised copy (unless you ask for flags only).
- **Change Notes** — material edits made and any assumptions.
- **Standards Flags** — one line per issue in `FLAG_CODE | severity | evidence` format, or `NONE`. Flag codes include `MISSING_NUT_GRAF`, `WEAK_NUT_GRAF`, `WORD_COUNT_EXCEEDED`, `MISSING_STORY_TYPE`, `MISSING_EXPLAINER_LABEL`, `MISSING_EXPLAINER_QA_STRUCTURE`, `HEADLINE_RED_FLAG`, `FRONT_LOADED_ATTRIBUTION`, `STENOGRAPHY_PATTERN`, `REDUNDANT_SECTION`, `CUT_IN_OTHER_BUSINESS`, and `OVERLOADED_LEDE`.

## Contents

- `SKILL.md` — main skill instructions, workflow, and output contract.
- `references/bdn-style-rules.md` — canonical BDN style and headline rules.
- `references/bdn-story-standards.md` — newsroom values, story-type requirements, word-count caps, and structure checks (nut graf, etc.).
- `agents/openai.yaml` — UI metadata.
