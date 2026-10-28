# OptClaudeCodeRules — BA / Tester v1.2 (flat workspace)

Reusable Claude Code rules, BA/QA specialist agents and templates. Main-agent recommendation: **Claude Sonnet 5.5 / Medium**.

## Flat project-workspace: exactly two data directories

    project-workspace/
    ├── work/
    └── tests/

There are **no required or auto-created subdirectories** within either directory. This rules pack does not prescribe a folder taxonomy for BA tasks, features, manual tests, reports, E2E, API tests or fixtures. Keep pre-existing files and their filenames/layout intact. Place existing BA/QA materials directly in work/ and existing automation files directly in tests/, without reclassification, renaming or restructuring. If pre-existing materials already have their own arrangement, do not migrate or modify it automatically.

- work/ holds existing BA work items, business analysis, requirements, user stories, AC, manual test cases, testing results, bugs, reports, traceability and automation plans.
- tests/ holds the user's existing runnable automation tests and supporting files. No enforced runner, naming convention or test-type folders.

Tools should **find and use the existing files** instead of manufacturing a new tree. Feature/TC IDs and links may live in file content; do not demand particular filenames or paths. Do not manufacture empty epics, feature registers, test cases, directories or duplicate files to satisfy a template.

Root CLAUDE.md, .claude/agents/, .claude/skills/, and docs/ba-qa/ are **distribution/configuration files belonging to the rules repo**, not extra working folders under project-workspace/. Agents must not overwrite them during user work.

## Task routing

BA:
- Work management: intake, tasks, owner, priority, dependency and status.
- Analysis: AS-IS/TO-BE, business rules, requirement clarification, story and testable AC.
- Independent domain review of high-risk ambiguities.

Tester:
- Manual: test design, exploration, real observed results and defects.
- Automation: automation candidate selection, TC-to-script mapping, authorized test code edits and scoped execution.
- Independent coverage/quality review and honest status/evidence.

Recommended main agent is Sonnet 5.5 Medium; Haiku is used for simple extraction, Sonnet for normal BA/QA tasks, and Opus for high-risk review. Main session selection is configured in Claude Code; frontmatter sets agent presets, not the main model.

## How to use

Launch Claude Code from the repository root to load the bundled CLAUDE.md and agents; use /model and /effort to choose Sonnet 5.5 Medium. Put existing files into work/ or tests/ without rearranging them. Ask for BA/Tester work; the agent searches existing files and operates in place.

The rule pack only **manages project data** in project-workspace/work/ and project-workspace/tests/. Reading authorized source documents elsewhere is permitted; writing outside the two destinations, creating subdirectories, rewriting unrelated artifacts or modifying product code is not. No production or destructive test operations without explicit permission. Scripts are not proof of passing tests.

## Configuration

See docs/ba-qa/framework/WORKSPACE_RULES.md for the binding workspace contract, and the other frameworks/templates only when needed.

Claude Code documentation: https://code.claude.com/docs/en/sub-agents | https://code.claude.com/docs/en/skills

## Reduce repetitive Claude in Chrome approval prompts

During UI testing, keep Claude Code out of **Plan Mode** because state-changing browser calls prompt there. Use \`/chrome\` to confirm connection, and \`/permissions\` to inspect Claude Code Ask/Allow/Deny rules. In the **Claude in Chrome** extension, trust only the specific staging/test origin via **Always allow actions on this site** when appropriate; **Allow this action** grants only one action. If your side panel supports **Automatically approve**, it can reduce per-step approvals while retaining safety checks; do not use **Skip all approvals** for routine QA. Some protected actions must still request approval.

Agent instructions now implement one scoped QA-Handoff UI-test agreement and avoid *self-imposed* per-click conversational confirmation. They deliberately cannot bypass genuine tool or extension prompts. Full policy: docs/ba-qa/framework/BROWSER_TEST_SESSION_RULES.md. For production and sensitive websites, keep manual approvals.

Docs: https://code.claude.com/docs/en/chrome | https://support.claude.com/en/articles/12902446-claude-in-chrome-permissions-guide
