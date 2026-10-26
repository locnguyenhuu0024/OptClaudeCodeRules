# Business Analysis rules

## Intake and scope
Find actual task/context files in project-workspace/work/ without assuming special folders or filenames. Establish objective, stakeholders/actors, current vs desired behavior, source/version, constraints, in/out scope, dependencies and blocking decisions.

## Work management
Track Epic/Feature/Story/Task when these concepts exist in the user's records; preserve existing IDs and project conventions. Maintain priority rationale, owner (if known), dependency, status and next decision. Update relevant existing file(s) in work/ directly. Do not create dummy lists, duplicate issue trackers or force a hierarchy. A task marked Done is not BA approval.

## Analysis
Describe AS-IS/TO-BE workflows, state transitions, permissions, business rules, exceptions, validations, calculations, rounding/timezones, integration contracts and applicable NFRs. Distinguish approved facts from inference/assumption/open questions. Derive objectively testable acceptance criteria with observable preconditions/actions/results. Use Given/When/Then where helpful, not obligatorily. Tag each criterion with available source/ID. Surface unresolved contradictions and human decision owners.

## Quality
Avoid unmeasurable words without thresholds, hidden business decisions or oversized documents for minor changes. Reuse existing feature documents without relocating or renaming them. Put all new BA output as directly contained files in project-workspace/work/ only; no child directories. Reference WORKSPACE_RULES.md for immutable boundaries and no-migration policy.
