# Module Topology

Use this lens during architecture planning when a proposal materially changes a
conceptual or physical owner, dependency, visibility, facade, or re-export. It
owns the design-time projection into helpers, types, modules, files, directories,
packages, and namespaces. Domain, authority, representation, contracts, resources,
and cost retain their own decisions. An obvious implementation-local relay cleanup
belongs to `software-development`.

## Project the semantic graph

```text
accepted domain capability and vocabulary
  -> invariant, policy, authority, effect, or lifecycle owners
  -> admitted dependency and translation edges
  -> visibility and compatibility surface
  -> smallest project-native physical projection
```

For each proposed node, name the distinction it owns, its consumers, permitted
incoming/outgoing dependencies, and whether it is private, public, generated,
platform-specific, or transitional. Claim independent change locality only from
current callers, maintained history, or an accepted change model.

Cycles, reciprocal imports, broad re-exports, and repeated cross-boundary access
are signals to recheck ownership, not automatic reasons for another layer. Split
one owner only when doing so preserves a clear dependency direction or isolates a
real authority, lifecycle, compatibility, security, or variation.

## Make every boundary pay semantic rent

A boundary is justified when it owns at least one distinct domain invariant or
policy; authority/effect admission or representation translation; resource,
concurrency, or recovery lifecycle; public/security/protocol/compatibility surface;
reusable pure algorithm or real variation for coherent consumers; or evidenced
independently changing unit.

Line count, indentation, lexical prefix, symmetry, mock convenience, possible
future reuse, one call site, or preferred file size do not earn a boundary. A
helper that only forwards an operation to the value already owning it is not a new
semantic node. Retain a free function when no receiver owns the operation or it is
an independent pure algorithm; retain a wrapper when it owns policy, translation,
lifecycle, compatibility, or an adapter.

## Select the physical projection

Apply enforced project and language rules, then choose the smallest projection
that preserves owners and edges:

- keep one cohesive owner together when internal names need no boundary;
- group a parent namespace only when it owns multiple meaningful children and
  controls their internal/public edges;
- keep prefix-flat siblings when they are semantic peers or project policy makes
  that relationship clearest;
- isolate generated, platform, protocol, policy, security, or compatibility units
  only for their independent source/lifecycle/consumer; and
- add a facade or re-export only for a supported surface or live migration
  consumer, with a removal gate when transitional.

Mix grouping styles only when the difference encodes a named semantic, visibility,
platform, or enforced project distinction. Repository analogues constrain the
choice only when their domain, lifecycle, visibility, and dependency conditions
match.

## Falsify candidate topology before handoff

Inventory relevant definitions, imports, visibility, callers, tests, public
surfaces, project rules, and matching analogues. Draw only the semantic nodes and
edges needed for the decision; no durable module map is required.

Run only applicable design counterfactuals: replace a proposed helper with direct
delegation to its owner; inline/merge a candidate file; collapse or group its
namespace; move a symbol beside the invariant or lifecycle it uses; add the next
admitted variant or coherent consumer; remove a compatibility consumer; or trace a
representative accepted change. Reject a boundary when its removal loses no owned
obligation, edge, visibility rule, compatibility surface, or evidenced independent
change unit.

Settle the conceptual owners, permitted dependencies, visibility/compatibility
surface, and project-native projection. Ask the user only when multiple conforming
projections retain a material project/product tradeoff. Hand these constraints and
the relevant design falsifiers to `software-development`; its implementation
normal form owns actual-diff counterfactuals and may remove an obvious local relay.
Reopen topology only when the diff exposes a materially selectable owner, edge,
surface, or change-locality premise absent from the decision.

Hard gate: every material boundary has one semantic owner, admitted dependencies,
and a justified visibility or compatibility surface; the smallest conforming
project-native projection survives design counterfactuals without relying on file
size, prefixes, pattern fashion, or user correction.
