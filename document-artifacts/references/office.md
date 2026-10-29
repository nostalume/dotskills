# Native Office artifacts

Read this reference for Word, PowerPoint, or Excel OOXML-family inspection,
extraction, creation, editing, conversion, or rendering, and legacy Office
recognition/conversion. The routed package families include the following common
document, template, and show variants:

| Family | Macro-free packages | Macro-enabled packages |
| --- | --- | --- |
| WordprocessingML | `.docx`, `.dotx` | `.docm`, `.dotm` |
| PresentationML | `.pptx`, `.potx`, `.ppsx` | `.pptm`, `.potm`, `.ppsm` |
| SpreadsheetML | `.xlsx`, `.xltx` | `.xlsm`, `.xltm` |

This table is an activation and safety route, not a claim that one library can
edit every variant. Add-in packages such as `.xlam` and `.ppam`, binary `.xlsb`,
and producer-specific extensions require their own exact capability proof; they
still receive active-content and container recognition before any operation.
It owns shared OOXML package mechanics and
format-specific fidelity checks. It does not own document meaning, business
analysis, provider installation, or a default visual style.

For PPTX creation and visual revision, use the conditional recommendations and
composable resources in [presentations](presentations.md). Choose authoring,
editing and rendering by their separate feature contracts below.

## Admit the requested capability

Freeze format, operation, required fidelity set, preservation-critical features,
accepted losses, and output before selecting a mechanism. Then verify the selected tool
against the applicable row:

| Operation | Binding must prove | Completion evidence |
| --- | --- | --- |
| Inspect/extract | Observe every requested meaning-bearing feature without mutation | Source identity, feature inventory, requested values/structure, unresolved regions |
| Create | Produce the target format and requested features | Reopened output plus semantic/structural checks |
| Edit | Mutate the requested feature and preserve every declared invariant | Preserved source, distinct reopened output, before/after checks and named losses |
| Convert | Produce the declared target under an accepted loss model | Source/target identities, mapped content, explicit omissions and target validation |
| Render | Render the exact admitted artifact with the required fonts/layout inputs | Engine identity plus inspected pages, slides, or sheets |

A mechanism usable for one row or feature is not a general Office binding. Return
`unavailable` when no live binding can satisfy the postcondition. Return `refused`
when the requested mutation conflicts with trust, signature, active-content, or
preservation policy. Never replace a native edit with a Markdown/CSV projection or
reduce visual fidelity because a renderer is absent.

Choose the applicable feature row as well as the operation row. Their intersection
defines the required capability; the examples below are not an installed-tool list.

| Format / operation / feature | Portable mechanism requirement and limitation | Checks and loss boundary |
| --- | --- | --- |
| Word-family inspect/extract: stories, revisions, nested tables | Reader exposing requested body/header/footer/comment/revision parts; basic paragraph collections are incomplete | Compare requested source parts and locators; omissions remain unresolved |
| Word-family create/edit: styled runs, fields, comments | Native producer that edits the exact document/template variant while retaining the relevant relationships and untouched content | Reopen and compare text, run formatting, anchors/fields and relationships; render when visual fidelity is required |
| PowerPoint-family inspect/extract: slides, notes, masters | Reader observing existing presentation/template/show identities and notes without creating parts | Check order, notes presence, inheritance and source locators; reading order is not automatically shape order |
| PowerPoint-family create/edit: text, shapes, media | Producer supporting the affected feature and exact package variant while preserving layout/master/media relationships | Reopen and compare identities, geometry, z-order and values; animations or unsupported embedded content need their own proof |
| Excel-family inspect/edit: cells, formulas, cached values | Workbook/template reader/writer retaining requested types, formulas, formats, merges and relationships | Reopen formula and cached-value views separately; a cache is not recalculation |
| Excel-family create/edit: fresh formula results | Compatible calculation engine for the exact formulas and inputs, without unauthorized link refresh or macro execution | Reopen calculated values and check expected results/errors; setting a recalculate-on-open flag is insufficient |
| Legacy DOC/PPT/XLS convert | Converter that recognizes the actual source format and produces the admitted target | Preserve original, validate target, and report feature/layout losses; no implicit legacy native-edit promise |
| Any Office convert to text/Markdown/CSV | Extractor for selected content and a named target dialect/encoding | Record omitted stories/slides/sheets, formulas versus values, formatting, media and metadata as relevant; never call this a native round trip |
| Any Office render | Compatible rendering engine, fonts and page/slide/sheet selection | Inspect exact output for clipping, overflow, substitutions and layout; semantic/structural checks still apply when required |

## Recognize the container before OPC inspection

