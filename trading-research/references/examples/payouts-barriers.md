# Payout Gates and Attainable Barrier Outcomes

All values below are synthetic currency amounts/prices. Use
[decisions and labeling](../knowledge/decisions-labeling.md) for the general
construction and [execution](../knowledge/execution-funding.md) for the ledger.

## A cost mutation changes participation

Hold success probability \(p=0.63\), gross successful gain \(G=42\), failure
loss magnitude \(L=38\), and identical per-trade cost \(c\). Expected payment is
\(pG-(1-p)L-c\). At \(c=3\), it is 9.4; at \(c=15\), it is -2.6.
Threshold probability changes from \(41/80=0.5125\) to \(53/80=0.6625\).
The same calibrated forecast clears the first gate and fails the second. Changed
conditional magnitudes require recomputing the gate as well.

## Equal endpoint, different first passage

Entry price is 100, upper/lower barriers 102/98, with observation at each listed
point and immediate eligible fills at hit prices for this fixture only:

| History | First hit | Payout before costs |
|---|---|---|
| 100 → 103 → 99 → 101 | Upper | +2 |
| 100 → 97 → 103 → 101 | Lower | -2 |
| 100 → 101 → 100.5 at deadline | Timeout | +0.5 |
| 100 → 101, observed before deadline | Unfinished | Not yet mature |

A timeout class code of zero is not a zero-money payout. A hit exactly at a
deadline uses the frozen hit/deadline precedence convention. A bar with high 103
and low 97 leaves hit order ambiguous; these fixtures have ordered observations,
so their distinction is available. Coarser data must preserve an ambiguity status
or use a documented conservative treatment, not silently pick the favorable path.

## A trigger can be favorable while the fill loses

Assume shares entered at 10.20 cannot be resold that session and no old sellable
inventory exists. A later print at 10.60 triggers an upper barrier, but the first
permitted exit fills at 9.40. Realized simple return is
\((9.40-10.20)/10.20=-7.8431\%\), before costs. This is an assumed eligibility
fixture, not a current rule determination for every stock/account. Record the
trigger class separately from signed attainable payment. A policy that monitors
only after sale becomes eligible defines a different first-hit target. Old
sellable inventory requires a separate quantity record.

## An eventual recovery cannot undo forced exit

For a synthetic linear long of one unit at 100, deposit 20 cash equity, charge no
fees and assume fixed maintenance requirement 12. Mark sequence 100 → 90 → 110
gives equity 20 → 10 → 30 only if the position survives. Under this fixture's
rule, equity 10 breaches maintenance at 90; liquidation there leaves 10, and the
later recovery belongs to an unheld position. Actual contracts need their own
mark, margin and liquidation conventions. The target/payout must include the
allowed forced-exit policy rather than endpoint direction alone.

## First teaching policy and meta comparison

For a copper-style daily experiment, freeze a scale estimated from twenty known
one-session returns, horizontal distances of two scales, and a ten-session
deadline. Begin with close-observed triggers and explicitly later eligible fills.
Store class, interval, maturity, fill/status and net payment. For meta-labeling,
freeze a twenty-session momentum side, generate candidates forward, and compare
the same primary policy with/without a small probability gate. Fit on candidate
observations available then; in-sample learned primary predictions are not a
forward primary stream. Numerical model bindings are in [model pilots](model-pilots.md).

These constants define the initial experiment. Change them on development with
trial accounting. The result is a reproducible policy specification; no backtest
performance is asserted.
