# Model / effort routing — BA and Tester

Recommended **main-session coordinator: Claude Sonnet 5.5 / Medium**. A CLAUDE.md rule cannot override the actual model selected by the user. Individual specialist agent frontmatter configures their presets, subject to account/tool overrides.

## Route by decision entropy
| Activity | Agent | Suggested model / effort |
|---|---|---|
| Factual extraction / source inventory | ba-intake-extractor | Haiku 5.5 / Medium |
| BA backlog triage, owner/status updates | ba-backlog-manager | Sonnet 5.5 / Medium |
| BA requirement and AC analysis | ba-analyst | Sonnet 5.5 / Medium |
| Complex business rule/conflict review | ba-domain-auditor | Opus 5.5 / Medium |
| Risk-based QA test design | qa-test-designer | Sonnet 5.5 / Medium |
| Manual QA cases and observed records | qa-manual-tester | Sonnet 5.5 / Medium |
| Authorized test automation | qa-automation-engineer | Sonnet 5.5 / High |
| Independent coverage audit | qa-coverage-auditor | Opus 5.5 / Medium |
| Scoped, authorized execution assessment | qa-execution-assessor | Sonnet 5.5 / High |

Skip preliminary cheap routing for intrinsically high-risk decisions. After a targeted unsuccessful attempt, escalate based on specific reasoning failures. Do not use Fable or Opus High by default; require a justified manual choice for exceptional workloads.

## Cost and context
Optimize for cost per accepted artifact (generation, validation, revisions), not per token alone. Effort influences consumption, not a fixed tariff multiplier. For long sources, read targeted spans; Haiku 5.5 may cost more for inputs beyond its prompt price threshold. Only load one relevant framework and one necessary template.

## Flat workspace hard boundary
No agent may invent subdirectories under project-workspace/work/ or project-workspace/tests/, or require the user to rename/reorganize previously created data. Route by **task type and content**, not file paths, filename conventions, or feature-directory structures. The coordinator locates existing files first and only creates directly contained files when needed and permitted.

## Delegation
Pass objective, existing source file references, constraints and expected evidence in concise form. An independent auditor gets source and artifact, not original author's self-justification. Report actual model only when verifiable; no promises of quota enforcement from prose.
