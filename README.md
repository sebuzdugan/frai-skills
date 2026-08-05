# FRAI Skills

Agent skills for **responsible AI engineering** - part of the [FRAI](https://github.com/sebuzdugan/frai) ecosystem ([frai.cc](https://www.frai.cc/)).

Install into any AI coding agent (Claude Code, Cursor, and anything that reads the standard `skills/` layout):

```bash
npx skills add sebuzdugan/frai-skills
```

## Skills

| Skill | What it does |
|---|---|
| [`responsible-ai-spec`](skills/responsible-ai-spec/SKILL.md) | The **FRAI Gate**: every spec your agent writes for an AI-touching feature must answer 7 responsible-AI checks - risk tier (EU AI Act-aligned), data & privacy, human oversight, evaluation thresholds, bias & fairness, monitoring & rollback, transparency & incidents - before implementation starts. High-risk features require a named human sign-off; the agent is forbidden from self-approving them. |

## How it fits together

- **This repo** teaches your *agent* the workflow (spec template, risk-tier reference, gate checklist).
- **[`frai-gate`](https://github.com/sebuzdugan/frai/tree/main/packages/frai-gate)** enforces it mechanically: `npx frai-gate init --ci` scaffolds the spec + a GitHub Action, `npx frai-gate check FFRAI-SPEC.md` blocks CI until the gate is answered, `npx frai-gate draft` drafts the gate from your actual code.
- **[`frai`](https://www.npmjs.com/package/frai)** turns a passing spec into shippable governance docs (model card, risk file), scans code for AI usage, and runs evals.

MIT · by [Sebastian Buzdugan](https://github.com/sebuzdugan)
