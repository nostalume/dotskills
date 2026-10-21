---
name: document-artifacts
description: "Create, edit, inspect, extract, convert, or render native Microsoft Word, PowerPoint, and Excel OOXML artifacts—including macro-enabled and template variants—or Markdown, Typst, LaTeX, and PDF artifacts when physical format behavior matters. Also recognizes legacy Office formats for bounded conversion, and handles PDF OCR, protection, and forms."
---

# Document Artifacts

Own physical representation and format behavior, not domain conclusions.
Extraction consumes possibly unadjudicated sources; production consumes content
accepted by its research, software or business/data owner. Return a checked
projection or artifact with its limitations.

## Select the result and its route

Inspect project sources and conventions; preserve source format/layout by default.
Select operation and source variant once, before tools: OOXML documents/templates/shows
and macro-enabled variants, Markdown/Typst/LaTeX sources, analysis projections and
fixed-layout PDF have distinct preservation needs.

| Operation | Establish before action | Closure evidence |
| --- | --- | --- |
| Inspect | Source and requested information/page/region/feature scope | Located observations; no invented destination |
| Extract | Source, projection and coverage | Located content and unresolved scope; write only for a request or named consumer |
| Create | Accepted content and target format | Reopened output and requested fidelity checks |
| Edit | Current source, exact change, preservation set and output policy | Reopened source/output, changed scope and preserved features |
| Convert | Source, target, accepted losses and destination policy | Target opens/renders with declared losses; Markdown is not native editing |
| Render/validate | Source, target when rendering, fidelity and engine | Affected output states checked against the source revision |

Bind source/content to observed identities, revisions or digests. Establish the
postcondition, preservation set, accepted losses, trust and resource bounds
(pages/bytes/pixels/time/concurrency), and a nonempty subset of the fidelity classes
below. Writing needs a destination/overwrite policy; remote work needs explicit
authority. These are conceptual requirements, not schemas.

Read common obligations and only the selected branches:

| Selected work | Read before its dependent action |
| --- | --- |
| Producer depends on math, relations, table schema, references, media associations or nested layout | [Forward representation](references/representation-fidelity.md), before syntax/provider selection |
| Extract | [Located extraction](references/ingestion.md), before provider choice; the domain owner admits its evidence |
| Standalone PDF inspect/extract/create/transform/OCR/protection/forms | [PDF operations](references/pdf.md) |
| OOXML or legacy `.doc/.ppt/.xls` recognition/conversion | [Office](references/office.md): introduction and shared sections through **Apply format-specific requirements**, selected DOCX/PPTX/XLSX subsection, then **Match validation to the claim**; official references as needed |
| PPTX composition/revision/render/validation or tool selection | [PPTX selector](references/presentations.md#load-the-selected-pptx-path) |
| Markdown format work | [Markdown boundary](references/markdown.md) |
| Typst source/build/output | [Typst](references/typst.md): bind source, project-root, compiler, fonts, inputs, packages and outputs anew |
| LaTeX source/build/output | [LaTeX](references/latex.md): preserve project engine, class, packages and build graph; admit its compiler binding |
| Selected/requested MinerU hosted extraction/export | [MinerU](references/mineru.md): remote adapter, not editing/fidelity proof; check the destination format |

Typst/LaTeX-derived PDFs remain source-language builds; independent PDF edits use
PDF operations. Adapters/OCR/renderers/setup are conditional, not prerequisites.

For materially open chart, diagram, map, uncertainty or perceptual-hierarchy
choices, use an optional one-hop [visualization design](../visualization-design/SKILL.md)
handoff. If absent, preserve accepted content, report the open choice and do only
fixed container work. This skill retains native objects, preservation, rendering,
fidelity and delivery. Precise corrections, fixed conversions and settled
representations retain the accepted choice.

## Construct and check the artifact

1. Inspect the source read-only: structure, external dependencies and unsupported
   features determine the route to the requested result.
2. Construct the producer's meaning-bearing representation and containing regions
   before syntax. Bind headers, units, series and sources to shared accepted
   content; encode relations natively or declare losses. The fixed-chart PPTX
   [worked construction](references/presentation-design.md#worked-construction-one-source-two-native-objects)
   demonstrates object binding and defect diagnosis.
3. Resolve version-sensitive behavior from the specification/compiler/official
   documentation, not skill patterns. Choose the smallest producer/check graph
   that meets the postcondition in the current project's environment.
4. Before external libraries, CLI, MCP/API, multi-tool work, fallback or setup,
   read [execution](references/execution.md) for binding, effects, bounded retry
   and recovery. Already-proven tools retain authority/result obligations.
5. Give each effect one owner; use a distinct output unless in-place mutation is
   explicitly authorized. Reopen/compile/render the exact revision, report it and
   clean owned transient work.

| Fidelity | Evidence |
| --- | --- |
| Semantic | Meaning-bearing content matches the source: wording, values, formulas, citations and reading order |
| Structural | Native-aware reopening/parsing/compilation checks container, relationships, references, schema or structure |
| Visual | Declared-engine render checks affected pages/slides/sheets for overflow, fonts, geometry and images; not proof of meaning/structure |
| Accessibility | Check required reading order, native headers, alternatives, link purpose and redundant/nonvisual access; not inferred from appearance/export |

Use every applicable class. Skip unrelated costly visual work for semantic/
structural-only claims; missing tools/checks leave requested fidelity unmet.

## Admit effects before action

Selection grants no installation, upload, macro/embedded-code execution,
external-link retrieval, decryption, signature invalidation, overwrite,
reorganization or publication authority. Inspect/extract/review/validate grants no
editing. Use existing authorization; ask only for missing authority. Office's
admission/preservation checks precede parsing/mutation, including bounds, inactive
content and signatures.

Setup preserves project manager/versions and uses minimal authorized task-scoped
official commands; no implicit service/host change. If authority/capability is
missing, report the exact need. Before remote transmission establish credentials,
cost and retention as well as upload authority. Execution owns command bounds,
lifecycle and recovery.

Durable outputs/logs/manifests/projects/per-page material need a requested result,
named consumer, reproducibility or recovery. Reuse expensive work for unchanged
admitted inputs; corrected sources receive new identities and dependent checks. Remove
task-scoped scratch after verification unless requested or an observed regression
supplies a durable test consumer.

## Return the observed result

In the delivery report, return exact source/output identities/references,
available source maps/stable locators, checks performed/failed/skipped,
losses/unresolved regions, tool/provider identity and version, effects and
preserved source/recovery. Keep this execution record separate from the accepted
artifact content unless its reader contract requires it. Inspect authored or
changed body content, properties, comments, links and embedded resources for
incidental plan or workstation details; preserve required provenance and existing
content under the selected operation's preservation policy. Extraction, file
existence or opening alone proves neither completeness nor fidelity.

| Status | Meaning |
| --- | --- |
| `complete` | Every requested obligation passed |
| `partial` | Usable scope; identify each unmet obligation |
| `unavailable` | A required capability cannot currently execute |
| `refused` | Authority or policy disallows the operation |
| `cancelled` | Preserve cancellation and recovery state |
| `failed` | The request could not produce its result |

Distinguish malformed input, unsupported request, provider limitation, missing
binding, unauthorized effect, resource exhaustion and execution failure. Add
per-scope outcomes as needed without hiding refusal/cancellation in partial
success. Execution owns retry/branch behavior.
