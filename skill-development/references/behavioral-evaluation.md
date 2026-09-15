# Behavioral Evaluation

Evaluate a skill as a decision-making capability. Frontmatter validity, resolved
links, expected headings, and familiar phrases are useful structural observations,
but they do not show that the skill activates correctly, preserves authority,
chooses suitable structure, bounds effects, or fails honestly.

## Derive evidence from changed claims

Freeze the intended capability and inspect the actual skill before selecting
checks. For every new or changed claim, identify the cheapest observation that
could show it is false.

| Claim | Distinguishing evidence |
| --- | --- |
| Activation and exclusion | Neighboring positive, negative, and ambiguous requests route to the correct owner for reasons grounded in requested behavior |
| Semantic and operational closure | Without network retrieval, the core still constructs the needed state, preserves invariants, runs provider-independent protocols, refuses safely, and identifies the exact missing adapter fact |
| Protocol and adapter separation | Replacing a provider or local tool preserves semantic states and completion/refusal rules while changing only the selected binding |
| Domain invariant or safety rule | Positive, boundary, failure, and adversarial cases preserve the rule and expose its refusal condition |
| Contextual judgment | Contrasting content or constraints produce appropriately different choices, with criteria tied to the request |
| Progressive structure | A simple case stays complete and small; a complex case adds only resources with named consumers and direct routes |
| Refactor or consolidation | Baseline behavior and callers are characterized; unique rules survive once; stale or competing ownership is removed only after cutover evidence |
| External operation | Data, authority, credentials, cost, bounds, commit semantics, verification, fallback, and recovery are resolved where applicable; no effect occurs in a policy-only test |
| Temporal adapter claim | Project version, compatible local interface, provider-current authority and relied-upon claim are reconciled; changed bindings invalidate only dependent evidence |
| Portability and absent capability | The claimed semantic, package, suite or runtime surface passes its distinguishing check; missing capability yields an equivalent alternative, bounded partial, unavailable or refused result without weakened invariants |
| Structural contract | The repository-supported validator, link inspection, metadata rules, and relevant static checks pass on the final files |

Do not use a large scenario count to compensate for an undefined contract. Do not
claim behavioral evidence from keyword matching, snapshots of prose, file count,
or validator success alone.

## Bound the affected skill set

Distinguish the runtime-advertised or revision-scoped **discoverable catalog**, the
**effective set** actually selected or handed off to for one request, and the
**evaluation neighborhood** affected by a change. References and tools are
dependencies, not skills.

An activation overlap requires one concrete admissible request that satisfies both
skills' positive conditions, or that one claims while the other claims, excludes
or hands it off. It is material only when selecting a different owner can change
responsibility, authority, effects, invariants, postcondition, evidence, failure
class or a named material cost. Shared words, tools, extensions or source domains
do not suffice. A conflict means both claim primary ownership, give incompatible
decisions, or lack a clear precedence or handoff; explicit cooperation with one
primary owner is not a conflict.

A one-hop neighbor has one explicit incoming/outgoing handoff or one demonstrated
material overlap with the changed skill. Follow another hop only when changing the
first decision can change that downstream skill's activation, authority, result or
cost. Establish the neighborhood by snapshotting the advertised catalog or
top-level frontmatter at a named revision, inspecting explicit skill handoffs, and
tracing fresh positive, neighboring negative and applicable handoff requests. Do
not infer it from the entire directory or semantic similarity. A catalog snapshot
records each advertised name and description plus its source/package identity and
revision or digest when the runtime exposes them. If selection or handoffs are not
observable, report only the static declared closure; do not claim an effective set.

## Enforce the evidence budget

Use the reach chosen by the authoring workflow:

| Reach | Required default evidence |
| --- | --- |
| **R0** | The changed claim; one discriminating positive and, when exclusion can change, one negative case; final artifact/diff and structural checks |
| **R1** | R0 plus one discriminating case for every demonstrated one-hop material neighbor |
| **R2** | R1 plus incumbent/candidate comparison for each motivating failure, previously passing behavior tied to each changed invariant, and every affected effect/refusal boundary |

Before adding a check beyond that minimum, name the changed claim or unresolved
conflict, the observable result the check could produce, and the acceptance,
scope, owner or failure decision that result would change. Without a distinct
decision delta, do not run it. Reclassify only the affected change when a new
observed contradiction, neighbor or consequence justifies broader evidence.
Missing required evidence is a blocker; unjustified expansion is a warning and
must stop before more execution.

Stop expanding when every changed claim has a distinguishing observation or named
unavailable check; every material overlap or changed handoff has one owner; every
decision-sensitive contradiction or unknown is resolved, locally bounded or
blocking only its affected claim; and no proposed next check has a distinct
decision delta. Passing tests alone do not establish this. For persistent conflict,
run at most the next bounded check whose possible results lead to different
decisions, then resolve, narrow, defer or block.

## Design forward cases

Use requests not copied from examples in the skill. Keep each case small enough to
inspect completely. A case should record:

- request and authoritative starting material;
- expected activation or exclusion and mode of work;
- granted and withheld authority;
- one condition that distinguishes a good decision from a generic template;
- expected equivalent, bounded-partial, unavailable or refused result and effect;
  and
- artifacts and state to inspect after the run.

