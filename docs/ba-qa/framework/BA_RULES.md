# Business Analysis (BA) rules

## Source-of-truth hierarchy

1. Approved business decisions and signed-off requirements.
2. Current product behavior confirmed by reliable product artifacts or observed test evidence.
3. Stakeholder drafts, tickets, diagrams and meeting notes, with provenance.
4. Clearly labeled assumptions and proposals.

Record document/version, location and status. Conflicting sources are not resolved by recency alone: raise a clarification with an owner.

## Workflow

1. Intake: objective, actor/stakeholders, trigger, value, current vs target behavior, scope, out-of-scope, dependencies, impacted systems.
2. Model flows: happy path, alternatives, exception paths, state transitions, role/permission matrix, upstream/downstream contracts.
3. Extract rules: calculations, rounding, date/timezone, uniqueness, eligibility, validation, authorization, persistence, notifications, data retention.
4. For each requirement, assign stable ID (BR-001, FR-001, NFR-001) and provenance.
5. Draft user stories using actor/goal/benefit only if story format is useful; no forced stories for purely operational fixes.
6. Write independently testable acceptance criteria (AC-001...), preferably Given/When/Then; quantify thresholds and observable outputs.
7. Analyze negative paths, boundaries, duplicate requests, retries, permissions, concurrency, i18n/accessibility, downstream failures and migrations where relevant.
8. Record unresolved assumptions/questions with severity, decision owner and impact. Block sign-off on unresolved decisions that change expected behavior.
9. Perform BA Ready gate from QUALITY_GATES.md and hand over requirement-to-AC traceability.

## Rules for good AC

An AC must specify preconditions, input/action and observable result. Avoid adjectives (fast, intuitive, appropriate) without thresholds. Avoid implementation internals unless genuinely contractual. Separate multi-outcome conditions into distinct criteria. Include idempotency / rollback expectations for state-changing flows when relevant.

## Scope tiers

S: one requirement and key acceptance criteria, tiny clarification log.
M: compact requirements, user flows, AC, open questions and test handoff.
L: multi-system contract/data flows, roles, decision tables, NFRs, change impact, traceability and formal approval blockers.

## Never do

- Present assumptions as signed-off policy; invent edge-case values or numerical thresholds.
- Change product scope unilaterally or treat a suggested design as agreed.
- Create a 20-section document for a trivial change.
- Modify source, schemas or production data as part of BA analysis.
