# Data, Measurement, and Representation

Use this entry to construct the historical research object and the state a
restrained predictor can read. Select observations for their decision-relevant
distinctions, availability, cost and grain. A refined factor is a measurement
with a defined role; standardization is one possible operation on it.

## Reconstruct what was knowable

A record has an instrument/entity identity, event time, publication time, local
receipt time, version, unit, and source. These clocks answer different questions.
For a historical decision at \(t\), select the version whose applicable
availability time is at most \(t\). Later corrections stay in later views.

Let versions for fact \(j\) be \((v_{jk},a_{jk})\), where \(a\) is historical
availability. Its as-of value is the version with greatest \(a_{jk}\le t\),
subject to the source's supersession semantics. A fact without an admitted
historical availability time is unavailable for that predictive claim. The event
date alone does not decide admissibility.

Define the opportunity population from information and rules available at the
cutoff. Use historical listings, eligibility, sector/universe membership and
delistings. Current survivors create an outcome-conditioned population. Execution
failures after selection remain outcomes of the frozen policy; deleting them
because the trade later became inconvenient changes its assessed coverage.
Missing data require a stated status and an accountable claim boundary.

Instrument identity includes actual contract, multiplier, currency, trading
calendar and cash rights. A continuous futures chart is a representation; a
position holds particular contracts. A roll needs closing/opening legs, quantities,
fees and prices. Splits and distributions need price and quantity/cash adjustments
that preserve the specified wealth calculation. A token, direct share and
derivative on either have different rights even when they share a company name.

**First construction:** build a small immutable as-of table and an instrument/
cash mapping before scoring many factors. Check a delayed release, revised value,
historical universe change and contract transition by hand. Scale the storage
after the semantics and measured workload are known.

## Match a measurement to the relation

Suppose the relevant concept requires order, accumulation, relative position or
replenishment. Encode that relation before choosing a scalar proxy. Executed
volume is a flow; displayed depth is a revocable stock. A quote, trade, cancellation
and depth update can be separate event streams. Their timestamps and meanings
determine which comparisons are possible.

For an unsettled relation, compare histories that produce the same proposed
summary but require a different research or action consequence. A consequential
collision motivates the smallest missing state, stream or operation. The absence
of a discovered collision is a provisional adequacy judgment, not a proof of
sufficiency. A cheap summary can be the right starting representation when it
preserves the distinction the task needs.

This observation-map discipline also serves inquiries with an open trading role.
A measurement can diagnose a state or formulate a new question before it has an
actionable alpha interpretation. Its valid use is assessed at that role.

## Distinguish new observations from readable coordinates

For finite target \(Y\), old information \(X\), and added source \(A\), adding
and subtracting \(H(Y\mid X)\) gives

\[
I((X,A);Y)=I(X;Y)+I(A;Y\mid X),
\quad I(A;Y\mid X)=H(Y\mid X)-H(Y\mid X,A).
\]

The last difference equals the expected divergence between the richer conditional
distribution and the old conditional distribution, so it is nonnegative. A new
source raises the population ceiling through conditional contribution. An
alternative-data label alone guarantees nothing: redundancy, stale observations,
revisions or a mismatched target can leave the increment zero.

A deterministic \(F=\phi(X)\) adds no Shannon information. It can expose a
relation to a restricted model. Let \(X\) be uniform on \(\{-1,0,1\}\) and
\(Y=1[X\ne0]\). Both \(X\) and \(X^2\) determine \(Y\). A one-threshold
probability model on raw \(X\) isolates one pure endpoint and groups the other
endpoint with zero. Its optimal average log loss is
\((1/3)0+(2/3)h_2(1/2)=2/3\) bits. A threshold on \(X^2\) separates the two
pure groups and has loss zero. Both have the same no-input baseline
\(h_2(2/3)\). This is a genuine improvement in usable information under the
same restriction, with no added raw information.

