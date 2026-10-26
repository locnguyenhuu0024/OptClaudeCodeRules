# OptClaudeCodeRules — BA / Tester Pack v1.1

Reusable Claude Code configuration for BA work management, business analysis, manual testing and automation testing.

## Main agent
Recommended default: **Claude Sonnet 5.5, effort Medium**. Use Opus 5.5 Medium for particularly difficult multi-system business decisions or architecture; specialized agents use their own configured presets. A rule cannot force the main session's model.

## Managed project scope (strict)
This repository distributes reusable rules at root `CLAUDE.md`, `.claude/` and `docs/ba-qa/`. These are configuration, NOT generated project work.

Inside `project-workspace/`, only the following directories are managed:
- `project-workspace/work/`: BA backlog, one dossier per Feature, BA requirements, manual QA, QA plans, evidence, defects, traceability.
- `project-workspace/tests/`: executable automation tests, fixtures, helpers and ignored local test outputs.

Do not create or manage another tree under `project-workspace/`, including `test-results/`, `docs/` or `.claude/`. Do not change application code as part of BA/QA operations.

## Layout
```text
OptClaudeCodeRules/
├── CLAUDE.md
├── .claude/
│   ├── agents/                  # BA / QA specialized subagents
│   └── skills/                  # on-demand workflows
├── docs/ba-qa/
│   ├── framework/               # routing, BA, QA, workspace contract, quality
│   └── templates/               # reusable document templates
└── project-workspace/
    ├── work/
    │   ├── backlog/
    │   │   ├── epics.md
    │   │   ├── features.md
    │   │   └── tasks.md
    │   └── features/
    │       └── FEAT-001-sample-slug/      # create on demand, not prepopulated
    │           ├── brief.md
    │           ├── status.md
    │           ├── ba/
    │           │   ├── requirements.md
    │           │   ├── business-rules.md
    │           │   ├── acceptance-criteria.md
    │           │   └── decisions.md
    │           ├── qa/
    │           │   ├── test-plan.md
    │           │   ├── manual/             # cases, exploratory, observed runs
    │           │   ├── automation/         # plans, TC-to-script links only
    │           │   ├── defects.md
    │           │   └── test-report.md
    │           └── traceability.md
    └── tests/
        ├── e2e/
        ├── api/
        ├── integration/
        ├── fixtures/
        └── helpers/
```

One canonical Feature ID is shared by BA and QA. Never create separate BA and QA feature registries. Create optional dossier files only when needed. Executable tests belong exclusively to `tests/`.

## Workflow
1. BA work management: Epic -> Feature -> User Story -> Task.
2. BA analysis: discover sources, map AS-IS/TO-BE, define business rules and measurable acceptance criteria.
3. QA design: trace AC -> test case, choose manual or automated.
4. Manual testing: design and capture honest observations.
5. Automation: implement approved tests in `tests/`; store maps and test plans in `work/`.
6. Independent audit and coverage/defect reporting. Humans own business approval and release decisions.

## Run
Clone this repo and start Claude Code at repository root to discover CLAUDE.md, agents and skills, while managing only `project-workspace/work/` and `project-workspace/tests/`.
Use `/model` (Sonnet 5.5) and `/effort medium` for the main session; use `/agents` to inspect specialist agents. When integrating elsewhere, keep the managed path convention or update all rules accordingly.

## Safety
Permission-bound read of relevant outside sources is possible; write scope stays in two managed trees. Never run destructive tests or production writes without explicit approval. Do not fabricate approvals, expected results or passed tests. Test runner output stays in ignored directories under `tests/`, with redacted summaries under `work/`.

Docs: https://code.claude.com/docs/en/sub-agents | https://code.claude.com/docs/en/skills | https://code.claude.com/docs/en/model-config
