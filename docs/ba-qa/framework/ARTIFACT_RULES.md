# BA/QA artifacts, provenance and boundaries — v1.1

Only managed project roots: `project-workspace/work/` and `project-workspace/tests/`.

Under work/: backlog/ for canonical epics/features/tasks, features/<FEAT-ID>-<slug>/ba/ for BA, qa/manual/ for manual design and *observed* runs, qa/automation/ for automation plans and TC mappings, qa/ for defects/reports and feature root for brief/status/traceability.

Under tests/: e2e/, api/, integration/, fixtures/, helpers/ for executable test code. Runtime reports are kept under tests-local ignored paths, with sanitized summaries in work/. Do **not** write to the legacy `docs/ba-qa/artifacts/` path, or create `project-workspace/test-results/`.

Reusable templates live under repository-root docs/ba-qa/templates/ and are read-only during user project workflows. Do not overwrite approved artifacts without versioning and explicit decisions. Cite sources, versions and actual observed evidence. Do not infer PASS from writing scripts.

For S work, a small edit is enough. For M/L work, load only templates necessary to the task. Follow `WORKSPACE_RULES.md` on IDs, boundaries and human approval.
