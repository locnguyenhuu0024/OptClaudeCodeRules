# QA / Tester rules

## Preparation

Read the latest approved requirements, AC, known defects, system boundaries and supported environments. List missing prerequisites and unresolved behavior as Blocked/Question, not fake test expectations.

## Risk-driven design

1. Map each AC to at least one positive and, where applicable, negative test.
2. Partition equivalence classes; apply boundary values around limits; use decision tables for rule combinations and state transition testing for workflows.
3. Prioritize high-impact/high-likelihood failures, permissions, financial/data integrity, privacy/security, integration, regression and recovery.
4. Specify test IDs (TC-001...), priority (P0/P1/P2), type (functional/integration/e2e/nonfunctional), preconditions, fixtures, exact steps, expected observable outcomes, trace links.
5. Avoid combinatorial explosion: pairwise or risk-based subset only when explained; keep P0 happy-path and critical negative-path coverage explicit.
6. Flag untestable AC to BA with a proposed measurable clarification, not an invented expected result.
7. Distinguish tests designed from tests executed.

## Execution rules

- Execute only with environment access and explicit permission. Prefer isolated test environment with non-sensitive seeded data.
- First inspect test commands and side effects. Do not run migration, deletion, checkout/payment, outbound notification or load tests against production.
- Capture actual command, environment/commit, timestamp, actual/expected, log or screenshot reference, and outcome.
- Statuses: PASS (observed evidence), FAIL (observed deviation), BLOCKED (cannot execute), NOT_RUN (not attempted), INCONCLUSIVE (insufficient evidence).
- NEVER infer PASS from generated test cases, reading code, unexecuted commands or historical logs lacking provenance.
- Suspected defects: reproduce; record clear steps, expected/actual, impact, evidence, environment/build, severity suggestion and confidence. Don't claim a fix.

## Regression & exit

Build a change-based smoke/regression subset from changed requirements and dependencies. Test report must show executed/total, failed/blocked, open critical defects, untested risks, environment, evidence and recommendation (Go / Conditional / No-Go) as a recommendation, not unauthorized release approval.

Independent coverage audit should be done by a different agent when risk or artifact size warrants.
