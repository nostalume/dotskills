# Cache maintenance

Use this route for a selected cache inspection, cleanup or authorized maintenance
run. The entry owns host authority and recovery. Artifact/software/release owners
retain their own temporary resources; this route owns selected shared tool caches.
Review or policy design is read-only. Authoring these instructions installs no
executor and grants no recurring deletion authority.

## Select targets and policy

Resolve the installed tool, version, effective cache configuration and actual
target identity before measuring or deleting. Inspect manager shims before invoking
even discovery commands. Restrict work to explicitly selected caches; recheck
resolved paths/links before effects. Unknown identity yields a bounded partial
inspection or deferred cleanup, not a wider search or recursive-delete fallback.

Keep project source, locks, deliverables, existing project environments, installed
runtimes, browsers, models, credentials and recovery evidence outside the cache
target unless separately selected with their own lifecycle/authority. A cache name
does not establish that its contents are disposable or available offline again.

For recurring maintenance, bind the user's target allowlist, soft size budgets,
free-space threshold, check interval, idle condition, full-purge cooldown and allowed
escalation. These are host policy, not universal skill defaults or hard quotas.
Include rebuild/download cost and offline retention needs. Reuse existing authority;
missing cleanup authority permits inspection only. Scheduling is a separate effect.

## Check, defer, clean and observe

1. For an explicit inspection, observe only its requested scope. For an authorized
   maintenance run, check cheap disk free space and last-run state first. If not
   due and not under configured disk pressure, return before recursive size scans.
   A pressure trigger bypasses the time gate, not authority, exclusions or locks.
2. When due/under pressure, measure only selected caches. Below policy thresholds,
   keep reusable content. Do not rescan every project or enumerate the whole home.
3. Before cleanup, serialize maintenance for the same target and establish the
   tool's safe maintenance window across users/sessions that can access it. Honor
   native locks with bounded waits. Busy or uncertain use defers cleanup; never kill
   unrelated processes or force past locks. A maintenance mutex alone does not
   exclude builds, and a process-name check alone does not establish exclusivity.
4. Use the version-compatible native prune/clean operation for that exact cache.
   Start with supported narrow/unused-entry cleanup unless a full purge was
   explicitly requested. A direct purge uses its granted scope; recurring purges
   follow the selected escalation and cooldown policy. Missing tools,
   acquisition-triggering shims or unresolved command effects yield
   unavailable/deferred results; do not install,
   upgrade, bypass policy or manipulate shared-cache internals to make cleanup run.
5. Observe post-state and disk free space as well as command outcome. Hardlinks and
   concurrent writes can make apparent cache bytes differ from reclaimed space;
   report the observation's limits. Bound attempts; reconcile partial effects
   before retrying and do not claim quota compliance from a successful command.
6. In recurring maintenance, if a full purge is followed by rapid regrowth within
   its cooldown, defer another routine purge and identify repeated setup,
   version/source churn or duplicate builds. Notify once per actionable condition.
   Any emergency cooldown override
   must already be in the selected policy; continued pressure is not permission
   for repeated purges or expanding targets.

For a direct command, its observed result may suffice. An authorized recurring
executor needs only bounded per-target last-check/cleanup times and latest outcome,
including deferral/failure and notification state. Do not build an environment,
package or task registry. Successful background checks stay quiet; surface
unresolved pressure, persistent failure or rapid regrowth. Explicit requests still
receive their result. A policy file does not itself provide background execution;
add an executor/hook only for a requested consumer with bounded lifecycle.

## Bind Go or uv at the edge

Establish installed-interface compatibility and the authoritative behavior needed
for the selected command. Reuse matching evidence; if offline or version skew
leaves cleanup effects uncertain, return inspection and the exact missing fact.
Go and uv share the protocol above, not interchangeable deletion semantics.

| Adapter | Native maintenance | Limits and retained boundary |
| --- | --- | --- |
| uv | Prefer `uv cache prune`; `uv cache clean <package-name>` targets a selected package; `uv cache clean` is a full purge | Resolve the effective cache (`uv cache dir` when safely available) and scope the invocation to it. Prune is not a byte quota; versions may also remove centralized project environments. If those environments would be affected, require their explicit inclusion/recreation policy and a safe idle window or defer. Respect native cache locks and bounded waits; do not use `--force` or directly remove shared-cache files. |
| Go | Retain native age-based trimming; for an over-budget build cache, `go clean -cache` is the full-purge escalation | Resolve `GOCACHE`/`GOCACHEPROG` through configuration and, when safe, `go env`. An external cache program needs its own supported adapter; do not treat it as a local directory. Require a safe idle window for the selected cache. `-cache` is not selective LRU eviction and incurs recompilation; do not substitute `-testcache`, `-fuzzcache` or `-modcache`. Module-download/fuzz caches and offline dependencies require separately selected policy. |

Current authorities: [uv cache behavior](https://docs.astral.sh/uv/concepts/cache/),
[uv CLI](https://docs.astral.sh/uv/reference/cli/#uv-cache),
[Go cache behavior](https://pkg.go.dev/cmd/go#hdr-Build_and_test_caching) and
[Go clean](https://pkg.go.dev/cmd/go#hdr-Remove_object_files_and_cached_files).

For another tool, preserve the target/authority/idle/verification protocol and
establish its supported cleanup interface before acting. Moving caches or
disabling caching does not resolve unnecessary setup or repeated work.
