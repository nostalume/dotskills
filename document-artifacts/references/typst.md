# Typst artifacts

Use this reference for a Typst source or a rendered artifact whose canonical form
is Typst. Typst is a source language and compiler, not a Markdown or LaTeX dialect.
Resolve syntax from the [Typst reference](https://typst.app/docs/reference/)
compatible with the project's compiler/packages, and command behavior from the
admitted compiler's `help` output. Newer documentation does not authorize an upgrade.

## Preserve or establish the source boundary

For existing work or a new document in an existing project, locate the current
editing source, language companions, maintained template/public entry, imports,
assets, fonts, inputs, package/compiler constraints and output convention. Read
the owning project instructions and template interface before selecting defaults.
Preserve this graph unless the requested result calls for a change. When Typst
projects another accepted source, keep that direction and the meaning-bearing
correspondence; a parallel source or old output does not silently become current.

For independent new work, start with one source and its necessary assets. Add a
module for actual reuse or ownership, and reuse an applicable project producer.
PDF, PNG, SVG, HTML and other compiler targets remain derived artifacts.

Typst has distinct markup, math, and code modes. Determine the active mode before
escaping or changing syntax. In particular, do not translate a LaTeX command or a
Markdown construct by visual analogy. Use the current
[syntax reference](https://typst.app/docs/reference/syntax/),
[math reference](https://typst.app/docs/reference/math/), and maintained project
analogues.

## Author in the active language context

Use these distinctions when generating or changing source; consult the linked
official section for uncommon constructs instead of guessing from another language.

| Decision | Rule / source |
| --- | --- |
| Markup versus code | `#` enters a code expression from markup; do not repeat it inside an existing code expression. Content blocks return to markup, where embedded expressions need it again. See [syntax](https://typst.app/docs/reference/syntax/). |
| Content versus strings | `[markup]` creates content; `"text"` is a string. Displaying a string does not parse its characters as markup. Choose the value type required by the function; do not use evaluation to make user text executable. See [scripting](https://typst.app/docs/reference/scripting/). |
| Escapes and literals | Escape for the active mode. Raw code is literal, not an evaluated expression. Do not apply one global replacement rule to code, strings, markup, and math. |
| Styling | `set` configures supported element parameters; `show` selects elements for styling or transformation. Use the maintained template interface for document-wide choices and scoped rules for local variation; inspect their effective scope before adding overrides. See [styling](https://typst.app/docs/reference/styling/). |
| Contextual values | Effective styles, locations, counters, and queries can depend on where content is placed. Use `context` when the API requires it; it produces contextual content, not an eagerly available global value. See [context](https://typst.app/docs/reference/context/). |
| Mathematics | Use Typst math syntax and symbol/function names, not LaTeX commands. Inline/block form and multi-letter identifiers have language-specific meaning. Inspect rendered symbols and grouping. See [math](https://typst.app/docs/reference/math/). |
| References and citations | Attach labels to the intended elements and enable numbering when the referenced element requires it. Resolve bibliography keys from the admitted bibliography file; do not invent keys or treat a successful compile as citation correctness. See [references](https://typst.app/docs/reference/model/ref/) and [bibliography](https://typst.app/docs/reference/model/bibliography/). |
| Modules and packages | Distinguish including content from importing bindings; use imported module namespaces or explicit imported names. Preserve version-qualified package identities and resolve availability under the dependency rules below. |

For example, `#text([Value: #(1 + 2)])` enters code, returns to markup in the
content argument, then evaluates its nested expression. `#text("*literal*")`
displays the asterisks; it does not create strong emphasis. These illustrate mode
boundaries, not a document template or required typography.

## Project semantic structures into Typst

Apply [forward representation fidelity](representation-fidelity.md) to compose
paragraphs from prose, mathematical relations and references. Construct each
mathematical span from its operands, operations and attachments before spelling
Typst tokens. Preserve complete relations: `$J_(B) D$` has a following factor,
whereas `$J_(B D)$` puts both letters in the subscript. Group compound fractions
and attachments by that meaning, including inside running prose.

Choose math spans by their role in the sentence: variables and expressions use
math content; ordinary names, quotations and literal source retain their own
roles. A string such as `#text("Let $x_i$ vary.")` does not evaluate its embedded
notation. Compose markup or content arguments instead:

```typst
Let $kappa = 2 n + d - 2$ and $t = kappa - 2$.
Apply $S$ to $m_0$, $Y m_1$, and $U m_2$.
```

These sentences illustrate content boundaries, not required wording. Do not infer
math spans by globally replacing letters, Unicode glyphs or underscores. Resolve
variables, named operators, descriptive text and literal code from the accepted
meaning; Unicode symbols can be valid math input, while a text subscript glyph
does not establish a native mathematical attachment. Use compatible symbol,
operator and function names; group an attachment without absorbing the next
factor. Consult [math](https://typst.app/docs/reference/math/),
[fractions](https://typst.app/docs/reference/math/frac/) and
[attachments](https://typst.app/docs/reference/math/attach/) for uncertain grammar.

Inline math participates in the paragraph's syntax and reading rhythm. Use
`$x$` for an inline span; whitespace on both inside edges, as in `$ x $`, selects
display form. Keep surrounding sentence punctuation in prose unless it belongs
to the expression. Select a display equation when a derivation, alignment,
reference or expression size needs independent reading. For crowded inline math,
clarify or divide the sentence, introduce a reusable definition, or move the
relevant relation to display form before shrinking type. Judge baseline, script
size, font coverage, leading and line breaks in their actual paragraph, caption,
footnote or cell context. Template styles and contextual values determine those
results; preserve the project notation across inline and display uses.

For relational content, retain prose or inline notation only when the audience
does not need to trace material direction, branching, rejoining, grouping, or
hierarchy. Otherwise consume the representation selected by visualization design
and implement its nodes and typed edges with a compatible native construction,
project package, or accepted placed asset. Choose a package only afterward and
preserve its namespace/name/version identity. A cold cache without network
authority is an unavailable adapter, not permission to flatten the relation into
raw text.

Bind table headers, spans, units, cell content, captions, and references to their
accepted owners. Name the effective page, column, list, cell, or other containing
region when sizing an equation, table, figure, or diagram. Relative width resolves
against that region; resolve the compatible behavior from the current
[layout reference](https://typst.app/docs/reference/layout/layout/). Keep outer
placement separate from internal equation, label, or cell alignment; center an
object only when the accepted composition or project style requires it.

A containing width or an unbreakable block does not by itself fit its internal
equation. Break a derivation at meaningful relations and retain the argument
order. For overflow or excessive density, wrap labels, rebalance spacing/grouping,
reorient or split the representation, or select an authorized wider region before
scaling. Do not crop, overlap, or remove accepted meaning. Recheck the exact
render after each source revision that changes geometry.

## Admit one compiler binding

Select the official Typst CLI, or another provider when the request explicitly
requires it. Keep the following execution details with the task:

- executable/provider identity and observed version;
- the project or user compatibility constraint and current official source used to
  select that version;
- working directory, project root, entry source, distinct output, and overwrite
  policy;
- named external inputs and their non-secret values or references;
- system-font policy and any explicit font paths;
- local-package path, package-cache path, and network-acquisition authority;
- target format, diagnostic form, job/time/page/byte bounds, and cancellation;
- trust classification for source, packages, plugins, and external assets.

Probe the exact entrypoint with its version command and inspect its current general
and compile help before forming arguments. Inspect the compiler's font inventory
when typography or non-Latin glyph coverage matters. Do not infer support from a
launcher, editor extension, web application, lock file, or executable name.

Do not invoke watch, update, init, an output viewer, or a web compiler as part of a
bounded compile. Those commands introduce persistence, acquisition, long-lived
processes, GUI effects, or remote transmission beyond the compile postcondition.

## Contain inputs and dependencies

Set an explicit project root that contains every admitted local source and asset.
Reject or separately admit paths, links, or imports that escape it. Pass external
values through named compiler inputs only when the source contract calls for them;
do not place secrets in source, arguments, diagnostics, or generated metadata.

Fonts are dependencies. Name required families and variants from the source or
design contract, decide whether system fonts are permitted, and bind explicit font
directories when reproducibility requires them. A discovered family does not prove
glyph coverage or layout fidelity: compile and visually inspect representative
Latin, mathematical, CJK, or other required text. Missing fonts, substitution, or
missing glyphs are unresolved evidence, not harmless warnings.

A package import contains namespace, name, and version; preserve that identity.
The official compiler may fetch an uncached community package and then cache it.
Therefore source inspection and cache state decide whether compilation is local or
would acquire network content. A cache miss without network authority is
`unavailable`, not permission to retry online. Record a cache hit as reused local
state, not as a fresh download. Admit local packages, remote packages, and WebAssembly
plugins as separate trust and dependency boundaries. See the official
[package syntax](https://typst.app/docs/reference/scripting/#packages) and
[compiler package behavior](https://typst.app/open-source/).

## Compile and inspect each source revision

After source and binding are settled, make one direct compile call for that
revision. Inspect diagnostics and output; an authorized source correction changes
the input identity and permits recompilation. A stale output never proves that
the corrected source compiled. Its argument
record has this logical shape; include only options supported by the probed help:

```text
typst compile
  --root <project-root>
  [--input <name=value> ...]
  [font and local-package/cache bindings]
  [diagnostic and resource bounds]
  <entry.typ> <distinct-output>
```

Keep path handling native to the execution provider and pass arguments as an array
where the provider supports it. Choose the output extension or explicit format
from the live compiler's supported targets. If a paged raster/vector target needs
an output-name template, derive that rule from the same help rather than guessing.
Request dependency output when the postcondition needs a source graph or
reproducibility evidence. Do not compile the same settled source once for discovery
and again for delivery when one inspected output satisfies both.

Write to a distinct target. Replace an existing deliverable only after the new
artifact passes its required checks and the request authorized replacement. Keep a
failed or partial result separate from the prior valid artifact.

## Validate the claimed fidelity

- Semantic: inspect the accepted text, values, equations, labels/references,
  captions, links, table schema, relation paths, and named inputs in source and
  output as applicable. Compare changed mathematical relations, including inline
  spans and math left in text strings, with the accepted structure. In language
  companions, check those relations as well as shared display blocks; compilation
  or equality between two generated copies is not the independent source check.
- Structural: require a successful compiler result, inspect diagnostics and source
  locations, and compare the observed dependency graph to admitted inputs.
- Visual: inspect representative rendered pages for page geometry, overflow,
  tables, figures, formulas, references, font substitution, required scripts, and
  fit/alignment inside the named containing region. Inspect changed inline math
  at reading size with its surrounding lines and affected page transitions;
  display-only samples cannot establish paragraph fidelity.
- Accessibility: when required by the target and representation contract, inspect
  the delivered alternatives, reading sequence, link purpose, and structure with
  a suitable target-aware mechanism; do not infer them from the Typst source or
  rendered appearance.

Compilation alone proves neither appearance nor semantic equivalence. For a PDF
rendered from Typst, validation remains part of this source-language operation; an
independent PDF edit uses [PDF operations](pdf.md). Preserve existing source style. Claim
a formatter pass only after admitting and running the exact formatter binding; a
compiler is not a formatter.

Return the compiler/provider identity and version, exact source/root/output
identities, performed checks, diagnostics, dependency or font observations needed
by the result, package/network effects, losses, and cleanup. Remove scratch source,
downloads, caches, and generated pages unless the user requested retention or an
observed regression has a named durable consumer. Remove only owned scratch;
preserve pre-existing material of uncertain ownership and report its retention.
Cleanup failure does not erase a successful compile or justify claiming absence.
