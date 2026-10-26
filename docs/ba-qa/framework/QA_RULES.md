# Tester / QA rules

## Shared preparation
Read existing approved requirements, acceptance criteria, prior test cases and product restrictions as actually available in project-workspace/work/ or user-authorized sources. Never assume a prescribed file or folder layout; preserve existing test IDs and conventions.

## Manual testing
For test design, cover positive, negative, boundary, role/permission, state, recovery and risky integration scenarios. Specify preconditions, data, precise actions and observable expected outcomes. Save or revise manual case records, exploratory charters, actual observations and bugs as direct files under work/. Case creation is NOT_RUN, not PASS. Human-reported results and evidence must include provenance; if no safe observation exists, report BLOCKED/NOT_RUN/INCONCLUSIVE.

## Automation testing
Select stable, repeatable cases for automation, map to existing test IDs/AC, and record selection/mapping in direct work/ files. Implement only requested, authorized automation code/support files directly in tests/. Follow existing framework and established naming; no mandatory e2e/api/fixtures child directories and no gratuitous dependency installation. Never modify product source. Do not assume implementation proves passing execution.

## Execution
Inspect environment, commands, possible side effects and permission before running. Do not touch production payments, messages, private data, destructive DB actions or load unless separately approved. Output must use files directly within tests/ or work/ only. If the runner cannot avoid directory creation, do not execute; report the issue for a decision. For any run, record command, build/environment, actual result, time, evidence and honest PASS/FAIL/BLOCKED/NOT_RUN/INCONCLUSIVE status.

## Reporting
Provide test coverage, high-risk gaps, linked defects, regressions and an evidence-backed Go/Conditional/No-Go recommendation, not a release approval. All output is in work/ or tests/ with no new subfolders; see WORKSPACE_RULES.md.
