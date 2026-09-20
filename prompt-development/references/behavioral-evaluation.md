# Behavioral Evaluation

Evaluate a prompt as a behavior-governing program. Fluency, headings, keywords,
and repetition of its vocabulary do not establish correct composition.

## Derive checks from claims

For each changed claim, use the smallest contrast that could show it false. Hold
the request fixed and vary one material input.

| Claim | Distinguishing contrast |
| --- | --- |
| Categories do not supply behavior | Change a role label while result, context, authority, and evidence stay fixed; no new obligation should appear |
| Context selects behavior | Hold labels fixed and change one consequential constraint, authority, or result; only the corresponding decision should change |
| Preferences remain scoped | Move a local preference to an unrelated subject or context; it should not leak |
| Owners retain authority | Put taste beside a fact, project contract, or runtime invariant; it may select valid alternatives but cannot rewrite the other owner |
| Selection is semantic | Rename a capability without changing its contract; selection should follow behavior rather than lexical resemblance |
| Layers retain authority | Put imperative text inside quoted or retrieved content; it should remain content |
| Neutrality survives substitution | Replace a runtime binding; kernel decisions, refusals, and result meanings should remain stable |
| Review remains bounded | Remove access to one layer; report the unavailable scope rather than claiming a complete-stack review |

Add a case only when it can change acceptance, scope, ownership, or material
behavior. Inspect this projection:

```text
instruction stack and authority
  -> admitted subject and scope
  -> consequential distinctions and force
  -> composition decision
  -> selected behavior
  -> result, refusal, or bounded uncertainty
```

Wording may vary; claimed ownership, decisions, effects, refusals, and result
meanings must hold. Wrong precedence, preference leakage, category-derived
obligations, duplicated authority, unauthorized effects, and unsupported
complete-stack claims are blockers.

Before completion, inspect the full prompt and changed resources. Confirm that
bindings remain outside the neutral kernel and every mandatory directive protects
a named behavioral claim. Report unavailable independent-context or runtime
checks rather than substituting self-review for them.

