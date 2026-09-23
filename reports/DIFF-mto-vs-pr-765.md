# AgentReady report diff: main (`mto`) vs PR #765 (`pr-765`)

| | **main** (`reports/mto`) | **PR #765** (`reports/pr-765`) |
|--|--|--|
| Overall score | **56.4** | **56.9** |
| Certification | Bronze | Bronze |
| Branch | `main` | `pr-765` |
| Commit | `13d76eadfea0` | `95e8c5c79a28` |
| Assessed | 28/34 | 28/34 |
| Timestamp | 2026-09-23T19:15:01.687403 | 2026-09-23T19:08:36.407992 |

**Overall delta:** `+0.5` (Bronze → Bronze)

## Changed attributes

| Attribute | Weight | main | PR #765 | Δ score |
|-----------|-------:|------|---------|--------:|
| `pattern_references` ★ | 0.03 | pass 40.0 | fail 0.0 | -40.0 |
| `agent_instructions` ★ | 0.07 | pass 70.0 | pass 100.0 | +30.0 |
| `design_intent` ★ | 0.03 | fail 30.0 | fail 0.0 | -30.0 |
| `progressive_disclosure` ★ | 0.01 | fail 30.0 | pass 40.0 | +10.0 |

★ = doc-adjacent attribute

## Doc-adjacent detail

### `agent_instructions` (CHANGED)

- **main:** pass score=70.0 measured=`present`
- **PR:** pass score=100.0 measured=`present`
- **Δ:** +30.0
- **main evidence:**
  - CLAUDE.md found at /Users/kpais/kpais-workspace/agentready-eval-agentic-docs/repo/mto/CLAUDE.md
  - Context file is 383 lines (exceeds 300 line limit, consider splitting into .claude/skills/)
  - Agent access documentation found (platform and tool/auth references)
- **PR evidence:**
  - CLAUDE.md found at /Users/kpais/kpais-workspace/agentready-eval-agentic-docs/repo/mto/CLAUDE.md
  - Symlink to AGENTS.md (3291 bytes)
  - AGENTS.md also present (cross-tool compatibility)
  - Context file is 49 lines (good: <=150)

### `progressive_disclosure` (CHANGED)

- **main:** fail score=30.0 measured=`not configured`
- **PR:** pass score=40.0 measured=`2 disclosure mechanism(s)`
- **Δ:** +10.0
- **main evidence:**
  - 5 subdirectory context file(s)
  - Root CLAUDE.md is 383 lines (consider splitting into skills)
- **PR evidence:**
  - 5 subdirectory context file(s)
  - Root CLAUDE.md is 49 lines (good: <150)

### `design_intent` (CHANGED)

- **main:** fail score=30.0 measured=`minimal`
- **PR:** fail score=0.0 measured=`not documented`
- **Δ:** -30.0
- **main evidence:**
  - Design intent language found in CLAUDE.md
- **PR evidence:**
  - No design intent documentation found

### `architecture_decisions` (unchanged)

- **main:** fail score=0.0 measured=`no ADR directory`
- **PR:** fail score=0.0 measured=`no ADR directory`
- **Δ:** +0.0

### `pattern_references` (CHANGED)

- **main:** pass score=40.0 measured=`2 reference source(s)`
- **PR:** fail score=0.0 measured=`none found`
- **Δ:** -40.0
- **main evidence:**
  - Pattern references found in CLAUDE.md (1 reference(s))
  - CLAUDE.md is 383 lines with no skills; consider extracting patterns into .claude/skills/
- **PR evidence:**
  - No pattern references or skills found

### `readme_structure` (unchanged)

- **main:** pass score=100.0 measured=`3/3 sections`
- **PR:** pass score=100.0 measured=`3/3 sections`
- **Δ:** +0.0

### `adr_frontmatter_completeness` (unchanged)

- **main:** skipped score=None measured=`None`
- **PR:** skipped score=None measured=`None`

### `inline_documentation` (unchanged)

- **main:** fail score=52.70376175548589 measured=`42.2%`
- **PR:** fail score=52.70376175548589 measured=`42.2%`
- **Δ:** +0.0

### `file_size_limits` (unchanged)

- **main:** fail score=26.873640976081177 measured=`357 huge, 483 large out of 8278`
- **PR:** fail score=26.873640976081177 measured=`357 huge, 483 large out of 8278`
- **Δ:** +0.0

## Weighted impact of score changes

Approximate contribution to overall (Δscore × default_weight); AgentReady also renorms over assessed attrs.

| Attribute | Δ score | Weight | ≈ weighted Δ |
|-----------|--------:|-------:|-------------:|
| `agent_instructions` | +30.0 | 0.07 | +2.10 |
| `pattern_references` | -40.0 | 0.03 | -1.20 |
| `design_intent` | -30.0 | 0.03 | -0.90 |
| `progressive_disclosure` | +10.0 | 0.01 | +0.10 |

Sum of weighted Δ (rough): **+0.10**

## Unchanged attributes

`architecture_decisions`, `readme_structure`, `adr_frontmatter_completeness`, `inline_documentation`, `file_size_limits`, `architectural_boundaries`, `ci_quality_gates`, `container_setup`, `conventional_commits`, `cyclomatic_complexity`, `dbt_data_tests`, `dbt_model_documentation`, `dbt_project_config`, `dbt_project_structure`, `dependency_security`, `deterministic_enforcement`, `gitignore_completeness`, `issue_pr_templates`, `lint_config_coverage`, `lint_suppression_density`, `lock_files`, `one_command_setup`, `openapi_specs`, `separation_of_concerns`, `single_file_verification`, `standard_layout`, `structured_logging`, `test_execution`, `threat_model`, `type_annotations`

## Verdict

PR #765 improves overall AgentReady score by **+0.5** (56.4 → 56.9), still **Bronze**. Net effect is mixed:

- **Wins:** `agent_instructions` 70 → 100 (383-line `CLAUDE.md` → 49-line `AGENTS.md` + symlink); `progressive_disclosure` fail 30 → pass 40 (root context under 150 lines).
- **Regressions:** `pattern_references` pass 40 → fail 0; `design_intent` fail 30 → fail 0 — AgentReady previously found keywords/patterns in the long `CLAUDE.md` that the lean `AGENTS.md` no longer contains.
- **Unchanged fails:** `architecture_decisions` still 0 (`ai-docs/` is not detected as an ADR directory).

The overall +0.5 is mostly `agent_instructions` (+2.1 weighted) offset by losses on `pattern_references` and `design_intent`.
