---
name: system-mutation
description: Set up tools and local environments, register integrations, change host configuration, organize files with recovery, or migrate backups. Use for deliberate host or environment changes, not ordinary source edits, artifact creation, or tests merely writing files.
---

# System Mutation

Carry out the requested host change using existing tools and the smallest useful
procedure. Ordinary code and document edits stay with their respective skills.

## Route by host effect

Select the requested mutation before choosing a tool or procedure:

| Route | Required boundary | Closure evidence |
|---|---|---|
| Inspect/preview | target identity and read-only authority | observed current state; no mutation |
| Install/register | package or integration target, source, authority, and scope | consumer can use the selected installation or registration |
| Configure | exact setting owner and reversible change | effective configuration and preserved unrelated settings |
| Organize/migrate | source/destination, conflict policy, and recovery material | resulting layout plus recovery or rollback evidence |
| Backup/restore | source, destination, integrity, and retention policy | verified contents and post-state |
| Verify/reconcile | expected versus actual state | observed difference or confirmed match |

Read only the procedure selected by the route. A tool, hosted service, or
credential is an adapter for the admitted host effect; it is not permission to
perform that effect. Review and preview routes must not mutate.

## Inspect, act and verify

Identify the requested operation, exact targets, relevant existing state and
conflicts. Inspect only what can affect the decision. Preview and verification
requests do not authorize installation, repair, deletion or other unrequested work.

Keep an authorized direct local operation concise. When the selected route
downloads code or data, registers a provider, transmits task content, calls a
hosted service, incurs cost, or mutates remote state, read
[external integration](references/external-integration.md) and admit only the
external-edge concerns material to that operation. Local installation or
registration authority does not silently authorize disclosure, billing, remote
mutation, retention or publication.

Use authority already supplied by the user and session. Ask only for genuinely
missing permission or information. For an authorized direct operation, its command
and observed result can be the entire plan and record; no typed request, receipt
schema or custom runner is required.

Use the selected tool's official interface. Before a destructive operation, resolve
the actual target and preserve the recovery material the task requires. Refresh
identity immediately before acting when links, concurrent changes or remote state
could change the target. Keep secrets out of command text and reports.

Verify the requested end state, including the actual consumer when readiness is
claimed. A successful command alone may not prove it. Report material changes,
partial results and remaining limits briefly. Keep durable mappings or logs only
when needed for batch recovery, reproducibility or an explicit request.

## Recovery

After interruption, inspect what actually changed before retrying. Preserve useful
partial output and later user edits. Undo only recorded, still-identifiable effects;
do not infer ownership from a path name or old PID. Stop the affected operation if
identity or authority is uncertain. Describe irreversible effects honestly rather
than requiring a fictional rollback. Clean only owned disposable work.

## Read the relevant procedure

- Missing dependencies or a new task environment:
  [minimal project environments](references/project-environments.md).
- Installing or registering a CLI, local service, MCP server, API or hosted
  integration:
  [external integration](references/external-integration.md).
- File layout, conflicts, moves or undo:
  [file organization](references/file-organization.md).
- Platform/API details or implementing a PowerShell provider:
  [host adapters](references/host-adapters.md).
- Configuration edits or dotfile synchronization:
  [configuration](references/configuration.md).
- Backup transfer or verification:
  [backup repositories](references/backup-repository.md).

When implementing mutation software, use software-development for code and tests.
Exercise the specific failure/recovery behavior that software promises in disposable
fixtures. Running an ordinary command does not require building an adapter or
injecting failures into the user's host.
