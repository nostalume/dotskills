# Execution, Financing, and Path Survival

Use this entry when a forecast, allocation or price relation must become a net
cash outcome. Begin with a chronological inventory/cash replay and small accounting
fixtures. Add fill detail where it can change the result. A favorable terminal
payoff requires a feasible path of orders, fills, collateral and settlement.

## Chronology determines attainable labels and outcomes

Bind source event time, information availability, signal cutoff, order release,
acceptance, fills, settlement and outcome maturity. A close-derived signal normally
cannot receive that same close without a documented admissible order mechanism.
For a stop, the observed trigger chooses the next action; its fill is a later
event, possibly beyond the trigger price. Bars touching both barriers leave hit
order unresolved. Admit finer observations or a frozen ambiguity treatment; a
favorable assumed ordering is a selected modeling choice.

Separate market eligibility from actual acceptance and fills. An unavailable
borrow, halt, quantity rejection or adverse gap remains an opportunity outcome
under the declared policy. It must not disappear because the realized trade
would have been inconvenient. [Labels](decisions-labeling.md) retain their policy,
signed payouts, timeout and maturity semantics.

## Derive the ledger invariant

For a cash asset, current units \(q\), execution price \(p\), change \(\Delta q\)
and cash \(C\), an immediate fill updates

\[
q^+=q+\Delta q,\qquad C^+=C-p\Delta q-c(\Delta q).
\]

Marked at the same price, wealth \(E=C+pq\) changes by \(-c\): the two inventory
terms cancel. With no fees, same-price rebalancing cannot create wealth. A dividend
adds its cash entitlement to cash; a split changes quantity and price consistently.
Adjusted data can support return measurement, while actual quantities/cash need
the physical corporate-action bridge. Avoid adding a dividend again to a total-
return series. Borrow accrual, financing, foreign-exchange cash and liquidation
proceeds are separate dated events.

Futures normally exchange collateral and variation rather than full spot notional.
For a declared linear contract, holding \(q\) contracts with multiplier \(m\)
across settlement prices gives variation \(qm(F_{k+1}-F_k)\). Record its payment,
collateral transfers, fees and funding. Posting margin transfers cash to collateral;
it is not itself a trading loss. Do not mark settled gains again as an unsettled
asset. Between settlements, the linear contract's remaining mark contribution is
\(qm(F_t-F_{\rm last\,settlement})\); at settlement that contribution moves to cash
and its basis resets. Reconcile accessible cash, posted collateral and remaining
unsettled value once each. Inverse/nonlinear contracts require their own payout
and collateral units.
A continuous adjusted future is a signal representation; rolling holdings means
closing one actual contract and opening another with their own prices and cash.

Pre-rebalance holdings drift. With fully invested initial weights \(w_i\) and
one-period simple returns \(R_i\), before costs/cash flows,

\[
w_i^-=\frac{w_i(1+R_i)}{1+\sum_jw_jR_j}.
\]

Numerator is the new asset value and denominator the new total value. Required
turnover uses target minus \(w^-\), not target minus yesterday's target. Cash,
leverage and flows call for the more general ledger rather than this restricted
formula. Check inventory and wealth after every event before comparing returns.

## Derive participation, capacity and a trading band

For nonnegative quantity \(q\), illustrative expected gross advantage \(gq\),
linear cost \(cq\), and impact \(aq^2\), \(a>0\), expected net gain is
\((g-c)q-aq^2\). Its derivative gives \(q^*=(g-c)/(2a)\) if \(g>c\), otherwise
zero, then apply limits. Here \(g,c\) are currency per unit and \(a\) currency
per squared unit. The quadratic is a teaching cost model, not an exchange law.
Estimate costs conditional on spread, liquidity, participation, session and stress;
test a frozen size ladder before increasing capacity claims.

Suppose an unconstrained desired holding is \(q^*\), deviation costs
\(k(q-q^*)^2/2\), \(k>0\), and changing inventory from \(q^-\) costs
\(c|q-q^-|\). Away from the kink, differentiating gives
\(q=q^*-c/k\) for buying and \(q=q^*+c/k\) for selling. At the kink the
left/right derivatives straddle zero when \(|q^*-q^-|\le c/k\). This creates
a no-trade band. Signal updates therefore need not force immediate rebalancing.
The coefficients, actual fill constraints and evidence determine its useful scale.

## Multi-leg trades carry residual exposure

Track each leg's submitted, accepted and filled quantity. A successful first leg
with a failed second leg produces an outright position, not the intended spread.
Freeze timeout/cancel, fallback hedge, maximum residual exposure and cost treatment.
Evaluate leg order against inventory, depth and the cost of failure. A quoted
cross-venue spread needs prefunded assets/cash or a verified delivery path; assumed
instant transfers can erase the opportunity and its financing risk.

Let \(E_t\) be marked equity, \(M_t\) required collateral, and \(A_t\) cash
actually accessible by the deadline. A strategy can have \(E_T>E_0\) yet fail
when \(A_t<M_t\) or maintenance equity is breached earlier. Segregated spot gains
or a receivable on another venue cannot pay a local call before transfer/settlement.
Stress adverse gaps, widened basis, haircut increases, rejected transfers,
withdrawal suspension and forced exits. These are separate from direction accuracy.

## Usual practice path

1. Freeze the executable policy and temporal/fill convention. Start at a grain
   that can resolve its required order and liquidity distinctions.
2. Replay actual instruments, inventory, cash, funding and collateral. Reconcile
   unchanged-price rebalance, one distribution, one settlement and one roll.
3. Add rejected/partial/gap cases and multi-leg residual management. Retain failed
   opportunities in the comparator population.
4. Apply inventory-aware trade bands, risk and accessible-cash limits. Test net
   outcomes across a frozen size ladder and stress paths.
5. Confirm versus cash/no trade or a feasible benchmark. An offline result does
   not authorize account access, orders or future fill claims.

Worked ledger and path failures: [cash and funding examples](../examples/cash-funding.md).
Historical mechanisms: [institutional experience](../examples/institutional-experience.md).
Execution background: [Almgren and Chriss](https://doi.org/10.21314/JOR.2001.041).