An extension is a hint, not identity. Inspect the file signature/container and
format metadata before selecting its parser. A ZIP reader may find an embedded
archive inside a compound file; successful ZIP opening does not establish that the
outer document is an OPC package. Check the outer container and its document-type
relationships, not just ZIP readability or a content-types entry.
Legacy `.doc/.ppt/.xls` and their legacy template/show variants are not OOXML;
neither renaming the file nor feeding it to an OOXML ZIP parser converts it.
Non-ZIP input is not automatically malformed: legacy formats and encrypted Office
containers need their own recognition. A compound-file signature alone does not
identify which Office format it holds. Encrypted packages may contain an OOXML
document internally; route decryption only under the appropriate authority.

For a recognized legacy source, preserve its identity and use a compatible reader
or explicitly admitted conversion if it satisfies the request. The converted copy
is a distinct artifact with checks and a loss report, not a replacement original.
Report an unsupported source/operation or unavailable compatible converter without
pretending modern-library support covers legacy files. Ambiguous or mismatched
format metadata requires resolution before mutation.

## Inspect admitted OOXML packages

OOXML uses an Open Packaging Conventions ZIP container with typed parts and
relationships. Before a native parser receives untrusted input:

1. Bound source bytes, entry count, per-entry and total expanded bytes,
   compression ratio, nesting, time, memory, disk, and concurrency.
2. Inspect entries without extracting them. Refuse encrypted entries, absolute or
   parent paths, duplicate/conflicting names, and limit violations.
3. Require `[Content_Types].xml`; parse content types and relationship parts with
   entity and network expansion disabled.
4. Inventory external targets, digital-signature parts, VBA projects, embedded/OLE
   objects, custom XML, and format-specific parts. Do not retrieve or execute them.
5. Compare the inventory with the requested preservation set and the binding's
   observed feature surface before any mutation.

Do not unpack into the destination tree. If a low-level operation requires
extraction, contain every resolved target beneath task-scoped scratch and clean it
afterward. ZIP/XML well-formedness, schema validation, native reopening, and visual
rendering are separate evidence classes; none implies the others.

## Preserve source and inactive content

Write a distinct artifact by default. Produce it in task-scoped scratch, close the
producer, and reopen/check that candidate before committing it under the shared
execution rules. Verify the committed bytes and source identity; avoid a redundant
parse when the checked candidate and committed bytes are identical. Never overwrite
a prior valid artifact merely because the producer exited successfully.

- Treat VBA, embedded code, OLE objects, and external relationships as inert data.
  Never enable macros, activate objects, refresh data, follow links, or fetch
  templates during inspection or editing.
- A provider option named `keep_vba`, `keep_links`, or similar requests
  preservation only; it does not execute content or prove semantic/byte
  preservation.
- Refuse mutation of a signed package unless signature invalidation is explicitly
  accepted. Report the signature inventory and loss.
- Do not change between macro-enabled and ordinary extensions by renaming. Package
  content types, parts, producer capability, and the requested target must agree.
- Do not repair or rewrite malformed input as a side effect of inspection.

## Apply format-specific requirements

Apply [forward representation fidelity](representation-fidelity.md) to bind
equations, relations, tables, charts and references to accepted content and their
effective regions. Use compatible native objects for required semantics and
editability; declare losses for substitutes. Preserve field/reference targets,
chart source bindings, reading order, headers and alternatives when required.
The shared reference owns capacity repair and evidence classes.

### DOCX

Locate the affected story and its paragraph, table or section context, including
headers/footers, notes, revisions, text boxes and relationships when relevant.
Construct paragraphs by their roles in the maintained style hierarchy; compose
text, emphasis, links, fields and equations as inline objects. Resolve pagination
through section geometry and paragraph flow (spacing, keep-with-next, breaks),
then inspect the affected pages.

For a phrase edit, map its character span across existing inline objects before
changing text. For example, replacing a name split across two styled runs means
distributing replacement text under the accepted formatting policy while keeping
surrounding runs and link/field targets. An ambiguous match or styling policy
needs resolution at that span. Whole-paragraph replacement is suitable only when
its inline structure is expendable under the request.

With `python-docx`, assigning `Paragraph.text` removes run-level formatting;
`iter_inner_content()` distinguishes runs and hyperlinks. Its document paragraph
and table collections omit revision content, and the latter excludes nested tables.
Use a compatible mechanism for affected features outside that view, or report the
exact limitation. Reopen to compare the changed span, style inheritance and
preserved inline objects/relationships; compilation or rendering cannot replace
those checks.

### PPTX

Inventory slide order, sizes, masters, layouts, themes, shape-tree order, groups,
placeholders, text, tables, notes, media, charts, hyperlinks, animations, SmartArt,
embedded objects, signatures, and active content as applicable.