The transform would erase a sign target. Judge it relative to the desired use.
The [prediction entry](prediction-information.md) defines usable information and
the baseline needed for a fair comparison; its model-family restriction matters.
[Xu et al.](https://arxiv.org/abs/2002.10689) provide the formal framework.

## Construct a small task state panel

For positive prices, past log move and moving-average deviation are

\[
m_{t,k}=\ln(P_t/P_{t-k}),\quad
\bar P_{t,k}=k^{-1}\sum_{j=0}^{k-1}P_{t-j},\quad
d_{t,k}=P_t/\bar P_{t,k}-1.
\]

Multiplying all prices by \(a>0\) cancels in both ratios, proving the stated
scale invariance. Price zeros, negative values, contract changes and cash
distributions need their own representation. This algebra does not repair them.

A rowwise learner has no memory beyond the supplied row. The latest move cannot
represent all medium-horizon state. Provide a few policy-relevant past horizons,
trend/deviation, realized movement scale, volume/liquidity state and instrument
context. For futures add simultaneous-contract basis/curve and open-interest
state when historically available. Fix price, maturity, annualization and roll
conventions before interpreting carry. Economic relations motivate these fields;
their empirical orientation is a development question.

For relative tasks, cross-sectional centering/scaling exposes contemporaneous
position:

\[
z_{i,t}=(f_{i,t}-\bar f_t)/s_t,\quad
\bar f_t=n_t^{-1}\sum_i f_{i,t},\quad
s_t^2=n_t^{-1}\sum_i(f_{i,t}-\bar f_t)^2.
\]

The historical eligible, available set defines \(n_t\). Zero dispersion means
there is no relative distinction; use a fixed constant/missing-state convention.
Relative return, sector state and shared set summaries can supply context to a
per-asset learner. For single-instrument timing, use frozen training scaling or
a specified trailing window. Future evaluation rows cannot supply either scaler.

When a known exposure matrix \(B\) is to be removed, let \(W\) contain positive
diagonal observation weights. Weighted least-squares
neutralization solves \(\min_\beta(f-B\beta)^TW(f-B\beta)\). Differentiating
gives \(B^TWB\beta=B^TWf\); when invertible,
\(f_\perp=f-B(B^TWB)^{-1}B^TWf\) satisfies \(B^TWf_\perp=0\).
Handle rank deficiency explicitly. The operation removes the chosen linear
exposures. It can also remove useful predictive content, and nonlinear exposure
can remain. Choose the exposures from the target/risk role, then compare the
residual's incremental use.

**Usual starting panel:** a few multiscale relative moves/deviations, local risk,
liquidity/activity and the task's economic context. Define each column's formula,
lookback, unit, required streams, availability, missingness and intended relation.
The exact windows and feature count bind a first experiment, not the general
method. Add one justified relation at a time and retain its development history.

## Preserve persistent state when reducing frequency

First choose the low-frequency decision cutoff and target. Summarize events that
arrived before that cutoff. A completed future daily bar cannot enter a morning
decision. A high-frequency pattern can be an instantaneous disturbance or a
persistent state; the low-frequency consumer needs a construction that separates
those roles.

Under the declared model \(x_j=s+\epsilon_j\), with constant state \(s\) in the
window and independent mean-zero noise of variance \(v\), the window average
has noise variance \(v/m\). With common covariance \(c\) between disturbances,
it becomes \(v/m+(m-1)c/m\). Averaging helps under those assumptions and can
retain a noise floor. If state changes or ordering is decisive, averaging can
erase the desired information.

Start with interpretable window summaries: imbalance/flow, replenishment,
spread/depth/liquidity and a few subwindow states. Add a sequence encoder when
ordered histories with the same summaries require different outcomes. The encoder
must fit on development data and produce cutoff-valid outputs; a supervised
encoder trained on future evaluation outcomes leaks through its representation.

Variance retention is a different objective from predictive retention. For
\(X=(\epsilon Z,U)\), small \(\epsilon\), and \(Y=Z\), a one-component PCA
may preserve the higher-variance nuisance \(U\) and discard the low-amplitude
useful component. PCA chooses variance through covariance eigenvectors. A
supervised or target-shaped bottleneck chooses a different quantity and requires
its own temporal comparison. Heavy regularization likewise can erase thin signal.

## Isolate and confirm the representation's contribution

1. Build the as-of opportunities and actual instrument/cash mapping.
2. Bind target and attainable monitoring/exit policy from
   [decisions and labels](decisions-labeling.md).
3. Construct the small state panel and hand-check its formulas, units and
   cutoff validity on normal, missing, revised and contract-transition cases.
4. Hold label, model family, budget, scaling and splits fixed. Compare the panel
   against a simple control, then compare a justified added relation. This
   controlled addition/removal is an ablation.
5. Check held-out loss/ranking, calibration where used, and incremental economic
   role. Keep search and confirmation separate using
   [validation](inference-validation.md).
6. A repeated summary collision calls for additional state/ordering. A stable
   fit with no independent increment calls for target, source or relation review.
   Data finer than the decision requires adds acquisition and processing cost.

## Professional references

- Xu et al., [*A Theory of Usable Information Under Computational Constraints*](https://arxiv.org/abs/2002.10689), ICLR 2020. Restricted prediction and usable information.
- James et al., [*An Introduction to Statistical Learning*](https://www.statlearning.com/), second edition, 2021. Regularization, principal components and assessment.
- Gorton, Hayashi and Rouwenhorst, [*The Fundamentals of Commodity Futures Returns*](https://www.nber.org/papers/w13249), NBER working paper, 2007; published 2013. Economic background for inventory and commodity basis research; orientation and tradability remain task-specific.


## Worked applications

[State Representation](../examples/state-representation.md). Numerical settings are illustrative experiment bindings; the principles and change criteria above govern their use.
