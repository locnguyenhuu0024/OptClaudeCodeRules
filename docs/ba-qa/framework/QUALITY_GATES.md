# Quality gates for BA / QA

Gate states: PASS / FAIL / BLOCKED / NOT_APPLICABLE. A gate cannot PASS on missing evidence. The AI does not sign off for a product owner or release manager.

## BA Ready (for implementation)

- In/out of scope and stakeholders identified.
- Requirement IDs and trusted source references exist.
- Each critical business rule has observable acceptance criteria.
- Dependencies, roles, exceptions and relevant NFRs considered.
- No unresolved high-impact conflict that determines expected behavior.
- Decisions needing human approval are clearly assigned.

## Test Design Ready

- AC-to-TC mapping (RTM) present; unmapped AC called out.
- Positive/negative/boundary/permission/state coverage risk-based and justified.
- Test data, fixtures, environment and dependencies specified.
- Expected results are objective, not guessed.
- High-risk gaps and blocked assumptions documented.

## Execution Evidence Ready

- Each PASS has reproducible environment/build and contemporaneous evidence.
- FAIL contains actual vs expected and defect linkage as appropriate.
- NOT_RUN/BLOCKED/INCONCLUSIVE distinguished; no fabricated runs.
- Relevant regression tests identified and results summarized.
- Residual risk and unknowns explicit.

## Release assessment (advisory only)

Do not recommend unqualified Go when a P0/critical path is untested, there is an unresolved release-blocking defect, or required approvals are absent. State evidence limitations and the actual accountable decision owner.

## Finding classification

BLOCKER: prevents agreeing testable behavior or valid assessment.
MAJOR: material coverage/behavior/safety discrepancy.
MINOR: non-blocking ambiguity or usability/documentation gap.
INFO: optional improvement. Each finding needs source or reproducible evidence and a concrete remediation.

## v1.1 Cross-role acceptance
- One canonical feature record, common BA/QA traceability.
- Changed AC flags related TC/manual results/automation scripts for review.
- Test design != executed testing; observed proof required for PASS.
- Generated work and code confined to project-workspace/work/ and project-workspace/tests/.
