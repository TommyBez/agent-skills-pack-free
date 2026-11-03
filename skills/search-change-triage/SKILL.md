---
name: search-change-triage
description: Use every Monday, or when traffic / rankings / AI Overviews / AI citations moved, to classify the external search change and then choose wait, watch, or act. Never "rewrite everything" off a wobble. Not a property performance report.
---

# Weekly search-change triage

Classify what actually changed, then prescribe wait / measure / act. Never "rewrite everything" off a wobble.

Official boards first, trade press second, vendor blogs last. Keep your own dated watchlist of the live URLs below, and write a short dated research note when a run finds material change, so the next run starts from it.

Search Console dates are **Pacific Time**. Convert them to the reader's time zone before reporting.

## 1. Official boards (15 minutes)

1. [Google Search Status Dashboard — Ranking](https://status.search.google.com/products/rGHU1u87FJnkP6W2GwMi/history)
2. [Search Central blog](https://developers.google.com/search/blog) + [docs changelog](https://developers.google.com/search/updates) + RSS `https://developers.google.com/search/updates/search_docs_updates.rss`. The changelog does not list every guidance edit: when one doc changes, diff its siblings (e.g. gen-AI guidance + helpful content changed together on 1 Oct 2026) against a Wayback capture
3. [Search product blog](https://blog.google/products-and-platforms/products/search/) only if a product event landed
4. Bing Webmaster Guidelines (a JavaScript single-page app: if a plain fetch returns only a JS shell, use search snippets or a real browser; do not treat an empty shell as "no GEO section") + [blogs.bing.com](https://blogs.bing.com) + Microsoft Advertising GEO posts
5. OpenAI [ChatGPT Search help](https://help.openai.com/en/articles/9237897-searching-the-web-with-chatgpt) + [API web-search](https://developers.openai.com/api/docs/guides/tools-web-search) + [bots](https://developers.openai.com/api/docs/bots)
6. Anthropic web-search docs; Perplexity [changelog](https://docs.perplexity.ai/docs/resources/changelog) + [crawlers](https://docs.perplexity.ai/docs/resources/perplexity-crawlers)
7. SEJ / SEL / SERoundtable / SparkToro / Aleyda **after** official boards, last 7 days only

If Bing guidelines or OpenAI help time out, retry, use search snippets, a real browser, or Wayback. Update your watchlist the same day if a URL dies or redirects.

## 2. Classify

Pick one class, then wait / watch / act. Durable classes: broad core · spam · spam policy (geo split) · Discover-only · product/UI · measurement · docs/rich-result sunset · quality guidance · model-citation swing · on-site.

Dated examples and first-response notes (refresh from boards): [references/classify-examples.md](references/classify-examples.md)

## 3. 14-day evidence pack

Load [references/evidence-pack.md](references/evidence-pack.md) once you have a class from §2 and before choosing wait / watch / act: it lists the dated Search Console, Bing, prompt-grid, analytics and control-window checks to collect over the last 14 days.

## 4. Wait / watch / act

- **Wait:** in-flight core (<7 days after complete); ChatGPT citation mix only; residual ranking wobble after a completed spam update with no new dashboard incident, e.g. after the **September 2026 spam update** (complete 8 Oct 2026; Google says recovery can take many months and periodic refreshes follow). Read the fixed window 24 Sep → 8 Oct 2026 against a sitewide control, after confirming Search Console freshness
- **Watch:** any spam rollout still in flight + no manual action; a product/measurement rollout that is real but not yet on this property. Once a rollout is Complete, residual wobble moves to **Wait**. Keep checking Search Console **Manual actions** and Performance **Last updated** before reading right-edge cliffs. Current dated watch items (refresh from boards): [references/classify-examples.md § Watch list](references/classify-examples.md#watch-list-dated)
- **Act now:** a live manual action in Search Console (fix the named pattern, then reconsideration, not a sitewide rewrite); robots / snippet blocks; Bing `NOARCHIVE` / mistaken `NOINDEX` on money pages; expired-domain / scaled-content / site-reputation patterns (outside the EEA these still demote); indexation collapse; opted out of Search generative AI by mistake; eligible vertical missing regional aggregator/supplier markup/participation when that unit is the actual goal; fabricated author personas or unreviewed AI pages on a generated site (fix the process, with a review step and honest bylines, not a panic rewrite of every URL)

## 5. Stakeholder note

- What changed (link + date)
- What did **not** change
- What we measured
- What we will not do (panic rewrites, "GEO schema", llms.txt-for-Google, "Preferred Sources = ranking", "Preferred Sources email count = ranking", "right-edge cliff during a reporting delay = drop", "parasite SEO is fine in EEA", "gen-AI impressions = AIO success", "multimodal filter = ranking", "SAFE paper = Sep spam target", "conference timing table = deadline")
- Next check date (usually next Monday)

If a skill's facts moved, update the matching playbook (e.g. `technical-seo-2026-delta`, `aeo-answer-surface-playbook`, `geo-citation-playbook`) the same day. If nothing material changed, stay quiet rather than sending filler.

## Done when

A one-page triage note with class, evidence, and wait / watch / act. No tactic list unless class = act now.

**Verify:** the note names one class, links at least one official board (or documents the timeout), and chooses exactly one of wait / watch / act.
