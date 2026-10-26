---
name: qa-automation
description: Select automation candidates, map TC IDs to scripts, implement safe scoped automated tests and assess evidence.
---
# QA automation

Read WORKSPACE_RULES and QA_RULES. Decide test candidates based on criticality, stability, isolation and maintenance costs. Plans/mappings belong to project-workspace/work/features/<FEAT-ID>-<slug>/qa/automation/; runnable scripts, fixtures, helpers and test config belong only in project-workspace/tests/. Use preexisting framework, scoped deterministic fixtures and TC IDs. Before execution inspect command and permissions, avoid external/production mutations, and keep ignored run artifacts inside tests/. No application source edits; writing code is not proof of execution.
