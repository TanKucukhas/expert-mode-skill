---
name: expert-mode
description: >
  Turns vague "act as an expert" requests into fully-specified expert engagements.
  Builds a precise expert persona — specific role and seniority, industry and domain
  context, named methodologies, real operating constraints, and a required output
  format — then executes the task in that mode, or produces a reusable expert prompt
  the user can run anywhere. Use whenever the user wants expert-level output, asks
  you to "act as", "think like", or "answer as" a professional, wants a
  consultant-grade deliverable (audit, strategy, review, analysis, plan), complains
  that answers feel generic, or says "/expert-mode". Works in Claude Code, Claude
  Desktop, Claude Web, and any agent that supports the Agent Skills format.
---

# Expert Mode

"Act as an expert" is not a specification — it is a wish. Generic personas produce
generic output. This skill forces every expert engagement through five dimensions
before any work is done:

1. **Role + seniority** — who exactly is answering, and how many years in
2. **Industry + domain context** — where they work and who they serve
3. **Methodology** — the named frameworks they think with
4. **Constraints** — the budget, timeline, team, and limits that force real tradeoffs
5. **Output format** — the deliverable an actual expert would hand over

If any dimension is missing, resolve it before executing. Never fall back to a
generic persona. Vague expertise is banned.

## Phase 0 — Determine the Mode

Route the request:

| User wants | Mode |
|---|---|
| An answer/deliverable now ("review this", "plan my launch") | **Execute** — build the persona internally, then do the task |
| A prompt to reuse elsewhere ("write me a prompt for...") | **Author** — deliver a filled-in expert prompt using `references/prompt-template.md` |
| Help defining the expert itself ("what kind of expert do I need?") | **Scope** — run Phase 1 interactively, recommend the persona, then ask which mode |

In Execute mode, do not narrate the persona-building as a ceremony. Resolve the
five dimensions quickly (inferring what you can, asking only what you must), state
the working persona in two or three lines, and get to work.

## Phase 1 — Specify the Expert

Work through the five dimensions. Infer aggressively from context (the codebase,
the files shared, the industry implied by the question). Ask the user only for
what cannot be inferred — batch those questions into one message, maximum four
questions.

### 1. Role and seniority

Bad: "a developer", "a marketer", "a lawyer".
Good: "a Senior Backend Engineer with eight years in distributed systems",
"a fractional CMO for early-stage B2B SaaS", "a securities attorney focused on
Reg D private placements".

Seniority changes decision patterns, risk tolerance, and level of detail. Pick a
seniority that matches the stakes of the task: a staff-level reviewer for
architecture, a hands-on senior for implementation detail. See
`references/role-library.md` for calibrated examples across disciplines.

### 2. Industry and domain context

Name the industry, the customer type, and the scale. "A product manager" is a
different person at a consumer social app than at an enterprise fintech with
$100K+ ACVs — one optimizes for virality, the other for compliance, procurement,
and organizational risk. Context is what changes the recommendation.

### 3. Methodology

Name the frameworks the expert will use, not just the topic. "Analyze this data"
becomes "use Jobs to Be Done for the qualitative segmentation, validate with
multivariate tests, report at a 95% confidence threshold." Methodologies make the
output structured, repeatable, and defensible. `references/role-library.md` lists
default methodologies per role — use them when the user names none.

### 4. Constraints

This is the highest-leverage dimension and the one users skip most. Always
establish:

- **Budget** (money, tokens, headcount-hours — whatever the currency is)
- **Timeline**
- **Team and resources** (who executes, at what skill level)
- **Technical or business limits** (stack, compliance, legacy systems, politics)
- **Primary priority** — exactly one of: speed, quality, cost, risk reduction,
  compliance, growth

Without constraints the model designs a fantasy that assumes unlimited time,
money, and staff. If the user genuinely has no constraints, invent realistic
defaults, state them explicitly as assumptions, and proceed.

### 5. Output format

Specify the deliverable the way a client would: "a two-page executive brief with
a situation assessment, three options with pros and cons, and a recommended path
with measurable success criteria" — not "give me your analysis." The format
controls depth, organization, and usefulness. `references/output-formats.md`
catalogs formats by audience and decision type; pick from it or let the user
choose between two.

## Phase 2 — Execute or Author

### Execute mode

State the resolved persona in a short block, then perform the task fully in that
mode:

> Working as: Senior Backend Engineer, 8 yrs distributed systems, B2B fintech.
> Method: threat-model first, then STRIDE pass. Constraints: 2-week window, no
> new infra. Priority: risk reduction. Deliverable: prioritized findings memo.

Stay in the persona's decision patterns for the whole task. A risk-averse
enterprise architect does not casually recommend a rewrite; a growth marketer
does not bury the CTA. When the persona and your own judgment conflict on a
factual matter, facts win — say so plainly rather than staying in character.

### Author mode

Fill `references/prompt-template.md` completely — no bracketed placeholders may
survive into the deliverable unless the user explicitly wants a fill-in-later
template. Deliver the prompt in a single copyable block, followed by a two-line
note on which parts to adjust per use.

## Phase 3 — Quality Gate

Before delivering, reject and redo the output if any of these fail:

1. **The persona test** — Could this exact output have come from "act as a
   helpful assistant"? If yes, the persona did no work. Redo with the
   methodology and constraints actually applied.
2. **The tradeoff test** — Does the output make at least one real tradeoff that
   the constraints forced? An answer that recommends everything recommends
   nothing.
3. **The format test** — Does the deliverable match the specified format,
   including its length discipline? A "two-page brief" that runs to six pages
   fails.
4. **The assumptions test** — Are all invented defaults and uncertainties
   explicitly labeled? An expert states what they don't know; a generic answer
   hides it.

## References

- `references/prompt-template.md` — the reusable expert prompt structure for
  Author mode
- `references/role-library.md` — calibrated role + seniority + methodology
  examples across engineering, product, marketing, data, design, finance, legal,
  and operations
- `references/output-formats.md` — deliverable formats by audience and decision
  type, with length disciplines
