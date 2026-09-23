# agentready-eval-agentic-docs

AgentReady assessment results measuring the impact of [agentic-docs](https://github.com/openshift-eng/ai-helpers/tree/main/plugins/agentic-docs) on OpenShift component repositories.

## Reports

| Path | Description |
|------|-------------|
| [`reports/DIFF-mto-vs-pr-765.md`](reports/DIFF-mto-vs-pr-765.md) | Score comparison: multiarch-tuning-operator `main` vs PR #765 (agentic-docs) |
| `reports/mto/` | Baseline assessment (`main`) |
| `reports/pr-765/` | Assessment with agentic-docs applied |
| `reports/mtao-with-docs/` | multiarch-tuning-operator with docs |
| `reports/ztwim-with-docs/` | ztwim with docs |
| `reports/ai-helpers-assess/` | ai-helpers marketplace assessment |

Each run directory has `assessment-*.json` (machine-readable) and `report-*.md` / `report-*.html` (human-readable).

## Tooling

Scores produced with [agentready](https://github.com/ambient-code/agentready).
