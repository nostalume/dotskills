# Contracts and compatibility

This reference owns the **observable promise**: what callers can rely on and, when
live consumers exist, how that promise changes without an unplanned break. It does
not define internal value construction, effect ownership, or resource recovery.

## Define target behavior

Define the user operation before parser, transport, or implementation vocabulary.

For a CLI or process adapter, freeze:

- grammar, defaults, configuration/environment precedence, quoting, and `--`;
- working-directory, platform, packaged-executable, and secret behavior;
- stdout data, stderr diagnostics, and exit status;
- stable/versioned machine schemas;
- externally visible cancellation, timeout, partial-failure, and idempotency
  behavior.

For a library or protocol, freeze:

- accepted domains and legal externally visible transitions;
- error categories and preservation of source and target identity;
- sync/async behavioral parity without requiring representation parity.

## Evolve with live consumers

Activate this decision only when an incumbent system, peer, or supported consumer
must coexist with the change. Name the live consumers and supported versions,
compatibility window, cutover or rollback condition, and evidence that permits
removing the old path. Do not invent a compatibility layer without a consumer and
removal gate.

Schema shape belongs here only when externally promised. The value-boundary
reference owns how that schema is decoded into internal types.

## Durable tests

Test externally observable behavior, promised transitions, and
boundary/edge/failure semantics across real seams. Prefer black-box tests. Use
white-box tests only for a durable logical invariant that cannot be observed more
directly.

A test should survive an implementation rewrite that preserves the accepted
contract. Do not recursively test tests or freeze unpromised file layout, internal
fields, annotations, types, helper calls, or other ephemeral representation.
Static analysis and build tooling own structural and typing policy. A path or
schema field qualifies only when an external consumer is promised compatibility;
test its observable contract, not its implementation shape.

## Failure coverage

Test malformed input, unsupported variants, ambiguous dispatch, schema drift,
partial I/O, cancellation, incompatible peers, and compatibility expiry. Process
contracts require packaged-process smoke tests; library-only tests are
insufficient.

Hard gate: help, docs, parser, and schema agree; read-only operations remain
observably read-only; error and cancellation semantics survive wrapping; every
compatibility layer names a live consumer and removal gate.
