# Workspace and feature lifecycle — v1.1

## Two approved project trees
`project-workspace/work/` and `project-workspace/tests/` are the complete managed **project** write scope. The root `CLAUDE.md`, `.claude/` and `docs/ba-qa/` distribute configuration and templates, not generated working files.

| Directory | Responsibility |
|---|---|
| work/backlog/ | Epic / Feature / Task registers, priority, owner, dependencies, status |
| work/features/FEAT-ID-slug/ | Shared Feature brief, status and traceability |
| work/features/FEAT-ID-slug/ba/ | Discovery, AS-IS/TO-BE, rules, requirements, stories, AC and decisions |
| work/features/FEAT-ID-slug/qa/manual/ | Manual test cases, exploratory charters and observed runs |
| work/features/FEAT-ID-slug/qa/automation/ | Automation selection, plan and TC-ID-to-script mapping ONLY |
| work/features/FEAT-ID-slug/qa/ | QA plan, bug log, assessment, report |
| tests/ | Runnable E2E/API/integration tests, fixtures, helpers and test-local config/output |

These are relative to `project-workspace/`. No other path in `project-workspace/` may be managed. Root rule files are read-only during feature work. External materials may be read with permission, never written. Reject path traversal/symlink escapes. Configure tool permissions for hard enforcement; instructions alone are not a security boundary.

## One canonical work hierarchy
Use `EP-001` Epic, `FEAT-001` Feature, `US-001` story, `TASK-001` work item, `FR-001` / `BR-001` / `NFR-001` requirements, `AC-001`, `TC-001`, `BUG-001`. To disambiguate feature-local IDs use fully-qualified `FEAT-001/TC-001` in cross-feature registers.

Feature states: Backlog -> Discovery -> In Analysis -> BA Review -> Ready for QA -> In Testing -> QA Review -> Ready for Release -> Closed. Allow Blocked and Reopened with reasons. Agent cannot mark approved without human sign-off; a task Done is not Feature Approved.

## BA / QA handoffs
BA -> QA: scoped, sourced, versioned and reviewed business rules, AC, known unknowns and testability. Material unresolved decisions block matching tests.
QA manual -> automation: stable TC/AC with precise observable assertions and fixtures; preserve one TC ID and map script filename rather than duplicating expected behavior.

On any requirement / AC change, enumerate impacted tests, manual runs, automation scripts, regressions and reviewers. Flag for review; do not overwrite prior evidence.

## Execution evidence and output placement
All newly designed manual tests start NOT_RUN. PASS/FAIL requires actual observed build, environment, timestamp and evidence. Runnable automation source stays in `tests/`; transient reports under ignored `tests/.artifacts/` or runner-specific paths **inside tests/**. Summary/links/redacted evidence live in `work/`. Never create `project-workspace/test-results/` or any third tree. Never commit credentials, PII or sensitive real datasets.

Create only files needed for current S/M/L task. Don't generate a whole feature dossier for minor changes.
