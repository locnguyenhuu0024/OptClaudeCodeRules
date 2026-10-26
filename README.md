# OptClaudeCodeRules — BA / Tester Pack (v1.0)

Reusable Claude Code rules for Business Analysts and QA/Testers. Verified for the Claude 5.5 lineup on 2026-10-26.

## Design goals

- **Correctness before verbosity:** separate facts, assumptions, open questions and recommendations.
- **Traceability:** every acceptance criterion and test case maps back to a requirement/source.
- **Cost awareness:** cheap extraction first; use stronger model for decisions and independent audits.
- **Context discipline:** short always-loaded CLAUDE.md; load framework/templates only when relevant.
- **Read-only by default:** do not modify application code, databases or production data.

## Install into a working project

Copy the following paths into the root of the *target* repository (not your global home directory):

    CLAUDE.md
    .claude/agents/
    docs/ba-qa/framework/
    docs/ba-qa/templates/

Start Claude Code from that target repository. Check with /agents and /context. On first creation of an agents directory during a running session, restart Claude Code if the agents do not appear. No CLI plugin, extra daemon, or API proxy is required.

For a BA-only task, ask: "Analyze this feature as a BA; produce requirements, ambiguity log, user stories and testable acceptance criteria; do not implement."
For test design, ask: "Design a risk-based test suite and RTM for feature X based only on approved requirements."
For audit, ask: "Independently audit this BA/QA pack for omissions, unsupported assumptions and non-testable acceptance criteria."
For verification, ask: "Inspect the test commands and execute only approved non-destructive checks in a disposable environment; report actual evidence and limitations."

## File guide

- CLAUDE.md — small routing, safety and output contract, loaded on startup.
- docs/ba-qa/framework/ROUTING_RULES.md — decision framework and price/effort guidance.
- docs/ba-qa/framework/BA_RULES.md — requirement and acceptance criteria discipline.
- docs/ba-qa/framework/QA_RULES.md — test case design, execution and defect discipline.
- docs/ba-qa/framework/QUALITY_GATES.md — BA/QA readiness gates.
- docs/ba-qa/framework/ARTIFACT_RULES.md — artifact boundaries and evidence handling.
- docs/ba-qa/templates/ — load only the template needed for the task.
- .claude/agents/ — six purpose-built agents with pinned Claude model IDs and effort.

## Baseline routing (cost optimization, not a guaranteed benchmark)

| Work | Agent | Model | Effort |
|---|---|---|---|
| Extract/source inventory | ba-intake-extractor | claude-haiku-5-5 | medium |
| BA requirements/story design | ba-analyst | claude-sonnet-5-5 | medium |
| Independent domain review | ba-domain-auditor | claude-opus-5-5 | medium |
| Test case and RTM design | qa-test-designer | claude-sonnet-5-5 | medium |
| Risk/coverage audit | qa-coverage-auditor | claude-opus-5-5 | medium |
| Authorized test evidence collection | qa-execution-assessor | claude-sonnet-5-5 | high |

For exceptional tasks, manually escalate the session or revise the specific agent only after confirming model access and budget. Fable 5.1 is NOT launched automatically; it may require usage credits.

Claude Code does not dynamically change the *main-session* model merely because CLAUDE.md says so. The main agent delegates work to separately configured agents. The CLAUDE_CODE_SUBAGENT_MODEL environment variable and per-invocation overrides may supersede frontmatter; verify the effective model/effort. Global settings and account/organization model availability can also apply.

## Official API list prices as of 2026-10-26

| Model | Input $/MTok | Output $/MTok |
|---|---:|---:|
| Haiku 5.5 | 0.10 | 0.50 |
| Sonnet 5.5 | 2 | 10 |
| Opus 5.5 | 4 | 20 |
| Fable 5.1 | 10 | 50 |

Haiku 5.5 costs $0.50 input and $2.50 output per MTok once the prompt exceeds 100k input tokens. Effort changes *token/tool consumption*, not the fixed per-token tariff. These API prices do not convert directly to Pro/Max subscription quota or guaranteed cost per task.

## Model IDs and compatibility

Full model IDs are intentionally pinned for reproducibility. Refresh this pack if model IDs are retired, newer models pass your evaluations, or your organization forbids one of the pinned IDs. Model/effort support and subscription availability must be verified on the target account.

## Safety / quality boundary

No fabricated test run, screenshot, business rule or source citation. No silent requirement decisions. No production writes, destructive database operations, secret exposure or code changes without explicit authorization. A generated plan or test case is NOT proof of an executed test.

## References

- https://platform.claude.com/docs/en/models/overview
- https://platform.claude.com/docs/en/models/haiku-5-5/overview
- https://platform.claude.com/docs/en/about-claude/pricing
- https://code.claude.com/docs/en/sub-agents
- https://code.claude.com/docs/en/model-config
- https://code.claude.com/docs/en/memory
