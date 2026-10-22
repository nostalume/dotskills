# User documentation

Write for a reader trying to accomplish an observable goal, not for the source
tree. Choose the form from the question: a tutorial teaches through one guided
success, a how-to solves one task, a concept explains a model, and troubleshooting
maps symptoms to diagnosis and recovery. Do not combine all four by default.

For a conceptual explanation, establish the practical question and a small
organizing model before its details. Introduce a concept where it resolves a
reader-visible need; connect its meaning to a concrete case, then its consequence
and limits. Each paragraph should build on what the reader now knows. Tutorials
interleave this explanation with actions at the point of use; the task sequence
below remains applicable to how-to work rather than a mandatory article outline.

## Minimum successful path

Present, in this order when applicable:

1. the goal and expected result;
2. prerequisites, supported version/platform, permissions, cost, and destructive
   or external effects;
3. the shortest copyable sequence using public vocabulary;
4. one concrete observation that proves success;
5. options only where the reader must choose;
6. common failures with symptoms, cause, safe recovery, and residue;
7. compatibility or migration limits and the next useful step.

Separate commands from their output. State the working directory, shell/runtime,
placeholder syntax, and whether a command reads, changes, publishes, or deletes
state. Never hide required approval, credentials, network access, or cleanup in a
prerequisite paragraph.

## Reader-oriented checks

Run the path as the documented reader from the declared starting state. Prefer a
clean install or packaged artifact when users do not consume the source tree.
Confirm copy/paste behavior, output, errors, links, and recovery. For explanations,
trace whether the reader can identify why each new concept is needed and how the
next conclusion follows; repair a missing bridge rather than merely add headings.
Test unsupported
or dangerous variants when the document promises their refusal. Remove internal
details that neither change a user decision nor explain an observable failure.
