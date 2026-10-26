# BA and QA quality gates

Outcomes: PASS / FAIL / BLOCKED / NOT_APPLICABLE, supported by actual source/evidence rather than confidence language.

## BA Ready
Business objective and scope defined; relevant sources/version retained; rules testable with observable AC; roles, exception paths and dependencies considered; material conflicting requirements escalated to a human decision owner. Task Done does not imply approved requirements.

## Test Design Ready
AC/requirement -> test cases traceable in whatever original files the user maintains. Risk-based positive/negative/boundary/permissions/state/regression coverage justified. Unknown expected behavior marked blocked, not assumed. Manual and automation candidates clearly identified where relevant.

## Execution Evidence Ready
Each PASS tied to contemporaneous observation/environment/build; FAIL contains actual vs expected; unrun, blocked and inconclusive tests distinguished; open defects and residual risks explicit. Script existence is not execution evidence.

## Cross-role change impact
When requirements or AC change, identify affected test IDs, manual execution records and automation files; mark for review, do not silently rewrite history. Preserve existing filenames and locations. Work files are direct children of project-workspace/work/; runnable automation files direct children of project-workspace/tests/. No enforced feature folders or mandatory restructuring.

## Severity
BLOCKER: missing agreed behavior or valid evaluation; MAJOR: meaningful risk/coverage failure; MINOR: nonblocking ambiguity; INFO: optional improvement. Include source or reproducible proof and a concrete next action.
