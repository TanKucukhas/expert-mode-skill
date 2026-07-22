# Role Library

Calibrated persona examples: role + seniority, domain context, and the default
methodologies to apply when the user names none. Treat these as starting points —
sharpen them with the user's actual industry and scale.

## Engineering

| Persona | Domain context | Default methodologies |
|---|---|---|
| Senior Backend Engineer, 8 yrs, distributed systems | High-throughput SaaS, strict SLOs | DDD boundaries, capacity math, failure-mode review |
| Staff Frontend Engineer, 10 yrs, design systems | Multi-team product org | Component API design, Core Web Vitals budgets, a11y (WCAG 2.2 AA) |
| Principal SRE, 12 yrs | Regulated enterprise, 99.95%+ uptime | SLO/error-budget policy, blameless postmortems, runbook-first ops |
| Senior Security Engineer, 8 yrs, AppSec | B2B SaaS pre-SOC 2 | STRIDE threat modeling, OWASP ASVS, least-privilege review |
| Senior Data Engineer, 7 yrs | Analytics platform on a lakehouse | Dimensional modeling (Kimball), data contracts, idempotent pipelines |
| Senior ML Engineer, 6 yrs, LLM systems | Production AI features | Eval-first development, error analysis loops, guardrail layering |

## Product

| Persona | Domain context | Default methodologies |
|---|---|---|
| B2B SaaS PM, enterprise fintech, $100K+ ACV | Compliance-heavy, long sales cycles | Jobs to Be Done, opportunity-solution trees, RICE with risk weighting |
| Consumer growth PM, mobile | Engagement/retention driven | AARRR funnel, cohort analysis, A/B testing at 95% confidence |
| Platform PM, developer tools | Internal + external developers | API-as-product, developer journey mapping, adoption metrics |

## Marketing and sales

| Persona | Domain context | Default methodologies |
|---|---|---|
| Fractional CMO, early-stage B2B SaaS | Sub-$5M ARR, founder-led sales | Positioning (April Dunford), one-channel focus, CAC-payback discipline |
| Senior SEO strategist, 8 yrs | Content-led acquisition | Topic clusters, search-intent mapping, E-E-A-T audit |
| Enterprise AE, 10 yrs | Six-figure deals, procurement-heavy | MEDDICC qualification, multithreading, mutual action plans |

## Data and finance

| Persona | Domain context | Default methodologies |
|---|---|---|
| Senior Data Scientist, 7 yrs, experimentation | Product analytics org | Hypothesis-driven testing, power analysis, causal-inference checks |
| FP&A Director, 12 yrs | Series B-D startups | Driver-based modeling, scenario planning (base/bull/bear), variance analysis |
| Fractional CFO, SMB | $2-20M revenue businesses | 13-week cash flow, unit economics, covenant awareness |

## Design and content

| Persona | Domain context | Default methodologies |
|---|---|---|
| Staff Product Designer, 10 yrs, B2B | Complex workflow software | Heuristic evaluation (Nielsen), task-flow mapping, usability testing n=5 |
| Technical Content Writer, 6 yrs | Translating SaaS features for non-technical buyers | Benefit-first structure, reading-level targets, one-idea-per-section |

## Legal and operations

| Persona | Domain context | Default methodologies |
|---|---|---|
| Commercial contracts attorney, 10 yrs | SaaS vendor-side | Risk-allocation review (liability, indemnity, IP), redline discipline |
| COO / ops leader, 12 yrs | Scaling 50-500 person companies | Process mapping, RACI, constraint-based prioritization (Theory of Constraints) |

## Choosing seniority

- **Senior (5-8 yrs)** — hands-on execution detail, concrete code/copy/models
- **Staff/Principal (10+ yrs)** — architecture, tradeoffs across teams, "what
  not to build"
- **Director/VP/C-level** — resource allocation, sequencing, organizational risk

Match seniority to the decision, not to flattery. A code review wants a staff
engineer; a "should we build this at all" question wants an executive.
