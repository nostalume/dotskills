# Minimal project environments

Use the task's project root and existing tools first. For a new artifact, establish
its working directory beside the intended sources and outputs; the installed skill
directory is not the artifact project. Inspect manifests, lockfiles, environment
directories, available executables and user instructions before choosing setup.
Check whether a discovered command is a manager shim: even `--version` can trigger
acquisition. Inspect its manager configuration or installed payload first when so.

Follow the user's selected manager and installation route, including aqua for
uv, Node, Bun or Deno. Otherwise prefer a simple official, supported installation
method for the selected platform. Acquire only missing tools and dependencies.
Use the manager's commands directly. Do not generate a bootstrap script, managed
environment registry, process supervisor or installation wrapper for routine setup.
If an installation script is needed, explicitly tell the user its source, purpose
and effects before executing it; obtain any missing authority. A request for a
custom setup script is a separate deliverable. Existing setup authority remains valid.

Isolate project dependencies when compatibility requires it; preserve a suitable
existing environment. Reuse the selected tool's configured/native cache and
installed compatible runtimes. A new task, chat or working directory alone does
not justify another environment, private cache or runtime copy. Use a private cache
only for an explicit disposal, security or verification boundary. Moving a cache
does not address repeated acquisition or unbounded retention.

Scope required environment overrides to the command or task session. Avoid global
package installs, profile/PATH changes, and changes to another application's
environment. Respect user-selected shared storage. Acquire a missing runtime
through the selected manager within the authorized scope; do not copy it into
every task. Check tool-specific browser/model/font downloads separately.
OS-managed fonts, profiles and temporary writes may follow provider-specific
rules; inspect relevant effects rather than inventing a containment wrapper.
Keep observed executable paths, installed versions and machine-specific failures
in task evidence. Reusable instructions use portable inputs and conditional
provider requirements; rediscover bindings in each destination project.

## Select the smallest setup

| Existing state | Action |
| --- | --- |
| Suitable project with dependencies ready | Run the selected operation; no setup |
| Installed runtime/standard library can perform the operation | Invoke it directly; no project or environment initialization |
| Project exists but a dependency is missing | Add or sync through its manager and preserve its constraints |
| Third-party dependencies need an environment and none is compatible | Create the smallest environment through a suitable manager; uv for Python or Deno for compatible JS are useful defaults |
| Required runtime or manager is missing | Acquire only the proven missing capability through the user's route or an official supported installation; create an environment only if the operation needs one |
| Node, Bun or another runtime is required by the project/tool | Use that runtime and its local dependency workflow; do not migrate it solely to use a default |

## Direct command examples

These are alternatives for a new task root, not a sequence to run everywhere.
Check installed help and current official documentation before use. Preserve an
existing manifest; initialize only when needed and absent. Keep manifests and locks
with the source, and ignore generated environments and caches in version control.
Angle-bracketed values below are consumer-supplied placeholders, not literal shell
arguments or dependency choices made by this setup reference.

For a new Python project that requires third-party dependencies, reuse a compatible
Python and uv's selected cache. If Python is missing, use the admitted installation
route and the installed version's options to avoid unintended executable
registration or PATH changes. A minimal new project can use:

```sh
uv init --bare
uv add <python-dependency>
uv run python <entry.py> [arguments...]
```

uv owns `.venv`, `pyproject.toml` and `uv.lock`. A one-off dependency-bearing
operation that cannot use an existing compatible environment can instead use
`uv venv .venv` and
`uv pip install --python <venv-python> <python-dependency>`, then invoke that
interpreter directly. Use `.venv/bin/python` on POSIX or
`.venv/Scripts/python.exe` on Windows. See the official
[project workflow](https://docs.astral.sh/uv/guides/projects/) and
[environment settings](https://docs.astral.sh/uv/reference/environment/).

For a compatible Deno project, preserve its selected cache and keep `deno.json`
and `deno.lock` with the source. If a dependency is missing, add only that dependency:

```sh
deno add npm:<js-dependency>
deno run <required-permissions> <entry.mjs> [arguments...]
```

Run the project source with the file/environment permissions its dependencies
need. Verify the actual operation; a Node example is not automatically a tested
Deno example. If local `node_modules` is needed, use Deno's documented
`nodeModulesDir` setting. See official
[Node/npm compatibility](https://docs.deno.com/runtime/fundamentals/node/)
and [environment variables](https://docs.deno.com/runtime/reference/env_variables/).

For an existing Node/npm project, a direct `npm install <js-dependency>` uses the
project manifest and local `node_modules`; invoke `node <entry.mjs> [arguments...]`
afterward. Preserve its configured/native cache. Follow the corresponding
native workflow for a user-selected Bun or other manager. The consuming capability
selects dependency names, versions, entrypoints and permissions; this setup owner
must not choose them on its behalf.
Official acquisition guidance: [uv](https://docs.astral.sh/uv/getting-started/installation/),
[Deno](https://docs.deno.com/runtime/getting_started/installation/),
[Node](https://nodejs.org/en/download).

## Resume and verify

After setup, run the requested author/edit/render operation and inspect its output.
That real operation can establish readiness; a separate generic probe is optional.
Keep setup separate from artifact helpers so ordinary edits never reinstall tools.
Report material installed components and locations briefly; no receipt protocol
or separate JSON manifest is needed for a routine direct command.

Project dependency isolation does not sandbox arbitrary code or all OS writes.
Inspect the selected tool's actual storage and execution behavior before claiming
containment. Before creating resources, distinguish their lifetimes:

- Keep source, manifests, locks and a maintained project environment for its named
  consumer and subsequent revisions; compatible connected work shares that owner.
- Remove owned one-off verification environments and scratch after their checks
  and required evidence are complete. On failure/cancellation, stop owned work and
  retain useful recovery material; directory names alone do not establish ownership.
- Retain installed runtimes and shared caches under their tool/user policy.
  Creating an environment grants no authority to purge shared caches.

For a selected shared-cache maintenance request, use
[cache maintenance](cache-maintenance.md). Ordinary setup and artifact work do not
scan shared caches, create maintenance hooks or register environments.
