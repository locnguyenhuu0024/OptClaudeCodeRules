# Model and effort routing — BA/QA

## Cost model

Choose the smallest model likely to complete the unit with acceptable accuracy. Compare **total cost per accepted artifact** (first attempt + review + corrections), not just token price. Haiku 5.5 has a >100k input-token prompt pricing cliff. When source context is broad, extract targeted excerpts first rather than dumping an entire corpus into Haiku.

## Main agent and scope

Default coordinator: **Sonnet 5.5 / Medium**. Opus 5.5 / Medium on complex business decisions; stronger model only when needed. The main model is selected in the session, not by subagent frontmatter. Write only to project-workspace/work/ or project-workspace/tests/.

## Workflow routing

| Complexity | Trigger | Assigned role | Preset |
|---|---|---|---|
| S0 | Classification, indexing, deterministic extraction, format checks | ba-intake-extractor | Haiku 5.5 / medium |
| S1 | Clear, localized story/AC from complete inputs | ba-analyst | Sonnet 5.5 / medium |
| S2 | Test matrix, boundary cases, RTM from signed-off spec | qa-test-designer | Sonnet 5.5 / medium |
| S3 | Business-rule conflicts, financial/data/security implications, cross-system behavior | ba-domain-auditor | Opus 5.5 / medium |
| S4 | Independent coverage/risk audit or high-impact release assessment | qa-coverage-auditor | Opus 5.5 / medium |
| S5 | Approved, non-destructive test verification | qa-execution-assessor | Sonnet 5.5 / high |
| S6 | Epic/Feature/Task triage | ba-backlog-manager | Sonnet 5.5 / medium |
| S7 | Manual cases/exploratory/evidence | qa-manual-tester | Sonnet 5.5 / medium |
| S8 | Approved test automation | qa-automation-engineer | Sonnet 5.5 / high |

When urgency/complexity warrants, jump directly to S3/S4. Do not always start with Haiku. If a Sonnet artifact fails a targeted review, revise a concrete issue once; escalate unresolved conceptual problems to Opus. Do not spend more than two same-tier unsuccessful attempts.

## Effort escalation

- low: quick classifications/summaries with trivial error cost; use interactively where appropriate.
- medium: default BA and test-case authoring.
- high: complicated multi-step test reasoning or high-stakes review.
- xhigh: exceptional investigation only, after medium/high fails with an identifiable gap.
- max: one-off critical recovery only; do not set as a persistent project default.
- Fable 5.1: explicit user-approved exception; may require credits; do not silently select.

An effort is not a price multiplier. Evaluate on real business cases and total token/tool usage.

## Subagent mechanics

Each .claude/agents/*.md defines model and effort in frontmatter. The *main* session's model is a separate UI/CLI setting, not overridden by these rules. CLAUDE_CODE_SUBAGENT_MODEL and invocation overrides can replace frontmatter; account restrictions may cause fallback. Report actual model if available, otherwise say unverified. Don't claim hard caps on quota from prompts alone.

## Delegation contract

Provide: objective, scope, exact evidence files/sections, immutable business constraints, expected artifact, allowed tools, and done-when. Return concise findings, evidence pointers, ambiguities, risks and any unexecuted steps. Do not pass full project history or irrelevant templates. Independent reviewers receive the artifact and its sources, not the original author's self-justification.
