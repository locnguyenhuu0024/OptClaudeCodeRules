# Artifact discipline — flat working folders (v1.2)

All BA/Tester project writing is constrained to direct files inside project-workspace/work/ or project-workspace/tests/. No new subdirectories may be created.

- work/: existing backlog/tasks, business analysis, requirements, AC, manual cases, run records, defects, traceability, plans, reports.
- tests/: existing or specifically approved runnable automation scripts, fixtures, helpers and safe output files.

Do not impose a mandatory document set, naming pattern, Epic/Feature dossier tree, test-type subdivision or migration. Locate existing records first, update in place, and preserve their established filename, language, formatting and organization. If a document already combines several concerns, do not split it merely to satisfy this rules pack. New files are optional and go directly inside one of the two folders.

Keep requirement -> AC -> Test Case -> evidence/defect traceability in file contents or existing identifiers, not directory paths. Reuse supplied sources and versions. Do not change existing approved conclusions without an explicit decision. Manual or automated tests authored but not run must show NOT_RUN. Report actual checks performed and evidence, never fabricated successes.

Reusable templates under repo-root docs/ba-qa/templates/ are reference-only and not work output. Do not create docs/ba-qa/artifacts/, project-workspace/test-results/ or any third managed project tree.
