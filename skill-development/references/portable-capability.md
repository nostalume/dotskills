# Portable Capability

A portable skill preserves the knowledge and operations needed for its declared
work while binding context-dependent means where used. Start from concrete
constructions: identify which distinctions and operations produce the result, and
what survives a relevant change of context. A shared abstraction earns reuse by
preserving those uses; its limits can require changing the abstraction itself.
Portability concerns the surface actually promised, not identical organization
across domains or support for every tool.

## Classify knowledge without flattening it

Use these orthogonal dimensions only when they change placement, execution or
evidence; they are reasoning aids, not a required manifest or directive schema.

| Dimension | Representative values | Governing question |
| --- | --- | --- |
| Role | semantic model, decision policy, operational protocol, adapter, evidence | What work does the knowledge perform? |
| Force | invariant, conditional requirement, heuristic, example | How strongly must it govern when its precondition holds? |
| Authority | user, domain or standard, project, provider or tool, derivation, observation | Who can make or change the claim? |
| Temporal binding | intrinsic, project-version-bound, provider-current, request-ephemeral | What identity or event can invalidate it? |
| Consequence | explanation, correctness, safety, compatibility, mutation or external effect | What happens if it is absent, wrong or stale? |
| Availability | embedded, project-local, probeable, fetchable, unavailable | Where can the selected operation establish it? |

A semantic model supplies the domain objects, relations and legal operations.
A policy chooses among alternatives; an operational protocol supplies a grammar,
algorithm or checking sequence whose order and completion matter. An adapter
binds it to a project, tool or provider. Evidence supports only what its method and
scope establish. A proposal remains provisional until adequate grounds support
its consequential use.

Keep domain constructions, derivations, grammar and failure semantics when they
are needed to perform the capability. For example, a self-contained language skill
needs enough syntax and grouping rules to produce valid source; replacing them
with generic advice to consult an adapter leaves the method incomplete.

State a rule with its actual applicability and force. Domain or interface
requirements govern where they hold; a useful house convention or local success
can remain contextual. When new cases defeat an abstraction, recover what its
successful uses depended on and reconstruct that relation before adding branches.

## Preserve owners and boundaries

- The user owns intent, reserved choices, authorization, and acceptance of taste.
- The skill owns its activation boundary, portable decisions, and declared
  quality contract.
- The domain or source owner owns facts and accepted content.
- The current project owns local instructions, formats, dependencies, and adapted
  resources.
- A selected tool or provider owns its execution semantics and effects. The skill
  must admit those effects but must not pretend to control what it cannot verify.
- Validators prove only the structures and rules they actually inspect.

Admit untrusted input at its boundary. Make decision triggers, variants and
failures explicit, with one accountable owner for each rule or effect. A
cross-skill reference is an optional, one-hop handoff at a real ownership
boundary—not a core prerequisite. Without the other skill, complete compatible
work or state the missing capability and safe result; do not copy its full policy.

## Keep the operation surface economical

Define operations by their result, evidence and authority/effect boundaries.
Reuse shared decisions across synonymous requests; introduce a distinct operation
when those boundaries differ. Native commands or entry points can retain their
interfaces while consuming a common method. Tone, selector or naming differences
alone need no new mode.

Select tools for the operation and declared scope. A provider-specific capability
may retain its provider knowledge; an authoring-machine path is contextual.
Bind an adapter's inputs, effects, authority, bounds, verification, recovery and
unavailability before its use. Connected tools remain dormant until needed and
authorized.

Treat automatic hooks, background watchers, and setup commands as external
operations, not harmless conveniences. They require an explicit consumer,
authority, bounded lifecycle, and post-observation. A policy-only or planning path
must not invoke them.

Persist context only for a real reader and maintenance consumer. Keep plans,
scratch reasoning, credentials, runtime state, and private evidence in their
private scope. A tracked or public-facing artifact needs an identified audience,
purpose, destination, exposure decision, and source-authority check; repository
paths and ignore rules do not grant publication authority. Never copy a plan or
unnecessary project inventory into a durable public document merely because a
tool can write it.

## Keep the core environment-neutral

Write the semantic core in terms of required capabilities and observable results:
for example, "render the final source and inspect representative pages," not "run
the renderer at a particular workstation path." Reuse a suitable current project
and its selected tools. Resolve manifests, paths, versions, platforms, credentials,
models, endpoints, and provider-specific limits only for the operation that needs
them.

A tool or provider dependency can belong to the declared capability; rediscover
its installation, credentials and target bindings where needed. A cross-skill
handoff states its trigger and unavailable path without hidden chains or cycles.
Portable behavior cannot silently rely on the authoring machine or mutate the
installed skill during use. Bind network-dependent operations explicitly and keep
adapter-specific guarantees within their actual scope.

Name only the portability surface actually claimed:

- **semantic:** the capability's activation, invariants, decisions and result
  meanings survive replacement of a local adapter;
- **package:** the skill and its declared included resources can move as one unit,
  with external skill dependencies explicit rather than hidden paths;
- **suite:** discovery and handoffs preserve one owner when the skill participates
  in an advertised collection; and
- **runtime/stateless:** a fresh invocation can recover the governing behavior
  from declared inputs and dependencies without prior conversational memory.

These claims are independent. Provider-neutral prose does not prove an isolated
package, and a valid package does not prove discovery or fresh-context behavior.
Use [behavioral evaluation](behavioral-evaluation.md) for the distinguishing
observations.

For a claimed provider-independent core, offline inspection must still support
activation, the necessary domain construction, choice/refusal and the portable
protocol it promises. Name the exact unavailable adapter fact. A compiler or
remote service can remain necessary for the dependent operation; preserve work
whose claim does not need it.

An alternative is equivalent only if it preserves the postcondition and evidence.
A bounded partial names each unmet guarantee; unavailable means no useful declared
subset can be established; refused means authority or policy prohibits it. Resolve
material missing decisions without weakening authorization, identity, safety or
mutation boundaries. Missing evidence cannot be replaced by fabricated success.

## Add structure progressively

Keep a self-contained skill in one file when its method fits. Add a reference for
a conditional method that would obscure the entry, a script for actual repeatable
execution/checking, or an asset for delivered work that consumes it. An intrinsic
selected operation can be the consumer; a hypothetical future use is insufficient.
Each resource retains an owner and an applicable verification obligation. Keep
direct routes to conditional guidance and remove orphaned or duplicated ownership
when its replacement is established. Examples explain choices, not file layouts.

Before promoting guidance, establish what it protects, where it applies, who
owns it, what can invalidate it and what observation could defeat it. Keep a useful
local method local when wider support is absent. These questions resolve actual
decisions; they need no classification worksheet or extra record.
