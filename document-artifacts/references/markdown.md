# Markdown boundary

Preserve the repository's consumer dialect and conventions. For new work, select
CommonMark, GFM or the required consumer when behavior differs. Compose content
roles before syntax: prose, literal code, mathematics, tables, references and
diagrams need their corresponding supported constructs. A dollar-delimited
expression needs a named math extension; the same characters inside a code span
remain literal. GFM tables/task items do not establish footnote or math support.

Apply [forward representation fidelity](representation-fidelity.md) to structured
content. Choose pipe tables, native extensions, HTML or assets by the required
semantics, editability and accessibility, declaring unsupported properties as
losses. Escape within the actual context; preserve code spans/blocks. Raw HTML is
consumer-controlled active content: it may pass through, be sanitized or rejected.

Validate with the destination's configured parser/renderer when support or
appearance is claimed; a generic Markdown/GFM library label is insufficient.
Resolve relative links from that destination. Conversion records omitted layout,
comments, formulas, metadata and media as applicable; it does not establish a
native round trip. Use the [CommonMark specification](https://spec.commonmark.org/)
or [GFM specification](https://github.github.com/gfm/) for the selected dialect.
