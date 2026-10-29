# Authoring Workflow

Use for creation and revision; scale routing and effect contracts to the
capability. A precise one-file skill needs no ceremony.

## Establish the contract

Start from representative user requests and the observable result, not from a
directory template. Record only decisions that affect the artifact:

- intended requests and nearby requests that must remain elsewhere;
- whether the work is creation, focused revision, consolidation, retirement, or
  review only;
- result, quality claims, failure states, and any user-reserved choices;
- owners of domain facts, project policy, mutable state, and external effects;
- compatibility that a real caller or supported repository contract requires;
- evidence that can distinguish success from plausible-looking failure.

Inspect applicable repository instructions and routing before choosing the name.
For an existing capability, inspect its entry point and the resources, callers,
validators and history relevant to the proposed change. Treat
current source and direct user edits as evidence that can contradict an earlier
plan or example.

Choose a concise kebab-case name that describes the capability rather than its
implementation, provider, or temporary project. Write the frontmatter description
as a discovery boundary: say what the skill owns, when it should activate, and—if
confusion is likely—what adjacent work it does not own. Keywords alone do not make
the boundary discriminating.

## Close and place the knowledge

Apply [portable capability](portable-capability.md) to preserve an operationally
closed kernel: activate, construct state, choose/refuse, perform claimed portable
protocols and identify missing adapter facts without retrieval. This does not
promise offline remote execution or require copying external specifications.

Place knowledge by owner, temporal binding, consequence, availability and actual
consumer:

- Embed stable semantic definitions, invariants and operational protocols when
  omission changes safety, correctness, authority, compatibility or completion.
- Read accepted project facts and version choices from project-local authoritative
  sources rather than generalizing them into the skill.
- Fetch or probe provider-, platform- or version-specific detail at the selected
  adapter when it is large, uncommon, externally controlled or independently
  mutable.
- Use both sides for mutable high-consequence facts: embed the invariant and
  refusal behavior, then establish the current adapter fact before its effect.
- Keep observed evidence with the task or audit unless a named repeated consumer
  justifies a durable resource.

Reuse a fetched, probed or derived claim only while its source owner,
applicability, selected version or target, and invalidation identity remain the
same. Reobserve when consequence or drift makes freshness material. Do not impose
a universal time-to-live, refetch unrelated documentation, or create a mandatory
cache, claim ledger or documentation mirror. If authoritative evidence is
unavailable, stop at the exact affected claim and return the compatible core,
bounded partial result, missing decision or accurate unavailability.

## Design the smallest complete structure

Keep each invariant with its precondition, owner, required outcome, and honest
failure. Give contextual heuristics criteria and override conditions. Route
adapters only after their operation has been selected. Bind evidence to the claim,
source identity, selected bindings and conditions under which it was observed.

Choose resources by their consumers:

| Resource | Add it when | Do not add it merely because |
| --- | --- | --- |
| `SKILL.md` | Always; it owns activation, governing behavior, essential flow, and routing | A reference could repeat the same rules |
| `references/` | A conditional mode or specialized body of guidance would obscure the entry point | Multi-file skills appear more complete |
| `scripts/` | A named caller needs deterministic, repeatable execution or checking that prose cannot supply safely | Automation might be useful later |
| `assets/` or templates | A delivered artifact or operation actually consumes reusable source material | An example looked good once |

Prefer one direct link from the entry point to each conditional resource. Use
cross-skill links only as optional, one-hop handoffs for materially distinct
ownership; the referring skill must preserve its invariants, finish compatible
work, or report the missing capability when the other skill is absent. Avoid
required chains, cycles, hidden dependencies, and duplicated contracts. The README
may coordinate discovery, but each skill must work or stop honestly on its own.
Every durable resource needs a consumer and every route a trigger; an intrinsic
decision, operation, or check is also a consumer.

A command or mode needs a distinct postcondition, evidence, authority/effect,
durable artifact or refusal behavior; otherwise use a parameter. For each binding,
identify its operation, capability, effects, authority, verification, cleanup and
unavailable fallback. Convenience does not make a provider, launcher, hook or
bridge part of the core.

Define artifact exposure before persistence. Name the reader, purpose, destination,
source authority, and whether the artifact is private working state, project-local
shared material, or public documentation. For instructions to state or record
context, distinguish agent working inputs, task evidence and delivered content,
and name the destination when ambiguity could change the result. Admit context
into code or documents by the target contract or reader need, not merely because
it was available during execution. Keep plans and scratch in their working scope
unless the requested artifact itself needs that material and its exposure is
authorized.

## Trace the affected decisions

