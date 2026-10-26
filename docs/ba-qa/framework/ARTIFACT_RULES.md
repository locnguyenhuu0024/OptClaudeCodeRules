# BA/QA artifacts, provenance and cost control

## Output locations in a target project

Write finalized work to docs/ba-qa/artifacts/<feature>/ only with user permission. Do not overwrite existing approved requirements; version replacements or show diffs. Use concise Markdown rather than long narrative chat.

Recommended conditional files:
- REQUIREMENTS.md: business objective, actors, scope, numbered rules/AC, ambiguity log.
- TEST_CASES.md: prioritized executable cases; create only for test-design tasks.
- RTM.md: requirement -> AC -> test -> observed evidence/status; create for M/L.
- DEFECTS.md: observed bugs and repro, not conjecture.
- TEST_REPORT.md: actual verification findings when tests truly ran.
- AUDIT.md: independent review findings, gate status, sources.

## Efficiency

S tasks need a small answer or single artifact, not every template. M uses relevant requirement/test templates. L uses traceability, review and gates. Source documents may be referenced by path and section; agents read targeted ranges. A critical absent source is flagged rather than reconstructed from generic assumptions.

## Traceability metadata

Every material claim is backed by input file+section, ticket URL/ID, requirement ID, or direct observed evidence. Label external data and its as-of date. If citation unavailable, say source not supplied. Respect confidentiality: redact secrets, customer personal data and sensitive logs.

## Handoff contract

Handoff includes: decision/version, scope, completed artifact paths, AC/TC coverage, high-risk gaps, open questions with owner, review status, and explicitly whether tests were run.
