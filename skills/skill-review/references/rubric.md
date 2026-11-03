# Rubric: score each line 0–2

Further reading on the principles behind this rubric (re-read when in doubt; do not paste essays into skills):
- https://open.substack.com/pub/productforengineers/p/what-nobody-tells-you-about-writing
- https://x.com/pvncher/status/2095991462416490862 (short when-to-use, no "pick me", progressive disclosure, fewer recipes, calibrated boundaries, explicit done-when)

| # | Line | 2 looks like | 0 looks like |
|---|------|--------------|--------------|
| 1 | Progressive disclosure | Name + description work as a *when-to-load* router. The description is short (about two sentences or less), says when **not** to use it, and avoids "pick me" / grab-all wording. The body is thin and points at `references/` / `scripts/` instead of dumping schemas inline. | Fat always-on description; overlapping "use for anything related to X"; everything loaded in one file. |
| 2 | Precise vs ambiguous | Goal / **Done when**, hard constraints, and context the agent cannot derive (paths, tools, schemas) are explicit. Steps, failures, and runtime specifics stay flexible. No scaffolding that only props up a weak model and overconstrains a strong one. | Over-specified workflows ("read lines 40–120", fixed file lists, brittle branch trees); missing Done when, so the agent stops at a first draft. |
| 3 | Anti-rot | Durable structure is hand-written; volatile facts point to a live source of truth or are regenerated. | Copy-pasted docs; patch piles with no stable base. |
| 4 | Ask > demand + boundaries | Goals, verification, and agent ergonomics. Assumes the agent can discover tools and errors and run safe local checks without being told how. "Ask first" / stop language only for real side effects (send, pay, delete, secrets, irreversible); otherwise permission to continue through the Done when. | Micromanaged commands; blanket "always ask" that stops legitimate work; no autonomy for disposable or local verification. |
| 5 | Worth existing + catalog | Repeated work, a task agents fail at by default, private context, or an autopilot loop, **and** no near-duplicate sibling that should absorb it. Prefer a clearer description or a merge over another skill that fights for the same load slot. | One-shot task; the model already does it well; overlaps another skill's when-to-load; catalog bloat that forces description truncation. |

**Verdict bands:** `ship` 8–10 · `tighten` 5–7 · `rewrite` ≤4 · `delete/merge` if line 5 is 0 (or there is clear sibling overlap).

## Soft checks (note them in the score table; do not invent a 6th scored line)

- **Description budget:** quote the description; flag it if it buries billing or rules in the router sentence or lacks a when-not.
- **Sibling scan:** name 0–2 nearby skills that could collide; propose a merge or rename if the collision is real.
- **Done when:** if missing, add one line as a minor fix (allowed without asking).
- **Boundary audit:** list any always-ask / always-stop phrases that are not tied to a real side effect; propose softening as a minor fix when the intent is clear.
