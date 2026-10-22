---
name: software-documentation
description: Write or review audience-specific software explanations, guides, references, and change notes from authoritative, versioned behavior. Exclude product changes and external publication.
---

# Software Documentation

Own the semantic accuracy and usefulness of software documentation. Treat each
document as an audience-specific projection of the same domain contract as the
software, not as late prose copied from implementation shape.

## Documentation contract

Before writing, establish the following as authoring inputs, not a required
section template:

- the audience, its immediate question, and the decision or successful action the
  document must enable;
- the intended exposure class and canonical destination, distinguishing public,
  internal, and local-only material;
- the authoritative source for every current claim and the software/version or
  compatibility range to which it applies;
- whether the artifact describes observed behavior, an approved future contract,
  a proposal, or historical change;
- the requested output, publication authority, and evidence that will make the
  result trustworthy.

Do not infer privacy, publication intent, or agent visibility from paths, worktree
presence, or ignore rules: Git ignores do not provide confidentiality. Select
content by the reader's task and the document's contract; source authority alone
does not make a detail useful to publish. Keep plans and authoring state in task
records. Include environment or layout details only when they affect reader
action or interpretation, using supported requirements and reader-usable paths
rather than incidental workstation bindings. A requested local diagnostic or
reproduction record may need exact bindings; preserve that document's scope.

Inspect relevant source, interfaces, help/schemas, tests, docs, examples and release
history. Use stable domain terms for the same concepts, defining unfamiliar terms
and necessary aliases before relying on them. Organize around the reader's question
and prerequisites; each section advances that question using already established
ideas. Keep reference lookup and expert summaries compact where their audience
permits it. Add layout only for a navigation/architecture question that a concise
link cannot answer; environment and other detail must satisfy the reader contract.

Review grants no edits; documentation grants no product change or publication.
Report source/behavior contradictions and unresolved domain, ownership,
compatibility or failure decisions with the exact missing evidence; do not invent
the rule.

## Route by claim and reader

After establishing the audience, source authority, version scope, and exposure,
select one route:

| Route | Primary reader need | Closure evidence |
|---|---|---|
| Onboarding/how-to | perform a supported task | clean or declared consumer-path success |
| Conceptual/troubleshooting | understand behavior or recover from failure | authoritative explanation plus boundary cases |
| Developer guidance | modify, extend, build, or debug | current source, commands, and project policy |
| CLI/API/reference | use an interface correctly | help/schema/public behavior comparison |
| Change/migration note | understand revision or compatibility impact | actual revision range and accepted contract |
| Review | find drift or unsupported claims | findings only; no edits |

## Load route guidance

Load only guidance and checks for the selected route. Rendering, generation, and
publication tools are optional evidence adapters; they do not define software
meaning or grant publication authority.

- For onboarding, how-to, troubleshooting, and conceptual guidance for operators
  or consumers, read [user documentation](references/user-documentation.md).
- For maintainers, contributors, architecture, extension, build, test, and debug
  guidance, read [developer documentation](references/developer-documentation.md).
- For CLI/API/schema reference, decision records, migration notes, or release
  notes, read [reference and change documentation](references/reference-and-change-documentation.md).

Keep software meaning and audience fitness distinct from physical-format
properties. For format-specific conversion, rendering, or inspection, use
[document-artifacts](../document-artifacts/SKILL.md) as an optional one-hop
handoff when available. The documentation workflow remains complete for accepted
text and semantic checks without it; if the requested physical-format guarantee
cannot otherwise be established, report that exact limitation. Check content from
extracted or transformed sources against authoritative software behavior; preserve
source references and uncertainty. Successful extraction or rendering alone does
not establish that an explanation is correct.

## Validation and result

Select checks from the claims actually made:

- execute snippets, doctests, commands, and minimal success paths in a clean or
  declared environment;
- build/render the artifact and inspect navigation, anchors, links, layout, code
  blocks, and accessibility where applicable;
- compare CLI help, schemas, generated references, public API, supported versions,
  and docs for drift;
- exercise installation instructions from the published/packaged consumer path
  rather than an ambient source checkout when that distinction matters;
- compare release or migration claims with the actual revision range and accepted
  compatibility contract.

Report validation commands, environment, observed outcomes, skipped checks and
limits in the task result or existing verification record; put them in the
document only when its reader contract needs them. Mark generated sections and
their source; do not hand-edit generated truth. State an
owner or trigger for version-sensitive claims and reopen the document when its
authority, behavior, audience, or supported version changes.

Do not call documentation complete while a current claim lacks authority, an
example is predictably stale or unexecuted without disclosure, a proposal reads as
implemented fact, or rendered output required by the task has not been inspected.
