# Structural migration

Use for modules, packages, crates, re-exports, CLI/library boundaries, features,
or other public topology.

## Inventory

Follow affected consumers and correctness dependencies through definitions,
entry points, serialized forms and package boundaries. Extend to manifests,
features, scripts, docs, targets or release metadata when they can change the move.

## Ownership

- Choose one owner crate/module/library for the coherent domain.
- Keep a CLI as a process adapter: parse typed input, call one domain operation,
  and render streams/status. Domain validation, decisions, state transitions, and
  reusable effects belong to the library.
- In Rust, separate behavior, resource/state, and external-adapter axes. Use static
  generics or associated types for compile-time composition; runtime policy belongs
  in adapters.
- A crate boundary needs an independent lifecycle, authority, security/protocol,
  or release reason. A feature needs a real optional capability and supported
  combinations, not preservation of an old layout.

## Transfer responsibility

Construct a useful connected slice in which the surviving owner performs the
work and consumers no longer maintain the displaced decision. Wire the active
path before removing its old implementation. Preserve accepted public behavior,
serialized forms and failure/resource obligations through coexistence and cutover.

Judge added transition code by the migration risk or coordination it removes and
the obligations it leaves behind. Keep a bridge for live accepted consumers with
a removal condition; adequate legacy paths outside the admitted slice can remain.

Complete the slice when its consumers use the surviving owner and displaced
authority is retired. Remove obsolete imports, aliases, configuration, scripts
and docs in that scope; full retirement requires no remaining live references.
Use the main workflow's checks for affected feature combinations, package contents,
docs, targets and MSRV/runtime obligations as applicable.
