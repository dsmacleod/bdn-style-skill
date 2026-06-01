---
name: bdn-style
description: Edit, rewrite, and quality-check copy to match Bangor Daily News style and story standards while preserving factual accuracy. Use when drafting or revising BDN-facing content such as breaking news, enterprise stories, profiles, explainers, investigations, projects, headlines, and decks, especially when checking for required structure such as a nut graf.
---

# BDN Style

## Overview

Apply BDN standards consistently across drafts while preserving facts, attributions, and intent. Use a strict edit workflow: classify, diagnose, revise, verify, then report structured flags.

## Workflow

1. Classify the task.
- Identify story type: breaking, enterprise, profile, explainer, investigation, project, or unknown.
- Identify deliverable: full rewrite, line edit, headline/deck options, or style QA.

2. Preserve reporting truth.
- Keep names, numbers, dates, locations, and quotes accurate to the source draft.
- Do not introduce new facts.
- Flag unclear or unsupported claims instead of smoothing over them.

3. Apply BDN style and story standards.
- Use `references/bdn-style-rules.md` for language and usage rules.
- Use `references/bdn-story-standards.md` for newsroom values, story-type requirements, word-count caps, and structure checks.
- If project-specific instructions conflict with defaults, follow project instructions and note the override.

4. Run mandatory structure checks.
- **Nut graf (always check)**: Scan early paragraphs (2-8) for a nut graf. A nut graf must establish stakes, significance, or timeliness — not just provide background. Treat a paragraph as a nut graf only if it explains all three: what the story is about now, why it matters to the audience, and stakes or context (the how/why). For ALL non-breaking stories, flag if no qualifying nut graf is present. A missing nut graf is one of the most important flags you can raise.
- **Attribution**: Flag front-loaded attribution ("Officials announced that X" → flip it). Flag stenography patterns (multiple consecutive paragraphs starting with "[Name] said").
- **Repeated words**: Flag sentences that repeat the same word unnecessarily.
- **Redundant sections**: Flag paragraphs that repeat earlier information or add nothing new — recommend cutting.
- **"In other business"**: Flag unrelated agenda items tacked onto meeting stories for removal. Do not copyedit — recommend cutting.
- **Overloaded ledes**: Flag ledes that try to cram multiple ideas into one sentence.

5. Optimize for clarity and utility.
- Lead with the most newsworthy verified point.
- Tighten language, remove filler, and reduce stacked clauses.
- Prefer concrete wording over abstract phrasing.

6. Run final QA before returning output.
- Check story-type compliance, style consistency, factual consistency, attribution clarity, and grammar.
- Confirm output format matches what the user asked for.

## Output Contract

Return output in this structure unless the user asks for raw copy only:

### Edited Draft

Provide the revised copy.

### Change Notes

- List material edits (tone, structure, clarity, style standardization).
- Mention any assumptions made.

### Standards Flags

- Return one line per flag in this exact format:
`FLAG_CODE | severity | evidence`
- Supported flag codes:
  - `MISSING_NUT_GRAF` (high): Any non-breaking story lacks a qualifying nut graf near the top.
  - `WEAK_NUT_GRAF` (medium): Candidate paragraph exists but misses one or more required nut-graf elements.
  - `WORD_COUNT_EXCEEDED` (high): Story exceeds BDN max for its type.
  - `MISSING_STORY_TYPE` (medium): Story type cannot be confidently inferred.
  - `MISSING_EXPLAINER_LABEL` (medium): Explainer draft is not labeled "explainer."
  - `MISSING_EXPLAINER_QA_STRUCTURE` (medium): Explainer is not organized by audience-facing questions.
  - `HEADLINE_RED_FLAG` (high): Headline contains a red-flag word, jargon, bureaucratic language, or violates a BDN headline rule.
  - `FRONT_LOADED_ATTRIBUTION` (medium): Attribution leads the sentence instead of the news.
  - `STENOGRAPHY_PATTERN` (medium): Multiple consecutive paragraphs begin with "[Name] said" attribution.
  - `REDUNDANT_SECTION` (medium): Paragraph repeats information already stated earlier in the story.
  - `CUT_IN_OTHER_BUSINESS` (medium): Meeting story includes unrelated agenda items that should be separate stories.
  - `OVERLOADED_LEDE` (medium): Lede tries to accomplish too many things at once.
- If no issues are found, return:
`NONE`

## Headline and Deck Rules

When reviewing or writing headlines:

- Evaluate against the full BDN headline rules in `references/bdn-style-rules.md`.
- Flag red-flag words from the list, missing W's (need at least two), commas, jargon, bureaucratic language, and weak/vague verbs.
- Do not flag verbs that are simply "not the strongest possible" — only flag genuinely weak or vague verbs (e.g., "addresses," "deals with"). A verb like "approves" is concrete and acceptable.
- Do not add information to a headline rewrite that isn't in the original (e.g., inventing a timeframe or specifying details not in the headline).
- Avoid bureaucratic/legalistic words: "moratorium" → "pause" or "ban"; "ordinance" → "rule"; "resolution" → cut it or describe the action.

When asked for headline/deck options:

- Provide 5 options by default.
- Keep language specific and factual.
- Avoid clickbait framing.
- Avoid hedging that weakens clear facts.
- Include at least one straightforward utility option.

## Guardrails

- Do not fabricate sources, quotes, or statistics.
- Do not overstate uncertainty when source facts are clear.
- Do not flatten voice into generic marketing tone.
- Do not remove nuance that changes meaning.

## References

- Default style rules: `references/bdn-style-rules.md`
- Story standards and nut-graf requirements: `references/bdn-story-standards.md`
