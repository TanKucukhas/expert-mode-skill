# Output Formats

Experts communicate through formats designed for a specific audience and
decision. Pick the format from the decision being made, then enforce its length
discipline — overrunning the length is a quality-gate failure.

## Decision-making formats

| Format | Audience / decision | Required sections | Length discipline |
|---|---|---|---|
| Executive brief | Leadership choosing a direction | Situation assessment; 3 options with pros/cons; recommendation with measurable success criteria | 2 pages max |
| Decision memo (one-way door) | Irreversible/high-cost choice | Context; the decision; alternatives considered and why rejected; risks and mitigations | 1-2 pages |
| RFC / design doc | Engineers reviewing an approach | Problem, goals/non-goals; proposed design; alternatives; rollout plan; open questions | As long as needed, but goals/non-goals fit on one screen |
| Business case | Budget approval | Problem cost; proposed investment; expected return with assumptions; sensitivity (what breaks the case) | 2-3 pages |

## Assessment formats

| Format | Audience / decision | Required sections | Length discipline |
|---|---|---|---|
| Findings memo (audit/review) | Owner deciding what to fix | Prioritized findings (severity-ordered); evidence per finding; remediation with effort estimate | Findings first, background last |
| Scorecard | Comparing options/vendors/candidates | Explicit criteria with weights; per-option scores; the one deciding criterion | 1 page + appendix |
| Postmortem | Team preventing recurrence | Timeline; root cause(s); what worked; action items with owners and dates | Blameless; actions ≤ 5 |

## Planning formats

| Format | Audience / decision | Required sections | Length discipline |
|---|---|---|---|
| Project plan | Team executing | Milestones with dates; owners; dependencies; explicit cut-list if timeline slips | Milestones ≤ 7 |
| Strategy one-pager | Aligning a team on direction | Where we play; how we win; what we will not do; 3 measurable goals | 1 page, hard limit |
| Runbook / SOP | Operator under pressure | Preconditions; numbered steps with expected results; rollback; escalation path | Steps testable by a newcomer |

## Communication formats

| Format | Audience / decision | Required sections | Length discipline |
|---|---|---|---|
| Client email | External stakeholder | Bottom line first; supporting detail; one clear ask | ≤ 200 words |
| Board update | Directors monitoring | Highlights; lowlights (mandatory, non-empty); asks; KPI table | 1 page |
| Talk/pitch outline | Persuading a room | Hook; problem; proof; ask; anticipated objections with responses | 1 slide of content per 2 minutes |

## Universal rules

- Every format ends with **assumptions and open questions** — an expert states
  what they don't know.
- Options come in threes at most; ten options is a research dump, not advice.
- Numbers carry units, baselines, and timeframes ("reduce p99 from 800ms to
  300ms by Q3", not "improve latency").
- If the user names no format, propose two candidates from this catalog and let
  them pick — do not default to an unstructured essay.
