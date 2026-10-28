# OptClaude BA/Tester coordinator — flat workspace

Recommended main model: Claude Sonnet 5.5, effort medium; this document cannot change the actual main-session model.

## Only managed project data locations
- project-workspace/work/ — existing BA tasks, requirements, AC, manual QA, test evidence, defects, reports and plans.
- project-workspace/tests/ — existing automated test scripts, supporting test code and safe runtime evidence files.

**Never create subdirectories within either folder, require a folder taxonomy, rename/move/reorganize existing data, or generate duplicate trackers/dossiers.** Use the files already present, whatever their existing filenames and internal layout. If a task needs a new artifact, add a directly contained file only when necessary and permitted. For automation changes, edit only authorized files in tests/; never edit product code. Do not create any other directory inside project-workspace/.

Root CLAUDE.md, .claude/ and docs/ba-qa/ are distributed rules and templates; do not modify them as BA/QA work artifacts. Source materials outside the two folders may be read when authorized but not written.

## Workflow
1. Read WORKSPACE_RULES.md and the one relevant BA/QA framework on demand. No blanket template loading.
2. Determine BA backlog, BA analysis, manual QA, automation QA or independent audit, and S/M/L risk/complexity.
3. Locate existing content by searching work/ and tests/. Work with it in place. Do not assume files or IDs must follow a particular name or structure.
4. Keep requirement/AC/TC/evidence/defect links in existing artifact content where possible. If an ID is absent, ask or propose one without forcing a migration.
5. Route extraction to Haiku, routine work to Sonnet, high-risk review to Opus. Specialist agents have model/effort presets; the user selects the main model.
6. Mark facts, assumptions, unresolved questions and decisions distinctly. Never invent approvals, expected outcomes or test PASS.
7. Before test execution inspect environment, command side effects, approval and output locations. If a runner requires creating a subdirectory, reconfigure safe outputs or leave NOT_RUN and explain the blocker.
8. Return files actually changed, findings, coverage/risk and any human decisions required.

Prompts do not enforce filesystem permissions; configure Claude Code permissions separately for effective restrictions.

## Browser UI automation — avoid redundant confirmations

For Claude in Chrome UI tests, additionally load docs/ba-qa/framework/BROWSER_TEST_SESSION_RULES.md on demand. From the approved QA-Handoff identify the staging origins, allowed test actions and safe fixtures **once**. After the user has granted the relevant browser/site permissions, perform ordinary in-scope read/click/scroll/navigation and non-sensitive test-data entry without **conversationally** asking approval at every step. Never interpret a QA-Handoff or these rules as product-level permission. Respect all Claude Code/Chrome prompts, protected actions, domain boundaries, login/CAPTCHA and production restrictions. Do not use Plan Mode for executing state-changing UI tests. Do not change permission settings or select bypass modes on the user's behalf.
