# Feature dossiers (create on demand)

Each Feature has exactly one directory: FEAT-<ID>-<slug>/. Example desired organization when required:

    FEAT-001-short-slug/
      brief.md
      status.md
      ba/
        discovery.md
        business-process.md
        business-rules.md
        requirements.md
        user-stories.md
        acceptance-criteria.md
        decisions.md
      qa/
        test-plan.md
        manual/
          test-cases.md
          exploratory.md
          executions.md
        automation/
          automation-plan.md
          test-mapping.md
        defects.md
        test-report.md
      traceability.md

Do not create imaginary FEAT-001 records in backlog. Create only needed files when a real feature is approved for work. Test scripts reside in project-workspace/tests/, linked from the automation mapping.
