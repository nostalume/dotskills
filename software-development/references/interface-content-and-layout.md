# Interface content and layout

Use for a user-facing interface change within the development entry's accepted
contract. Reuse current terminology, task flows, components and design tokens.
Settle a consequential change to product meaning or behavior through Admission;
local wording and geometry choices remain part of implementation.

## Build from the user task

Identify what the user needs to recognize, decide and do in this view. Trace the
object, decision evidence, action and resulting state; use their dependencies to
determine what must be seen together and what can follow. Keep this a working
model of the task, without adding a project artifact unless it has a consumer.

- Give each concept one stable user-facing term across headings, controls,
  feedback and related views. Use existing project strings or domain definitions;
  explain a necessary alias and preserve distinct concepts, compatibility names
  and localization keys. A small working term map can help repeated decisions;
  it need not become a new project artifact.
- Name actions by their actual object and effect. Distinguish saving a draft,
  submitting it and publishing it when those are different operations. Prefer a
  direct action label to an introductory phrase; retain counts, qualifiers and
  warnings that affect the user's choice. Use links for navigation and buttons
  for state-changing operations, with emphasis and placement suited to their
  task role. Settle an ambiguous effect instead of guessing a polished label.

## Make task relationships visible

Choose regions from those task dependencies, reusing a suitable project page
pattern. Selecting objects to inspect can favor list/detail; editing with
context can favor a work area and supporting region. These illustrate relations,
not a template menu: derive another arrangement when the task or space calls for
it. Allocate prominence to the primary task or comparison and its supporting
context; parallel comparisons can need equal emphasis.

Within regions, group each decision's evidence and inputs with its local action
and feedback where present. A shared final submit can close several groups while
each retains its task boundary. Express relationships through shared
alignment, closer spacing within groups, separation between groups and restrained
headings, adding containment when it clarifies a shared context. Text alignment
and the position of the whole content region are separate choices; a geometric
center or equal cards need not establish task focus. Map the arrangement to the
project's components and tokens. As space changes, reflow or sequence regions
while preserving related content, task dependencies and meaningful DOM, reading
and keyboard order.

## Check the delivered view

Trace a representative task through actual labels, controls, state feedback and
related views. Confirm that the same term still identifies the same concept and
that actions promise only their implemented effects. Inspect representative long
labels, empty/error states and intended desktop/compact widths for grouping,
competing emphasis, wrapping and overflow, using the task-based rendered probes in
[feedback methods](feedback-methods.md). Reuse relevant existing checks; report
unobserved rendered or interactive states instead of inferring usability from
source alone. A review-only request still grants no edits.
