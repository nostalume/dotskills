# Implementation normal form

Use for settled changes under the [entry's development-loop trigger](../SKILL.md#development-loop).
This reference guides construction within the accepted constraints; the entry's
Admission owns unresolved governing choices.

## Construct for local reasoning and change

Where consequential uncertainty or construction resistance warrants investigation,
try a relation that lets several obligations follow from established facts and
keeps the change-sensitive decision with one owner. Connect its predicted consumer
result to actual dependency behavior, alongside the coordination it removes and
the change it makes local. Use these expectations to choose the expression.

Choose how to carry the relation by what must remain independent. Native values,
calculations and scopes may express it directly; a type or boundary can carry
independent state, policy, authority, lifecycle or meaningful variation. One
private consumer can justify such work. Favor an expression that lets consumers
forget implementation decisions while preserving their promised behavior.
Duplication may be cheaper than sharing distinct policy;
extra types may clarify real variants. Names and line count do not settle this
tradeoff.

Choose implementation guarantees together with their failure, waiting and recovery
costs under the accepted contract. Reusing a general mechanism imports its
guarantees and obligations; weigh stronger semantics by the consumer benefit or
consequential failure that repays their cost. Preserve required guarantees; a
change to a governing promise, owner or budget returns to Admission.

Trace admitted input to the promised result: select its operation, transform
meaning-preserving values, invoke effect/resource owners, then return or delegate
after owed work. Give transformations explicit results or failures, compute costly
intermediates once, and retain genuine trust boundaries and variants.

## Preserve terminal handoff

Terminal delegation means the current owner has no remaining semantic obligation
after calling the next owner. Return or transfer that result directly, preserving
its failure, cancellation and resource handoff. Do not add a relay variable,
wrapper, callback, conversion, handler, or `await` solely to relay the same
outcome. Retain such machinery when the current boundary owns observation,
translation, cleanup, supervision, or other work after the call.

When a proposed helper only calls a method or operation on the value that already
owns it, with the same admitted input and outcome, remove the helper and delegate
directly. This is not a universal preference for methods: retain a free function
for an operation that belongs to no receiver or owns a reusable pure algorithm,
and retain a wrapper for a real adapter, policy, translation, lifecycle or
compatibility boundary.

This is not a universal demand for compiler tail-call optimization. Use an actual
tail call only when the language/runtime makes it sound and useful. Recursive
domains, parsers, graph traversal, concurrent fan-out/fan-in and explicit state
machines may not look syntactically linear; keep their transitions, joins,
cancellation and terminal states locally visible instead of flattening away their
meaning.

## Put handlers only at decision owners

An exception handler, result-error mapping, fallback branch or retry boundary is
justified only when this exact owner can do at least one of these:

1. recover through a bounded accepted domain or project policy;
2. translate into its settled public/domain error contract while preserving the
   original cause and relevant source/target identity;
3. compensate or roll back an effect it owns;
4. release an owned resource while retaining both primary and cleanup failures; or
5. add context required by a real consumer that is not already available.

Otherwise propagate unchanged. Remove catch-log-rethrow, catch-wrap at every
layer, broad fallback, and handlers around unrelated work. Do not turn
cancellation into ordinary failure or absence, replace a specific cause with a
generic message, duplicate diagnostics at every layer, retry an uncertain effect
without its idempotency/observation rule, or continue after a partially committed
operation as if nothing happened.

Prefer lexical or language-native cleanup such as RAII, scoped guards, `defer`, or
`finally` when cleanup is the only obligation. When cleanup can also fail, retain
the primary failure and make cleanup failure observable according to the settled
contract. Expected domain alternatives and unexpected faults may use different
project-native mechanisms; do not convert everything to exceptions or everything
to result values merely for visual uniformity.

## Keep effects, resources and work owned

Keep deterministic decisions separate from I/O, clocks, randomness, logging,
persistence and host/external capabilities when the accepted design distinguishes
them. Invoke each effect through its named owner and inspect the required receipt
or post-state. Do not hide a global effect behind a pure-looking helper or create
another adapter that only relays the existing one.

Implement the settled acquire/reserve -> initialize -> commit/adopt ->
release/recover lifecycle using native ownership, scopes or explicit states.
Children may not outlive their structured owner unless a named service adopts and
supervises them. Bound queues, concurrency, retries and caches at the owner able to
refuse or defer work.

## Worked relationships: a cached FTP Link

Suppose callers borrow a cached Link across requests. The instance owns the Link
lifetime, and a read belongs to both that borrowed lifetime and its own request.
Use the project's existing reference ownership to revoke the Link on final
release, and the read scope to revoke only its acquired IO. This relation can
generate admission, cancellation and cleanup together, without a second reference
counter or separate per-method revocation policy. A waiting caller owns no shared
connection yet: cancellation ends its wait; transport interruption belongs only
to the operation that acquired the connection.

Counterexample: equal request contexts do not establish shared IO ownership, and
releasing one borrower does not establish final release. Initializing, disconnected
and revoked instances are different states even when all lack a connection.
Keep those distinctions; deducing every state from `conn == nil` erases behavior.

Revocation, socket interruption and observed errors also have different timing.
A socket-close callback may run before a merged request context is canceled. The
captured owner supplies the revocation fact; transport closure performs the IO
effect. Stopping/joining the operation callback before handing off a reusable
connection prevents that old operation from interrupting its successor.

These examples illustrate derivation, not a prescribed class layout or universal
cancellation policy. Inspect actual borrower and release contracts; preserve
protocol completion, cleanup faults and cancellation identity where they matter.

## Preserve settled boundaries

For a material topology change, follow affected callers and value/resource
dependencies through owners, visibility, compatibility and project-native module
edges. Preserve the settled graph and examine whether the relevant change stays
local. Obvious private relay removal remains local when no obligation disappears;
a new governing owner, dependency direction or public surface returns to Admission.
