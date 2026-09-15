---
name: skill-development
description: Design, refactor, consolidate, retire, or semantically review Codex skills when capability boundaries, ownership, portability, effects, or behavioral evaluation are material; also create skills that require those decisions. Leave routine structural scaffolding or UI metadata to the generic skill creator, and ordinary software or artifact work to its domain owner.
---

# Skill Development

Own the boundary and behavior of a skill, not the domain facts, project policy, or
external services it uses. Preserve the user's intent and reserved decisions. An
existing project owns its instructions, conventions, manifests, lockfiles, and
accepted local resources. Source owners retain authority over factual content.
Tools and providers own their observable effects; their availability is not
permission to use them.

When a generic skill creator is also available, this skill remains primary for
capability boundaries, ownership, portable policy and behavioral evaluation; use
the generic creator only for supported structure or validation. Its absence does
not reduce this skill's semantic behavior.

Establish whether the request is creation, focused revision, consolidation,
retirement, or review only. Inspection and review do not authorize edits. Before
changing an existing skill, inspect its entry point, linked resources, live
callers, repository routing, applicable instructions, validation commands, and
working-tree state. Do not replace direct user changes or unique behavior merely
to make the skill resemble a preferred template.

Apply an authoritative, bounded correction directly. Treat an agent-inferred
lesson, or a change that widens activation, ownership, safety, compatibility,
effects or material cost, as a candidate until behavioral comparison distinguishes
it from the incumbent. One successful observation does not establish portable
policy.

Read [portable capability](references/portable-capability.md) before authoring or
revising skill policy. It defines the knowledge roles, force, authority, temporal
binding, consequence and availability decisions, plus the portability and
ownership rules that govern every skill. Apply those dimensions only when they
change placement, execution or evidence; they are not a required manifest.

## Develop the capability

1. Admit the intended requests, exclusions, outputs, authority, failure states,
   and observable quality claims. Reopen a material unresolved choice instead of
   hiding it in prose.
2. Preserve the smallest semantic and operational kernel that closes the claimed
   provider-independent behavior. Separate it from contextual policy, selected
   adapters and time-scoped evidence. Give each decision or effect one owner.
3. Choose the smallest complete structure. Keep the entry point focused on
   activation, governing behavior, and routing; add a resource only for a repeated
   decision, operation, validation obligation or delivered artifact that consumes
   it.
4. Author within the target skill and preserve the current project's authority.
   Bind paths, tools, versions, credentials, and providers only when the selected
   operation requires them.
5. Evaluate realistic behavior, inspect the actual artifacts and diff, and run
   repository-supported structural checks after the final edit. Report what the
   evidence establishes and any remaining limitation.

For creation, revision, consolidation, resource placement, or retirement, read
[authoring workflow](references/authoring-workflow.md). When the skill may install
dependencies, execute project code, disclose data, call a remote service, incur
cost, or mutate external state, also read
[external operations](references/external-operations.md) before specifying or
performing that operation. Before delivery, use
[behavioral evaluation](references/behavioral-evaluation.md) to test decisions and
effects rather than wording or template resemblance.

## Hard gates

- A self-contained simple skill stays simple; references, scripts, assets, setup,
  and compatibility layers require actual consumers.
- Without network retrieval, the claimed provider-independent core must still
  activate, decide, preserve its invariants, run its portable protocol, and name
  the exact unavailable adapter fact. This does not promise offline completion of
  work that intrinsically requires a remote service or missing tool.
- Portable behavior must not depend on this conversation, an installed authoring
  skill, a workstation path, a hidden runtime, or one provider.
- Examples and successful local observations may illustrate behavior but do not
  become universal policy without independent justification.
- Connected or installed does not mean authorized. Keep credentials out of skill
  files and disclose external effects before they occur.
- Review the actual result against intended activation, domain meaning, authority,
  compatibility, resource ownership, and evidence. Structural validation alone
  does not prove behavioral quality.
- Modify repository routing only when the capability is ready to become its named
  owner. Publication, installation, and unrelated cleanup require their own
  authority.
