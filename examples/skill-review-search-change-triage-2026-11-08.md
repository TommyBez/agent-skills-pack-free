# Example: skill-review on search-change-triage

One real, report-only run of the free `skill-review` skill. The output below is the report the skill asks for in its "Done when", unedited apart from formatting.

| | |
| --- | --- |
| Skill used | [`skills/skill-review/`](../skills/skill-review/SKILL.md) (`SKILL.md` + [`references/rubric.md`](../skills/skill-review/references/rubric.md)) |
| Input | [`skills/search-change-triage/SKILL.md`](../skills/search-change-triage/SKILL.md) and its `references/` |
| Commit | `7d5c7f46563a201005983648f2227d48f9f7983f` (`main` of this repo; both skills read at this commit) |
| Run date | 8 November 2026, 11:52 CET (Europe/Rome, UTC+1) |
| Ran by | Claude Code, model Claude Opus 5.5 (`claude-opus-5-5`) |
| Mode | Report only: no file was edited |
| Inputs read | `search-change-triage/SKILL.md`, `references/classify-examples.md`, `references/evidence-pack.md`; for the sibling scan, `skills/skill-review/`. No network access beyond `git clone`. |

**Reproduce:** copy `skills/skill-review` into your agent's skills folder (for example `cp -R skills/skill-review .claude/skills/`), check out commit `7d5c7f4` of this repo, then ask:

> Use skill-review on skills/search-change-triage/SKILL.md. Report only, do not edit any file. Use the other skill in skills/ for the sibling scan.

The run used `skill-review` as it was at that commit. The same change that adds this file rewords one `skill-review` constraint about secrets; that line does not affect scoring. Scores can differ by a point between runs and models. The quotes and line numbers below refer to the files at the commit above.

## Score table

| # | Rubric line | Score | Quote or gap |
| --- | --- | --- | --- |
| 1 | Progressive disclosure | 1 | The body is thin (56 lines) and sends the dated detail to `references/` ("Dated examples and first-response notes (refresh from boards)", line 30; the evidence pack is loaded only "once you have a class from §2", line 34). Gap: the description is three sentences (39 words) and its middle sentence is a rule, not routing: "Never \"rewrite everything\" off a wobble." (line 3, repeated in the body at line 8). |
| 2 | Precise vs ambiguous | 2 | Explicit Done when and check: "the note names one class, links at least one official board (or documents the timeout), and chooses exactly one of wait / watch / act" (line 56). Context the agent cannot derive is given (source order, live board URLs, "Search Console dates are **Pacific Time**", line 12). Steps stay flexible. |
| 3 | Anti-rot | 1 | Durable structure is hand-written (four steps, ten named classes, "Keep your own dated watchlist", line 10), and the references are dated ("as of 26 Oct 2026", "Last refreshed 2 Nov 2026"). Gap: the body itself carries volatile facts that will expire: the "**September 2026 spam update** (complete 8 Oct 2026 …)" window in §4 (line 38), the "1 Oct 2026" example in §1 (line 17), and an 11-item "What we will not do" list in §5 (line 47) that reads as accumulated patches. |
| 4 | Ask > demand + boundaries | 2 | No blanket "ask first". Failures are left to the agent: "If Bing guidelines or OpenAI help time out, retry, use search snippets, a real browser, or Wayback" (line 24). The output is a note, and "Act now" items are recommendations inside it, not actions the skill takes. Minor gap in the boundary audit below (line 50). |
| 5 | Worth existing + catalog | 2 | Repeated work ("Use every Monday"), a task agents get wrong by default (overreacting to a wobble, trusting vendor blogs before official boards), and dated context a model does not have. No near-duplicate in this repo (see sibling scan). |

**Total: 8 / 10.**

## Soft notes

- **Description budget:** "Use every Monday, or when traffic / rankings / AI Overviews / AI citations moved, to classify the external search change and then choose wait, watch, or act. Never "rewrite everything" off a wobble. Not a property performance report." It has a when-not ("Not a property performance report.") and no "pick me" wording, but it is three sentences and puts a rule in the router. skill-review's own check ("the reviewed description is at most two sentences with a when-not") does not pass as written.
- **Sibling scan:** the only other skill in this repo is `skill-review` (audits `SKILL.md` files); no when-to-load collision. `search-change-triage` names three other skills (`technical-seo-2026-delta`, `aeo-answer-surface-playbook`, `geo-citation-playbook`, line 50) that are not in this repo, so no collision can be checked for them here. `references/evidence-pack.md` line 11 points to `../technical-seo-2026-delta/references/checklist.md`, which does not exist in this repo.
- **Done when:** present (lines 52–56), with a one-line Verify. No fix needed.
- **Boundary audit:** no always-ask or always-stop phrase found. One instruction with a real side effect has no ownership condition: "If a skill's facts moved, update the matching playbook … the same day" (line 50) edits other skills, which may be vendor-managed or not installed.

## Verdict

`ship` (8 / 10, band 8–10). Line 5 is 2 and no sibling overlaps, so `delete/merge` does not apply. The proposals below are small tightenings, not a rewrite.

## Paths changed

None. Report-only run.

## Proposals (for the author)

1. **Description (line 3):** drop "Never \"rewrite everything\" off a wobble." The body already says it at line 8. That leaves two sentences with the when-not.
2. **§4 Wait (line 38):** keep the durable rule ("residual ranking wobble after a completed spam update with no new dashboard incident") and move the September 2026 dates and fixed window to `references/classify-examples.md`, whose Spam row already has them.
3. **§1 item 2 (line 17):** keep "when one doc changes, diff its siblings … against a Wayback capture" and move the "1 Oct 2026" example to the Quality guidance row in `references/classify-examples.md`.
4. **§5 "What we will not do" (line 47):** keep the few durable entries (panic rewrites, "GEO schema", llms.txt-for-Google) and move the dated ones to `references/` so the body stops growing each week.
5. **Line 50 and `references/evidence-pack.md` line 11:** add a condition such as "if you own that skill and it is installed; otherwise note the change in the triage note". This also covers the checklist path that does not resolve in this repo.
6. **`references/classify-examples.md` Measurement row (line 10):** one table cell holds eleven dated items. Split it into a dated list or prune resolved items on the Monday refresh.

Each of 1–3 and 5 is in skill-review's "may apply without asking" set when you own the skill (description rewrite, moving inline detail to `references/`). None was applied in this run.

## Self-check

`skill-review` itself still matches the rubric shape: a thin `SKILL.md` body, scoring detail in `references/rubric.md`, and a Done when with a Verify line.