After creation or editing, reopen and check slide/order identity, selected
master/layout relationships, shape type and z-order, text/table values, geometry,
and relevant media relationships. A high-level presentation library may expose
only part of this surface; probe the exact requested feature instead of inferring
preservation from successful opening. Basic slide construction does not prove an
existing corporate master, animation, or presentation behavior was preserved.

For `python-pptx` inspection, check `has_notes_slide` before accessing `notes_slide`:
access can create a notes slide and master when absent. Inspect inherited master
content separately when needed; it may be visible without appearing in the slide's
own shape collection. Extracting text does not prove its intended reading order.

### XLSX

Locate affected cells by row/column meaning, stored type, format and source
binding. Preserve workbook/sheet identity, merges, hidden state, names, tables,
validations, charts, pivots and active/external content as applicable. Keep text
identifiers such as leading-zero codes distinct from numbers. Interpret date
serials with the workbook's 1900/1904 system and cell format; required time zones
need an explicit convention.

For structural changes, construct the source-to-destination mapping and update
affected dependents, including incoming references. For example, inserting an
observation before a total can move the total, expand its formula, table and chart
ranges, and change a defined name or another sheet's reference. Decide each from
its intended data role: an expanding series and a fixed cohort need different
ranges. An unrelated constant or sheet remains unchanged. Reopen to inspect these
bindings, not merely the moved values.

With `openpyxl`, row/column insertion does not manage formula, table or chart
dependencies. `move_range(..., translate=True)` translates formulas inside the
moved range, not incoming references or defined names; explicitly repair the
affected bindings or choose a mechanism that preserves them.

Formula source, cache and freshly calculated result are separate. `data_only=False`
reads formulas; `data_only=True` reads stored caches. `openpyxl` does not calculate.
For required fresh results, use a compatible calculation engine and verify saved
values/errors against admitted inputs; a recalculate-on-open flag is insufficient.
A noncalculating edit can preserve formulas but leaves fresh results unverified.

Prove the affected feature round trip before a preservation-critical save;
unsupported drawings or other parts may be lost. VBA/link preservation flags
prove neither retention nor execution authority. Keep macros and external refresh
inactive. Worksheet/workbook protection deters editing; it is not encryption.

## Match validation to the claim

Use one native producer, then reopen the exact output once for all compatible
semantic and structural checks. Add a schema validator only when the requested
conformance class is named and a binding exists. Add a renderer only for a visual
claim; inspect the affected pages, slides, or sheet print regions for overflow,
clipping, font substitution, geometry, and image placement.

Provider success or native reopening does not prove preserved meaning, full OOXML
conformance, or visual fidelity. Record the inspected feature inventory, bindings,
checks, active/external content, accepted losses, unresolved regions, and recovery
in the shared `ArtifactResult`. Malformed input or an unsupported request is
terminal. A provider-specific limitation may select an admitted compatible branch
under the shared execution rules; it does not justify an unrelated library cascade.

## Authoritative references

Resolve version-sensitive rules from current primary sources at use time:

- [ECMA-376 Office Open XML](https://ecma-international.org/publications-and-standards/standards/ecma-376/)
- [Microsoft Open XML SDK documentation](https://learn.microsoft.com/en-us/office/open-xml/open-xml-sdk)
- [Microsoft 365 Math](https://learn.microsoft.com/en-us/office/math/)
- [Microsoft Office XML extension reference](https://learn.microsoft.com/en-us/office/compatibility/xml-file-name-extension-reference-for-office)
- [python-docx text API](https://python-docx.readthedocs.io/en/latest/api/text.html)
- [python-docx document API](https://python-docx.readthedocs.io/en/latest/api/document.html)
- [python-pptx documentation](https://python-pptx.readthedocs.io/en/stable/)
- [python-pptx notes behavior](https://python-pptx.readthedocs.io/en/latest/user/notes.html)
- [openpyxl workbook reader](https://openpyxl.readthedocs.io/en/stable/_modules/openpyxl/reader/excel.html)
- [openpyxl structural edits](https://openpyxl.readthedocs.io/en/stable/editing_worksheets.html)
- [openpyxl formulas](https://openpyxl.readthedocs.io/en/stable/simple_formulae.html)
- [openpyxl dates and times](https://openpyxl.readthedocs.io/en/stable/datetime.html)
- [Office encrypted packages](https://learn.microsoft.com/en-us/openspecs/office_file_formats/ms-offcrypto/b60c8b35-2db2-4409-8710-59d88a793f83)

The standard defines representation, provider documentation defines an interface,
and only the current request's probe establishes a usable binding.
