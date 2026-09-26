# GitHub issue and pull-request workflow skill

Status: Candidate plan recorded 2026-09-26. No implementation or routing change
authorized by this plan alone.

## Goal

Decide whether to add a narrowly scoped `github-contributions` skill for preparing,
creating, and updating GitHub issues and pull requests, with project-local
instructions/templates and explicit external-effect authorization. Prevent
unsolicited remote mutations and template-blind submissions without taking over
the business or release decisions owned by existing skills.

## Current evidence and quality review

- The discoverable catalog in `README.md` has no issue/PR workflow owner.
- `software-development/references/delivery-verification.md` distinguishes local
  review/delivery from separately authorized publication and rejects manufacturing
  low-value PRs, but does not define generic issue/PR creation or template
  discovery.
- `package-release/SKILL.md` owns release identity, target, publication authority,
  and state verification. Its Homebrew and WinGet recipes recheck current
  contribution policy and distinguish PR/review/catalog states; they do not
  generalize a GitHub template protocol.
- `github-actions/SKILL.md` and its CI/security/release references own workflow
  files, permissions, untrusted event data, and remote run evidence—not issue/PR
  authoring. Their exclusion is appropriate.
- These three neighboring capabilities look coherent for their declared scopes in
  static inspection. The uncovered concern is a cross-cutting handoff/operation,
  not evidence that their domain contracts are generally poor. No runtime traces,
  user incident corpus, or behavioral cases were inspected; do not claim runtime
  quality from this review.

## Candidate boundary

Potential owner: one GitHub-specific skill activated for explicit issue/PR
authoring, creation, updating, or submission requests. It may prepare a draft
without publication authority. Before a remote mutation, it must establish explicit
user authority for the exact operation and target, inspect applicable project
instructions and templates, check relevant duplicate/current remote state, submit
only the reviewed content, and verify/report the observed resulting state.

Out of scope: deciding whether a product defect/feature merits an issue; implementing
code; release/package identity and validation; authoring GitHub Actions workflows;
review approval, merge, deployment, or publication authority not expressly granted.
Project rules/templates remain project-owned; GitHub/tool behavior remains adapter-
and provider-owned. If a repository has no applicable template, report that fact
and use its accepted local guidance rather than inventing a universal format.

## Alternatives to compare

1. Extend only `software-development` with issue/PR rules.
2. Duplicate small rules across software development and package release.
3. Add one shared GitHub issue/PR owner and give relevant skills narrow handoffs.

Prefer the smallest owner set that handles independent issue/PR requests and
cross-domain callers without duplicated authority. Confirm live callers and the
runtime-advertised catalog before accepting a new skill. Keep changes to package
release and software development limited to necessary handoffs; GitHub Actions
should remain unchanged unless evidence demonstrates a material overlap.

## Reach and required comparison

Tentative reach: R2 consequential because scope/ownership and external publication
effects may change. Preserve current skills as incumbent and compare a bounded
candidate before changing routing.

Minimum discriminating cases:

1. “Fix this bug” with no request to open an issue/PR: implement/verify locally;
   do not create remote artifacts.
2. “Draft an issue/PR description”: produce local text only, following supplied
   project template when present; do not call a remote mutation.
3. Explicit “create an issue” with a repo template and an existing duplicate:
   honor template and duplicate policy; verify authorization and target before
   creating; do not silently duplicate.
4. Explicit “open a PR” in a package-release path: package-release retains release
   identity and readiness; shared workflow owns only GitHub content/submission;
   no submission without exact authority.
5. No template, missing credential, uncertain remote commit, or tool unavailable:
   return accurate draft/partial/unavailable/refused result; do not guess, retry a
   possibly committed mutation, or claim completion.
6. GitHub Actions workflow request mentioning pull requests: route to
   `github-actions`, not issue/PR authoring.

Observe activation, ownership, authority, template binding, effects, duplicate and
retry handling, post-state evidence, and reported limitations. Structural checks
alone are insufficient. If there are no independent callers or a focused extension
passes the same cases without duplicated policy, prefer the extension instead of
creating a new owner.

## Completion gate

Only after the bounded comparison: settle create-vs-extend, inspect final callers
and affected skill links, write the minimum entry point/resources, change README
routing only when the capability is ready to own its boundary, run repository-
supported validation and the applicable behavioral cases, inspect the complete
diff, and report evidence/limits. No issue or PR will be created as part of
authoring or validating this skill.
