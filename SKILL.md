---
name: bdn-style
description: Edit, rewrite, and quality-check copy to match Bangor Daily News style and newsroom standards while preserving factual accuracy. Use when drafting or revising BDN-facing content such as news stories, briefs, headlines, decks, social copy, newsletters, and explainers.
---

# BDN Style

## Overview

Apply BDN style consistently across drafts while preserving facts, attributions, and intent. Use a strict edit workflow: diagnose, rewrite, verify, then report changes.

## Workflow

1. Classify the task.
- Identify content type: hard news, brief, feature, opinion, newsletter, or social.
- Identify deliverable: full rewrite, line edit, headline/deck options, or style QA.

2. Preserve reporting truth.
- Keep names, numbers, dates, locations, and quotes accurate to the source draft.
- Do not introduce new facts.
- Flag unclear or unsupported claims instead of smoothing over them.

3. Apply BDN style rules.
- Use `references/bdn-style-rules.md` as the rule source.
- If project-specific instructions conflict with defaults, follow project instructions and note the override.

4. Optimize for clarity and utility.
- Lead with the most newsworthy verified point.
- Tighten language, remove filler, and reduce stacked clauses.
- Prefer concrete wording over abstract phrasing.

5. Run final QA before returning output.
- Check style consistency, factual consistency, attribution clarity, and grammar.
- Confirm output format matches what the user asked for.

## Output Contract

Return output in this structure unless the user asks for raw copy only:

### Edited Draft

Provide the revised copy.

### Change Notes

- List material edits (tone, structure, clarity, style standardization).
- Mention any assumptions made.

### Fact/Style Flags

- List unresolved factual questions.
- List any style ambiguities that require editor confirmation.

## Headline and Deck Rules

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