When a change makes ownership or dependencies unclear, trace the concrete request
through the affected guidance, project facts, tools/effects and result. Locate the
source of the ambiguity and correct its owning section. A layer sketch can help
resolve that question; it is not a prerequisite for every revision or a document
to maintain independently.

Select checks through [behavioral evaluation](behavioral-evaluation.md). A local
wording correction can be checked against its authoritative meaning and diff;
changing a decision needs a case that distinguishes its outcomes. Expand the
trace only where the change can alter a caller, effect or claimed guarantee.

## Author the constructive path

Center the positive construction: relevant objects/relations, how admitted inputs
become results, why consequential choices fit, and what establishes success. Ground
those choices in facts, explicit assumptions, mechanisms or inspectable derivation,
with criteria for choosing or changing the method. Explain non-obvious reasoning
that affects decisions; use examples to make the method usable, distinguish a
variant or demonstrate transfer.

Organize instructions along the reader's usable path through the capability.
For example, preserving source meaning can be made operational through source
positions, an explicit grouping identity, stable merging, and retained conflict
provenance; explain how those operations preserve the content. Choose the path
from the capability rather than imposing this sequence on unrelated work.

Attach conditions, limits, and failure behavior to the choice, action, or claim
they change. State a material boundary clearly at its owning location, before an
affected action when necessary, and continue compatible work. This gives limits
a concrete decision role while keeping the useful construction and its reasons
as the main content. Consolidate repeated caveats and omit generic disclaimers
that add no relevant information.

Write imperative instructions at the user's level of abstraction and use the
shortest complete explanation. Omit generic advice an agent already knows.
Examples clarify behavior rather than prescribe phrases to imitate. Judge the
content by its usefulness and support, not a word ratio or banned vocabulary.
Let the domain contract determine any mandatory intake form, fixed phase/file
count, or state artifact.

## Create a new skill

First check whether an existing owner should receive a focused extension. Apply
the contract, knowledge and structure guidance above, drafting the entry point
first. Validate links, selected resources, artifacts and behavior before changing
discovery; keep environment observations out of portable requirements.

Do not create a project, install dependencies, or call an external service just to
author prose. If a selected operation actually needs an effect, follow
[external operations](external-operations.md).

## Revise without losing behavior

Locate the requested change and characterize the affected current behavior,
including direct user edits and unique limitations. Preserve the force, owner and
context of still-valid content; establish obsolescence from actual use and evidence.

Apply an authoritative local correction directly when activation, ownership,
compatibility, safety and effects remain unchanged. If a boundary changes, inspect
its demonstrated callers or handoffs. If the proposal generalizes an inferred
lesson or changes consequential guarantees, retain the incumbent and compare a
bounded candidate on the motivating failures and affected invariants before
acceptance. The change's consequences determine this reach, not its file count or
a mandatory revision taxonomy.

Provider drift normally changes the affected binding, not the whole method. A
local observation remains scoped evidence until independent grounds or explicit
user policy warrants wider guidance. Use [behavioral evaluation](behavioral-evaluation.md)
for the checks and stopping condition; a routine correction needs no candidate
archive, experience ledger or staged workflow.

Make the smallest coherent change that satisfies the new contract. Preserve
unrelated wording and resources when they remain authoritative. A rename does not
authorize broader activation. A style edit does not authorize changing domain
meaning or effect policy. Review-only work reports findings and does not mutate
the skill unless fixes were also requested.

After editing, rerun the affected behavioral cases and structural checks. Inspect
all changed and newly created files; ordinary diffs may omit untracked content.
Search for stale links and activation text when ownership or names changed.

## Consolidate or retire skills

Consolidation is an ownership migration, not concatenation.

1. Inventory competing activation boundaries, unique behavior, resources, live
   callers, external references, and compatibility obligations.
2. Decide the target owner and map every still-valid rule and resource exactly
   once. Resolve contradictory policy at its governing owner.
3. Build and behaviorally validate the target before changing routing or removing
   an old owner.
4. Cut over discovery and live links together. Keep a compatibility alias only
   for an identified consumer, with a condition for removing it.
5. Search for stale names and inspect the final repository state. Remove only
   files whose ownership and replacement are established; preserve user changes
   and unrelated capabilities.

Do not leave indefinite overlapping discovery owners, a relay-only wrapper, or an
orphaned resource. If unique behavior cannot be placed without changing scope,
reopen that decision instead of silently dropping it. Retirement requires the
same caller and stale-reference evidence as consolidation even when there is no
replacement.

## Complete the work

Close through [behavioral evaluation](behavioral-evaluation.md) on the actual
artifacts and changed claims. Correct local defects; reopen decisions when a fix
changes capability or ownership. Report changed files/behavior, observed checks,
skips, blockers and limits. Publication, installation, commits and unrelated
routing changes require their own request authority.
