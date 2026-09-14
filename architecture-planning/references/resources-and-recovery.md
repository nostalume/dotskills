# Resources and recovery

Use this lens only for bounded work and resource lifetime across success, failure,
cancellation, races, retries, or process death. General decision ownership belongs
to authority; public failure promises to contracts.

## Select the applicable lifecycle

Apply only the transitions the resource can actually enter; do not invent
reservation, publication, adoption, retry, or process-death states for a local
value whose lifetime is already closed by its language owner.

- Model only the applicable transitions among acquire/reserve, initialize,
  publish/commit, claim/adopt, and release/recover. At each failure, race,
  cancellation, or process-death edge the environment can actually produce, state
  the surviving resource and authority.
- Identify the durable record or protocol transition that proves commitment or
  ownership transfer. Allocator hints, pointers, indexes, and summaries are
  recoverable projections, not lifecycle truth.
- When ownership is genuinely single-consumer, express it with native linear,
  affine, move, borrowing, RAII, or typestate mechanisms when available. Otherwise
  use a guarded explicit state machine; unenforced convention is not lifecycle
  evidence.
- Separate behavior from geometry and physical representation. Preserve lifecycle
  invariants across architectures without coercing one ABI into another.
- A process-local allocator may supply blocks but cannot establish recoverable
  shared ownership. Isolate non-recoverable heaps.
- Distinguish transport adoption from application processing; do not silently
  redeliver after ownership transfer.

## Bounded ingestion and publication

Apply this section when the design ingests or publishes untrusted encoded
collections, archives, or path-bearing entries. It is not a universal resource
protocol.

- Treat encoded headers, filenames, lengths, and timestamps as untrusted hints.
- Enforce decoded-byte, entry-count, depth, memory, and time budgets while work
  occurs; reject absolute, drive, UNC, traversal, link, device, and conflicting
  archive targets unless policy admits them.
- Resolve containment at creation time where races matter. Stage privately on the
  destination filesystem with create-exclusive files.
- Publish only after complete validation using the strongest platform guarantee;
  document non-atomic fallback.

## Recovery

- Recover from durable lifecycle truth, never interrupted allocator/cache intent.
- Reclaim storage before reusing metadata that still identifies it.
- Preserve primary and cleanup errors. Retries require identity/generation and
  idempotency laws that prevent ABA, duplicate publication, or double release.

Hard gate: every selected resource lifecycle has bounded work and explicit
outcomes at its applicable edges; applicable publication is contained; and
recovery never depends on stale hints.