Choose cases according to the changed boundary. A broad skill-development
capability should normally distinguish these families:

- a self-contained knowledge skill that should remain one concise file;
- a multi-operation skill with one genuinely conditional external provider;
- a focused revision that must preserve existing resources and unrelated behavior;
- a consolidation with overlapping triggers and unique rules in both sources;
- a review-only request that must report without editing;
- an offline, missing-tool, or missing-credential variant; and
- an ordinary software or artifact request that must not activate the skill.

Add domain-specific boundary cases when the skill makes stronger claims. For a
package-portability claim, copy the skill and declared included resources to a
disposable root, validate frontmatter and links, and confirm an absent external
skill produces its declared handoff or unavailability rather than hidden-path
dependence. For semantic portability, replace or remove one adapter while holding
the core contract fixed. For suite portability, exercise only the bounded
evaluation neighborhood.

For runtime/stateless portability, freeze the exact request, supplied material,
applicable project instructions and revision, advertised catalog, target skill and
declared sibling closure, plus granted and withheld tool/effect authority. Start a
new conversation or isolated evaluator that did not inherit the authoring turns;
supply only that bundle through normal discovery, without telling it which skill
must win. Record selection and handoffs, scope and authority, governing invariants,
operation, effects, result class, postcondition and limitations. Compare that
behavioral projection—not wording or reasoning order—with the contract, then
repeat only for the single mutation under test.

If a non-inheriting context is unavailable, perform static dependency and contract
checks, mark runtime portability unverified, and retain the runnable bundle only
while the task consumes it. Primary-agent self-review cannot establish this claim.

When knowledge placement or an evolving adapter changes, include the applicable
temporal mutations:

- omit one grammar/error/version rule from a self-contained DSL;
- reorder one safety-critical document or data-handling protocol step;
- remove a restricted audit's burden of proof, stop or reopen condition;
- evaluate pull-request feedback against a changed revision or location;
- hold the semantic core fixed while replacing a provider adapter;
- compare a project-pinned client with unversioned latest documentation;
- change provider target or policy after an otherwise reusable observation; and
- remove network access while distinguishing offline-capable preparation from an
  operation requiring fresh remote policy.

Change one semantic, temporal or availability input at a time. A useful case makes
only the corresponding decision, evidence requirement or bounded failure change.
Current structural validity and an old successful integration cannot satisfy a
changed operational or temporal claim.

## Inspect decisions and artifacts

For each case, trace:

```text
request and current authority
  -> activation and admitted scope
  -> role, normative force, authority and temporal-binding decisions where material
  -> semantic or operational kernel and selected adapter
  -> structure and resource selection
  -> any effect admission or refusal
  -> produced artifact and validation
  -> reported result and limitations
```

Inspect the complete output, not only its summary. Ask whether:

- the description separates the intended capability from adjacent owners;
- domain facts and project conventions retain their source authority;
- mandatory rules protect real correctness, safety, authorization, or
  compatibility rather than aesthetic or process preference;
- adaptable choices name the context that controls them;
- every reference, script, asset, setup step, and compatibility layer has a real
  consumer;
- provider-independent behavior remains operationally closed without mirroring an
  external specification;
- tools and providers are bound only on the selected route;
- reused or fetched claims retain their source authority, applicability, selected
  version or target, invalidation identity and consequence-appropriate freshness;
- unavailable capabilities and partial failures remain accurately distinguished;
- review or narrow-edit authority was not silently broadened; and
- the final response claims only what the observed checks establish.

Use contrast or mutation sensitivity where judgment might otherwise be cosmetic.
Change one meaningful input—remove network authority, introduce an existing
project convention, switch from private generation to public publication, add a
live legacy caller, or replace a skill request with ordinary code work—and confirm
that the decisions change at the corresponding boundary. Wording need not remain
stable; ownership, effects, and observable guarantees must.

Classify a finding as:

- **Blocker:** wrong activation, lost invariant, duplicated authority, hidden or
  unauthorized effect, unsafe/unbounded lifecycle, unsupported compatibility,
  untruthful result, broken structural contract, or missing evidence for a changed
  claim.
- **Warning:** maintainability, clarity, or contextual-quality concern that does
  not currently violate the capability; correct it or accept it explicitly.
- **Note:** non-gating observation or separately scoped improvement.

Correct local defects and rerun affected cases after the last edit. Reopen the
smallest governing decision when a failure changes intended scope, ownership,
compatibility, or effect policy.

## Close on the actual result

After behavior is satisfactory, inspect the final working tree including untracked
files and map every changed artifact to fresh evidence. Run focused cases first,
then repository-supported validation and static checks. Inspect links, resources,
generated artifacts, and any observable state rather than relying on exit status.

For a real external integration, record the exact target, pre-state, bounded
operation, stable identifier or receipt, post-state, cleanup, and residue. Skip
the call when it lacks authority; that skip can still validate the skill's refusal
behavior, but it cannot establish provider integration.

Delivery is ready when the final scope is identified, no blocker remains, each
changed behavioral claim has suitable fresh evidence, structural checks pass, and
warnings or skipped checks have an explicit disposition. Report exact observed
checks and their limits. Publication, installation, repository commits, and
external mutation remain separately authorized operations.
