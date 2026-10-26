# WORKSPACE_RULES — flat data placement (v1.2)

## Hard working scope

Only these two project data containers exist in the managed layout:

    project-workspace/work/
    project-workspace/tests/

**No agent may introduce subdirectories inside work/ or tests/.** Do not auto-generate backlog/, features/, manual/, automation/, e2e/, api/, integration/, fixtures/, helpers/, reports/, artifacts/ or a project-workspace/test-results directory.

work/ is a general container for every BA work item, process analysis, requirement, user story, acceptance criterion, manual test document, defect, testing note, traceability record, automation plan and test report. tests/ is a general container for existing or user-approved automated tests/support files and outputs that fit the flat layout.

## Existing data wins

- Users place their current documents/files in one of the two directories directly. Do not require a file naming convention, migrate an older layout, split/merge documents, rearrange artifacts, or auto-create a standard project skeleton.
- If existing data is already arranged differently, **do not reorganize it**. First inspect and report a conflict if the task would require writing to a nested or disallowed path; seek instructions instead of moving, overwriting or deleting it.
- Prefer updating existing relevant files over creating new ones. Only create a direct child file (no nested path) when requested or genuinely necessary and within scope.
- Do not create empty Epic, Feature, Story, Task, test or defect registers without a real need. No dummy FEAT-001 directories or fake sample tasks.
- Feature and Test Case IDs, where already present, should be preserved and referenced inside documents. Traceability is logical, not based on directory names. Human approval remains necessary for signed-off requirements and releases.

## Task ownership

BA backlog and business analysis: write relevant files directly in work/.
Manual test design, exploratory outcomes, bug reports and test summaries: write directly in work/.
Automation planning and mapping: write directly in work/.
Automated script/fixture/helper changes: write directly in tests/.
Read authorized external sources only; no product-code changes, no writes to other project trees or the rules pack configuration.

## Execution

Newly authored tests are NOT_RUN; only observed execution with build, environment, timestamp and evidence may be PASS/FAIL. Runner files/logs must be redirected to direct files under tests/ or summarized/redacted into files directly under work/. If tooling insists on nesting outputs and cannot be configured safely, stop and report NOT_RUN/BLOCKED; do not create a subfolder to bypass the contract.

Preserve existing files unless the requested edit explicitly changes them. Before writing, resolve target paths and reject traversal/symlinks escaping the allowlist. Read-only evidence outside these locations does not permit writes there. Tool permission settings, not prose, provide actual enforcement.
