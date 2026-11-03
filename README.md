# agent-skills-pack-free

Two free Agent Skills for SEO and AI-search work, from The 2026 SEO & AI-Search Skill Pack.

An Agent Skill is a folder with a `SKILL.md` file (name, description, instructions) and optional `references/` files. The agent reads the description to decide when the skill applies, then loads the instructions and references only when it needs them.

## Skills

- **skill-review**: Use when auditing, tightening, or deciding whether to keep one agent SKILL.md. Not for writing product code or inventing skill content you have not read.
- **search-change-triage**: Use every Monday, or when traffic / rankings / AI Overviews / AI citations moved, to classify the external search change and then choose wait, watch, or act. Never "rewrite everything" off a wobble. Not a property performance report.

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
```

Manual: copy a folder from `skills/` into your agent's skills directory.

| Agent | Project | Global |
|-------|---------|--------|
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |
| Cursor | `.agents/skills/` | `~/.cursor/skills/` |
| Codex | `.agents/skills/` | `~/.codex/skills/` |

For example: `cp -R skills/skill-review .claude/skills/`.

## Full pack

`search-change-triage` mentions other playbooks (`technical-seo-2026-delta`, `aeo-answer-surface-playbook`, `geo-citation-playbook`). Those are in the full pack, not in this repo.

The full pack (11 skills, $29 one-time): https://agent-skills-pack-indol.vercel.app

## License

The two skills in this repo are MIT licensed (see [LICENSE](LICENSE)). The full pack is sold separately under its own terms.
