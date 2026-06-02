# bdn-style

A Claude skill that helps editors catch Bangor Daily News style and story-standards issues in a draft — while keeping every fact, name, number, and quote true to the original. It's a second set of eyes, not a replacement for editing: it watches for the things a busy editor might miss and flags them, so the editor stays in control of the final copy. Does the story have a real nut graf? Is the lede overloaded? Is attribution buried? Are there redundant or off-topic sections worth cutting?

## What it does

- Classifies the story type (breaking, enterprise, profile, explainer, investigation, project).
- Checks copy against BDN language/usage rules and newsroom story standards.
- Runs structure checks: nut graf, attribution, repeated words, redundant sections, "in other business" pileups, and overloaded ledes.
- Reviews headlines and decks against BDN headline rules and can suggest options.
- Returns a suggested revision plus structured flags so the editor can see exactly what's flagged and why, and decide what to act on.

## Inputs

- A draft, passage, headline, or deck to edit or check (pasted in or referenced).
- Optionally, the desired deliverable: full rewrite, line edit, headline/deck options, or style-only QA.
- Optional project-specific instructions, which override the defaults (the override is noted in the output).

## Outputs

- **Edited Draft** — a suggested revision (unless you ask for flags only); the editor decides what to keep.
- **Change Notes** — material edits made and any assumptions.
- **Standards Flags** — one line per issue in `FLAG_CODE | severity | evidence` format, or `NONE`. Flag codes include `MISSING_NUT_GRAF`, `WEAK_NUT_GRAF`, `WORD_COUNT_EXCEEDED`, `MISSING_STORY_TYPE`, `MISSING_EXPLAINER_LABEL`, `MISSING_EXPLAINER_QA_STRUCTURE`, `HEADLINE_RED_FLAG`, `FRONT_LOADED_ATTRIBUTION`, `STENOGRAPHY_PATTERN`, `REDUNDANT_SECTION`, `CUT_IN_OTHER_BUSINESS`, and `OVERLOADED_LEDE`.

## Contents

- `SKILL.md` — main skill instructions, workflow, and output contract.
- `references/bdn-style-rules.md` — canonical BDN style and headline rules.
- `references/bdn-story-standards.md` — newsroom values, story-type requirements, word-count caps, and structure checks (nut graf, etc.).
- `agents/openai.yaml` — UI metadata.
