# Markdown boundary

Preserve the repository's existing Markdown dialect and conventions. For new
standalone text, name CommonMark, GFM, or another required consumer dialect when
the distinction changes behavior. Tables and task items are GFM extensions;
footnotes and dollar-delimited math need a separately named extension or consumer
contract. Apply the shared forward-representation protocol before selecting math,
diagram, table, raw-HTML, or image syntax. Raw text, ASCII art, pipe tables,
embedded HTML, and consumer extensions carry different semantic, structural,
editability, and accessibility guarantees; use one only when it preserves the
admitted contract or declare the exact loss. Preserve code spans/blocks and apply
escapes in the context defined by the selected dialect. Treat raw HTML as
consumer-controlled active content because
renderers may pass, filter, sanitize, or reject it differently. Validate links and
rendering only when claimed or required by that consumer. Select a parser/renderer
configured for that consumer before asserting extension support; a library's
"Markdown" or "GFM" label does not establish its enabled extensions. Check relative
links from the document's destination, and preserve literal code rather than
interpreting embedded math or escapes. A conversion records its
source and lost layout, comments, formulas, metadata, or embedded media rather than
presenting Markdown as equivalent to the original. Use the current
[CommonMark specification](https://spec.commonmark.org/) or
[GFM specification](https://github.github.com/gfm/) as applicable.
