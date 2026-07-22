# Expert Mode Skill

An [Agent Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills) that turns vague "act as an expert" requests into fully-specified expert engagements — and gets expert-level output instead of generic filler.

"Act as a developer" produces generic results. "Act as a Senior Backend Engineer with eight years in distributed systems, working in B2B fintech, using STRIDE for the security pass, with a two-week window and no new infra, delivering a two-page findings memo" produces something you can actually use. This skill enforces that discipline automatically.

## What it does

Every expert engagement is forced through five dimensions before any work happens:

1. **Role + seniority** — who exactly is answering, and how many years in
2. **Industry + domain context** — where they work and who they serve
3. **Methodology** — the named frameworks they think with
4. **Constraints** — budget, timeline, team, and limits that force real tradeoffs
5. **Output format** — the deliverable a real expert would hand over

Three modes:

- **Execute** — build the persona, then do your task in that mode
- **Author** — produce a reusable, fully filled-in expert prompt you can paste anywhere
- **Scope** — help you figure out what kind of expert you even need

A four-part quality gate rejects output that a generic assistant could have produced, that makes no tradeoffs, that breaks the format's length discipline, or that hides its assumptions.

## Structure

```
skills/expert-mode/
├── SKILL.md                      # workflow, modes, quality gate
└── references/
    ├── prompt-template.md        # the reusable expert prompt structure + worked example
    ├── role-library.md           # calibrated roles, seniority, and default methodologies
    └── output-formats.md         # deliverable formats by audience, with length disciplines
```

## Install

**Claude Code:**

```bash
cp -r skills/expert-mode ~/.claude/skills/
```

Then invoke with `/expert-mode`, or just ask for expert-level work — the skill triggers on phrases like "act as", "think like", or requests for consultant-grade deliverables.

**Claude Desktop / Web:** add the `skills/expert-mode` folder as a skill in Settings.

## Customize

Everything is plain Markdown. Fork it, add your own roles to the role library, your own deliverable formats, your own house methodologies.

## License

MIT
