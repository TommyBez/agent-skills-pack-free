---
name: skill-review
description: Use when auditing, tightening, or deciding whether to keep one agent SKILL.md. Not for writing product code or inventing skill content you have not read.
---

# Skill review

Audit one `SKILL.md` (and optionally tighten it) against a five-line rubric for skill craft, routing, and catalog fit.

**Scoring detail:** [references/rubric.md](references/rubric.md)

## How

Read the target frontmatter and body, plus its `references/` and `scripts/` if present. Score it with the rubric, including a quick sibling scan for when-to-load collisions with other skills in the same library. Prefer regenerating a weak section from its goal and constraints over stacking patches. Leave runtime discovery (which files exist, what the error says) to the agent that will run the skill under review. Do not hard-code their paths here.

## Constraints

- Skills you own: edit in place. Vendor, plugin, or managed skills you do not own: report only, never edit.
- **May apply without asking:** rewrite the description into a short when-to-use with a when-not (no "pick me" wording); trim over-specified steps into goal + constraints; add a one-line **Done when** / verification; soften a blanket "ask first" that is not tied to a real side effect; move an inline dump into `references/` and link it; fix broken relative links inside the skill folder; drop duplicate always-on filler.
- **Needs the owner's OK first:** delete, merge, change of purpose, rewriting more than about 40% of the body, any change to how a skill handles secrets. Never ask for, paste or repeat a secret value; if a reviewed skill contains one, point to its file and line only.
- Never invent file contents. Unknown owner: propose, do not write. One skill per fix pass; batch reports are fine. Keep the author's voice. Prefer a merge or a clearer description over adding another overlapping skill.

## Done when

- Score table for the five rubric lines (0–2 each) with one concrete quote or gap per line
- Soft notes from the rubric called out (description budget, sibling scan, Done when, boundary audit)
- Verdict: `ship` · `tighten` · `rewrite` · `delete/merge`
- List of paths you changed (if any) and proposals left for a human or the author
- Self-check: this skill's own shape still matches the rubric (thin body, detail in `references/`)

**Verify:** the reviewed description is at most two sentences with a when-not; soft notes appear in the report; detailed scoring stays in `references/rubric.md`.
