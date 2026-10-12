# Research Lifecycle and Traceable Computation

Use this entry to decide what a revision invalidates, diagnose deterioration and
scale a research workload. Begin with one recoverable full-route experiment and
three monitoring layers: inputs, mature task performance, and realization. Keep
the original question and admitted results when repairing a failed dependency.

## Evidence belongs to the complete route

An experiment binds source versions, historical population, availability rules,
target/payout/maturity, transforms, search/fitting, calibration, aggregation,
holdings and execution. Its predictions and trial history are observations of
that route. The smallest useful record is whatever lets its reviewer reconstruct
those bindings and distinguish a changed route; use existing project records.

| Revision | Affected evidence |
|---|---|
| Correct a field's historical availability | Rebuild affected features/predictions and downstream confirmation |
| Change a label, horizon or exit | Rebuild targets and maturity; reconsider fit, calibration, payout and inference |
| Change only numerical implementation of the same operation | Compare exact/tolerance output and failure cases; unchanged semantics may reuse market evidence |
| Change probability calibration, gate, risk or fill rule | Renew the selected consumer comparison, even with the same raw model scores |
| Add a factor after searching the test interval | That interval now informs selection; use a newly separated confirmation route |
| Change cash accessibility or borrow permission | Reopen feasibility and net-value claims; a prior forecast-loss result may remain valid |

A source/model digest identifies bytes, not the meaning or authority of a claim.
Record the assumptions that can invalidate reuse along with its numerical identity.

## Diagnose at the layer where the result changes

Input monitoring checks timeliness, units, missingness, releases/revisions, eligible
universe and joins. Mature task monitoring checks proper loss/rank quality,
calibration and opportunity coverage against its fixed control. Realization
monitoring checks holdings/exposures, turnover, spreads, fills, costs, cash and
counterparty accessibility. A forecast can remain useful while costs exhaust its
payment; a fresh data feed can still measure the wrong construct.

Derive review frequency and uncertainty from completed opportunities. If each of
\(m\) repeated looks has false-alarm probability at most \(\alpha\), the union
bound is \(m\alpha\), without assuming independent looks. Repeatedly applying a
single-look 5% rule can therefore raise false alarms. Freeze cadence and stopping,
use an appropriate sequential/error-spending design or assess the whole scheduled
monitor on development/stress data. Overlapping samples require the dependence
treatment in [validation](inference-validation.md); a handful of outcomes cannot
estimate a stable edge precisely.

**Suspend** affected actions for hard integrity, reconciliation or funding failures.
**Investigate** a statistical deterioration with its costs, uncertainty and rival
accounts. **Retire** a version whose supported use no longer clears its comparator.
**Redevelop** a new route when a repair can answer the originating question.
Do not turn a temporary crowded unwind automatically into model decay, or a
possible reversal into a reason to ignore liquidity limits. Preserve the dormant
version and its record for comparison rather than retroactively rewriting results.

## Shadow changes before replacing the comparison

Run old and proposed versions on the same as-of opportunities with withheld
execution effects. Compare paired predictions, decisions, hypothetical fills and
ledger results using the same admitted observations. Mark any differing observation
or policy assumption. A shadow fill model is not actual execution evidence.
Select changes on development and confirm their required increment; repeated shadow
selection also consumes evidence. Restore a frozen snapshot and reconcile its
outputs to test recovery, including unavailable dependencies and incomplete jobs.

## Scale the measured bottleneck

First profile the complete workload: acquisition/decoding, joins/transforms,
factor evaluation, numerical fit, memory, communication and result inspection.
Remove duplicated deterministic work and batch compatible operations before
parallelizing independent candidates. A cache key includes input and source
versions, as-of logic, operation, units, parameters and relevant runtime/numerical
conventions; a cache hit is valid only when those meanings match. Incomplete,
failed or mismatched results cannot masquerade as scored candidates.

If fraction \(s\) of work is serial, ideal speedup with \(n\) workers is at most
\(1/[s+(1-s)/n]\): sum unchanged serial time and divided parallel time.
Serialization, communication and failures lower the achieved gain. Distributed
data parallelism replicates a model and synchronizes gradients; parameter sharding
addresses a different memory problem. Verify actual runtime/version semantics
when implementing either. More workers do not fix an evaluator that rewards leaks.
Record bounded attempts, failure disposition and resumable outputs for long searches;
choose columnar files or a database from measured query/concurrency needs, not from
an institutional infrastructure shopping list.

## Usual practice path

One full-route record → one exact/tolerance rerun → input/task/realization controls →
fixed review cadence and action semantics → paired shadow comparison → renewed
confirmation at the changed edge → bounded replacement and recovery test.
Actual deployment, monitoring automation and live trading require their own
authorization. A conceptual or brief explanatory inquiry need not create a ledger.

Worked revision and recovery cases: [lifecycle examples](../examples/lifecycle-revisions.md).
Operational experience: [institutional cases](../examples/institutional-experience.md).
System background: [Sculley et al.](https://proceedings.neurips.cc/paper_files/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html).
