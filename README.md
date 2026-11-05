# Claude SEO skills on GitHub: agent-skills-pack-free

Two free, MIT-licensed Claude SEO skills on GitHub for SEO and AI-search work. They are plain `SKILL.md` folders that work in Claude Code, Cursor and Codex, taken from The 2026 SEO & AI-Search Skill Pack.

An Agent Skill is a folder with a `SKILL.md` file (`name`, `description`, instructions) and optional `references/` files. The agent reads the description to decide when the skill applies, then loads the instructions and references only when it needs them.

## What the two skills do

- **skill-review**: audits one agent `SKILL.md` with a 0–2 rubric (a quote or a named gap behind each score) and ends with one verdict: ship, tighten, rewrite, or delete/merge. It also flags sibling skills with overlapping descriptions. Use it on your own skills and on any third-party skill before you rely on it.
- **search-change-triage**: a weekly routine for when traffic, rankings, AI Overviews or AI citations move. It checks official sources first, puts the change into one class, and ends in a single call: wait, watch, or act. Never "rewrite everything" off a wobble.

## Install

With the [`skills` CLI](https://github.com/vercel-labs/skills):

```sh
# list the skills in this repo without installing
npx skills add TommyBez/agent-skills-pack-free --list

# install both
npx skills add TommyBez/agent-skills-pack-free

# install one skill, for one agent
npx skills add TommyBez/agent-skills-pack-free --skill skill-review -a claude-code
npx skills add TommyBez/agent-skills-pack-free --skill search-change-triage -a cursor
npx skills add TommyBez/agent-skills-pack-free --skill search-change-triage -a codex
```

Manual: copy a whole folder from `skills/` (with its `references/`) into your agent's skills folder, for example `cp -R skills/skill-review .claude/skills/`.

| Agent | Project folder | Global folder | How to check |
| --- | --- | --- | --- |
| [Claude Code](https://code.claude.com/docs/en/skills) | `.claude/skills/<name>/SKILL.md` | `~/.claude/skills/<name>/SKILL.md` | Run `/skills` (or ask "What skills are available?") |
| [Cursor](https://cursor.com/docs/context/skills) | `.cursor/skills/` or `.agents/skills/` | `~/.cursor/skills/` or `~/.agents/skills/` (also reads `.claude/skills/`, `.codex/skills/` and their `~/` versions for compatibility; only `~/.cursor/skills/` syncs to Cloud Agents) | Customize → Skills, or type `/` in Agent chat |
| [Codex](https://developers.openai.com/codex/skills) | `.agents/skills/` (scanned from the working directory up to the repo root) | `~/.agents/skills/` (admin: `/etc/codex/skills`) | Run `/skills` or type `$` in Codex CLI or the IDE extension |

Paths checked on each tool's docs on 4 November 2026. `npx skills add -a cursor` installs the project copy in `.agents/skills/`, which Cursor also reads. Step-by-step: [how to install Claude skills in Claude Code, Cursor and Codex](https://agentskillspack.com/guides/install-seo-skills-claude-code-cursor-codex?utm_source=github-free&utm_medium=readme).

## Full pack

These two skills come from a larger set of [Claude SEO skills](https://agentskillspack.com/?utm_source=github-free&utm_medium=readme). `search-change-triage` mentions other playbooks (`technical-seo-2026-delta`, `aeo-answer-surface-playbook`, `geo-citation-playbook`); those are in the full pack, not in this repo.

The full pack: 11 skills, $29 one-time, at [agentskillspack.com](https://agentskillspack.com/?utm_source=github-free&utm_medium=readme)

## License

The two skills in this repo are MIT licensed (see [LICENSE](LICENSE)). The license covers only the files in this repository. The full pack is sold separately under its own terms.
