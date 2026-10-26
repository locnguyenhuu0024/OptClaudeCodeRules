---
name: qa-manual
description: Prepare manual scenarios, executable cases, exploratory charters, observed run sheets and bug reports.
---
# QA manual testing

Read WORKSPACE_RULES and QA_RULES. Map each case TC -> AC -> requirement. Include priority, preconditions, test data, precise steps, expected observable result and edge cases. Store under project-workspace/work/features/<FEAT-ID>-<slug>/qa/manual/. Case defaults NOT_RUN; never claim PASS without evidence, timestamp and environment. Defects/test summaries stay in that feature's qa/; do not write to code or automation tests.
