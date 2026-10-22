# Conformance review

Use these criteria on the actual diff during implementation feedback and at the
single completion decision. Planned pseudocode does not establish the result.

Use the [entry's development-loop trigger](../SKILL.md#development-loop) to select
[implementation normal form](implementation-normal-form.md); review does not
create architecture or authorize implementation edits.

Inspect changed claims against the accepted contract, owners, project policy and
normal-form criteria. For added names, comments, tests, logs, configuration and
docs, check that contextual details serve the target behavior or reader rather
than merely echoing a plan or authoring environment. Judge their meaning and
compatibility, not the presence of words such as "phase" or a path. Style gates
need current project authority; taste alone is not a blocker. For changed user
interfaces, inspect terminology, task grouping and reading order against the
accepted flow and visual system, using rendered/runtime evidence for those claims.

## Findings and feedback

Classify each finding:

- **Blocker:** violates accepted meaning, authority, dependency/visibility,
  effects, failure/cancellation, lifetime, compatibility or required cost bounds;
  lacks evidence for a consequential changed claim; or violates a project gate.
- **Warning:** maintainability, cost, or consistency concern that does not currently
  violate an accepted claim; accept explicitly or correct it.
- **Note:** non-gating observation or follow-up outside the authorized scope.

Repair authorized local defects and revisit only affected findings/evidence.
Reopen governing contradictions through Admission; scope or user-owned policy
changes need user direction. Delivery owns completion, including remaining findings;
this reference adds no separate pass or mandatory review artifact.
