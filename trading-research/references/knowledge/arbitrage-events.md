# Arbitrage Relations, Event Outcomes, and Carry

Use this entry when the opportunity rests on equal cash flows, uncertain
convergence, a corporate event or a funding relation. First build the actual legs,
units and cash path. Equal cash flows lead to executable price inequalities;
statistical convergence needs a dynamic model; an event needs probability,
conditional payouts and time. These are different starting constructions.

## Replication begins with deliverable cash flows

If two attainable portfolios produce identical dated cash flows in every admitted
state, buying the cheaper and selling the dearer produces a positive initial
receipt with no residual modeled payoff. Quotes must be executable on opposite
sides, with fees, borrow, settlement, currencies and delivery rights included.
For identical claims A and B, a usable crossing is \(bid_A>ask_B+c\), not a
mid-price difference. Quantity limits, failed legs and inaccessible cash can defeat
the construction; [execution](execution-funding.md) supplies their replay.

For a currency triangle, each rate has a unit: if \(r_{AB}\) is B received per
unit A, the A→B→C→A conversion returns \(r_{AB}r_{BC}r_{CA}\) units A per A.
Use executable conversion rates for those directions and multiply fee-retention
factors. A product above one is a modeled gross cycle, whose depth, synchronization,
inventory and settlement determine executable value. Public equality can remove
the forecasting task while leaving infrastructure, access and inventory as the edge.

## Correlation is weaker than a stable residual

Let \(B_t=U_t\), \(A_t=U_t+V_t\), with independent random walks and small
innovation variance for V. Correlation can be near one while \(A_t-B_t=V_t\)
remains nonstationary. A cointegrating relation instead leaves a stable residual
from nonstationary levels. This is an empirical restriction to test over the
formation/confirmation history, not a conclusion from a large correlation.

For an admitted residual \(Z_t\), a teaching dynamic model is
\(Z_{t+1}-m=\phi(Z_t-m)+\epsilon_{t+1}\), \(|\phi|<1\), with zero conditional
mean innovations. Iteration gives

\[
Z_{t+h}-m=\phi^h(Z_t-m)+\sum_{j=1}^h\phi^{h-j}\epsilon_{t+j}.
\]

The expectation shrinks, but the shock sum remains. For \(0<\phi<1\), the
mean half-life solves \(\phi^h=1/2\), so \(h=\ln(1/2)/\ln\phi\).
Negative \(\phi\) describes alternating decay, not monotone convergence.
Estimate a relation on past-only formation data, freeze it for the test interval,
inspect residual dynamics/breaks and count searched pairs/windows. Standard
cointegration test critical values differ from a naive regression t test; use a
maintained method with its intercept/trend/lag assumptions bound to the study.

Start with stateful hysteresis: flat observations beyond an entry threshold can
open a spread; held observations enter a narrower exit band; horizon, loss,
relation-break and cash limits terminate or suspend under a frozen policy. The
same score can imply waiting while flat and continuing while held. Thresholds
are development bindings in the [spread example](../examples/relations-events.md),
not intrinsic values. Record reestimation and treatment of already-open holdings.

For price-level spread \(A-\beta B\), one spread unit has quantities
\((1,-\beta)\) after currency/multiplier conversion. For
\(Z=\ln A-\beta\ln B\), \(dZ=dA/A-\beta dB/B\) suggests local quantities
\((k/A,-k\beta/B)\) for currency exposure scale \(k\). Log coefficients
are not share counts; changing prices and rehedging change cost and cash.

## Event probability is conditional payment, not a text score

For current price \(P\), success value \(V\), failure value \(F\), success
probability \(p\), and total cost \(c\), fixed-horizon net expectation is
\(pV+(1-p)F-P-c\). With \(V>F\), participation requires
\(p>(P+c-F)/(V-F)\). Conditional failure prices, financing and probability
uncertainty matter as much as nominal completion accuracy. If completion time
\(\tau\) is random, compare discounted state-contingent payments
\(E[D(\tau)H_\tau]\) and cash accessibility; using one average time ignores
correlation between time and outcome. Lockup duration also consumes capital.

The first text product is an as-of event dossier: located terms, actors,
conditions, dates, source provenance and discrepancies. An extracted fact is not
a calibrated completion probability. Historical research needs both document
availability and a model whose knowledge/corpus does not reveal later outcomes.
A contemporary language model can leak a historical event's resolution even when
given an old document. Use defensible time-bounded data/models or restrict it to
auditable extraction; then train and confirm forecasts from eligible historical
events. Serving/quantization improvements affect extraction cost, not event alpha.
Work one event end to end before scaling entity resolution or model serving.

## Carry and funding retain delivery and basis risks

Borrow \(S_0\) at continuous rate \(r\), buy one deliverable non-dividend spot
unit, and sell a forward at \(F_0\). Terminal cash is
\(F_0-S_0e^{rT}\). A feasible reverse construction gives the opposite bound,
forcing \(F_0=S_0e^{rT}\) only in the frictionless two-sided setting. A known
dividend's present value reduces the financed spot cost; storage, borrowing,
delivery quality and convenience benefits change commodity relations. A token
that tracks a future can have different expiry, roll, cash and redemption rights;
it is not automatically the deliverable underlying.

For one spot unit long and one compatible linear perpetual unit short, let
\(b_t=F_t-S_t\), and let \(f_k\) be signed funding received by the short:

\[
\Pi_T=(S_T-S_0)+(F_0-F_T)+\sum_kf_k-c
=b_0-b_T+\sum_kf_k-c.
\]

Positive current funding leaves future basis and funding signs uncertain. Near-zero
total delta leaves venue-specific margin calls. Freeze mark/index, funding clocks,
collateral haircuts/tiers, liquidation and transfer terms for the actual product;
an offsetting gain elsewhere may miss the local deadline. Custody/default risk
remains even with a reconciled arithmetic hedge.

## Usual practice paths

**Hard relation:** cash-flow rights and currencies → executable bid/ask legs →
fees/depth/borrow/prefunding → residual-leg replay → net inequality and stress.

**Statistical spread:** related instruments → as-of population → frozen relation →
residual dynamics → stateful policy/horizon → quantity conversion → actual fills,
funding and net independent confirmation.

**Event:** historical eligible events → as-of dossier → calibrated outcome/time
forecast → conditional payment threshold → capital/failure path → complete-route
confirmation against no position and a simple event control.

**Funding:** one eligible spot/linear pair → realized basis/funding observations →
prefunded ledger → widening/reversal/transfer/default stress → net comparison.
Add forecasting only for a measured improvement in that consumer.

Worked deductions: [relations and events](../examples/relations-events.md) and
[cash/funding](../examples/cash-funding.md). Instrument distinctions:
[market context](market-instruments.md).
Background: [Engle and Granger](https://doi.org/10.2307/1913236),
[Gatev et al.](https://www.nber.org/papers/w7032).
