# Interface content and layout

Use for a user-facing interface change within the development entry's accepted
contract. Reuse current terminology, task flows, components and design tokens.
Settle a consequential change to product meaning or behavior through Admission;
local wording and geometry choices remain part of implementation.

## Build from the user task

Identify what the user needs to recognize, decide and do in this view. Relate the
visible objects, actions and states to that task before choosing copy or layout.

- Give each concept one stable user-facing term across headings, controls,
  feedback and related views. Use existing project strings or domain definitions;
  explain a necessary alias and preserve distinct concepts, compatibility names
  and localization keys. A small working term map can help repeated decisions;
  it need not become a new project artifact.
- Name actions by their actual object and effect. Distinguish saving a draft,
  submitting it and publishing it when those are different operations. Prefer a
  direct action label to an introductory phrase; retain counts, qualifiers and
  warnings that affect the user's choice. Settle an ambiguous effect instead of
  guessing a more polished label.

## Make task relationships visible

Group controls and feedback that complete the same subtask; give separate tasks
clear boundaries. Keep an action with its inputs and resulting state. Select the
primary task or comparison for this view, then allocate prominence to it and
supporting context. A geometric center, equal cards or a single dominant control
is not a universal requirement; parallel comparisons can need equal emphasis.

Use shared alignment and rhythm, closer spacing within groups and separation
between groups, and a restrained hierarchy of headings and emphasis. Match the
project system rather than introducing arbitrary tokens. Keep related content
together as the viewport changes; preserve meaningful DOM, reading and keyboard
order when visual placement changes.

## Check the delivered view

Trace a representative task through actual labels, controls, state feedback and
related views. Confirm that the same term still identifies the same concept and
that actions promise only their implemented effects. Inspect representative long
labels, empty/error states and intended desktop/compact widths for grouping,
competing emphasis, wrapping and overflow. A reader should locate the task and
its next action without knowing the component tree. Reuse relevant existing
checks; report unobserved rendered or interactive states instead of inferring
usability from source alone. A review-only request still grants no edits.
