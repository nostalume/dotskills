---
name: software-documentation
description: Write or review audience-specific software explanations, guides, references, and change notes from authoritative, versioned behavior. Exclude product changes and external publication.
---

# Software Documentation

Own the semantic accuracy and usefulness of software documentation. Treat each
document as an audience-specific projection of the same domain contract as the
software, not as late prose copied from implementation shape.

## Documentation contract

Before writing, state:

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
presence, or ignore rules: Git ignores do not provide confidentiality. Keep plans
and scratch separate from durable docs; copy plan details into public docs only
when authorized and useful to the named reader.

Inspect current source, public interfaces, help/schema output, tests, existing
docs, examples, and release history as applicable. Prefer domain vocabulary and
observable operations over internal call inventory. Write the shortest complete
path first, then add detail only for a real reader decision, failure, or boundary.
Include project layout only to answer a reader's navigation or architecture
question when a concise link will not suffice; do not duplicate discoverable
structure by default.

Documentation work grants no authority to change product behavior or publish an
artifact. A review-only request does not authorize documentation edits. If writing
exposes an unresolved domain, ownership, compatibility, or failure decision, stop
short of inventing the rule and report the exact decision and evidence still needed.
If documented behavior and implementation disagree, report the contradiction;
this documentation task does not authorize product changes.

## Route by audience and artifact

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

Record commands, environment, observed outcomes, skipped checks, and limits. Mark
generated sections and their source; do not hand-edit generated truth. State an
owner or trigger for version-sensitive claims and reopen the document when its
authority, behavior, audience, or supported version changes.

Do not call documentation complete while a current claim lacks authority, an
example is predictably stale or unexecuted without disclosure, a proposal reads as
implemented fact, or rendered output required by the task has not been inspected.
