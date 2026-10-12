# A Numerical Surrogate and Hedge Pilot

This is an unexecuted experiment specification with synthetic arithmetic checks.
Use [numerical pricing/hedging](../knowledge/numerical-pricing-hedging.md) for the
governing derivations and adoption criteria.

## Reference precision before training

For independent discounted payoff standard deviation 12 currency units, target
normal-approximation price half-width 0.05 and z=1.96, a fixed final count suggestion
is \((1.96\times12/0.05)^2=221,276.16\), rounded up to 221,277 paths. Pilot
variance uncertainty and tail/normal-approximation validity remain. Increasing
paths does not remove time/monitoring bias. Compare step refinements with enough
sampling precision to detect their difference; retain the actual contract schedule.

For an oracle sampling standard error 0.002, discretization error budget 0.002
and approximation tolerance 0.006 in currency, a deterministic error bound cannot
simply treat the sampling standard error as a certain maximum. State the confidence
policy and combine statistical and deterministic allowances at their own scope.
Labels carry their standard errors/seed lineage, including Greek-label error.

## Initial smooth approximation

Bind a model, contract, bounded domain and fallback. Price tolerance 0.01 currency
is a teaching starting requirement; set physical delta/gamma tolerances from the
consumer before labels are generated. Begin with 20,000 training inputs, 2,000
development inputs and 2,000 final inputs, plus distinct boundary/stress suites.
They specify a workload, not adequate coverage by theorem.

Use two hidden layers of width 64, tanh, normalized inputs and a linear normalized-
value output. Apply homogeneity only when the contract admits it. Use reliable
value/delta supervision and a separate gamma gate or gamma supervision. Begin Adam
at 0.001, batch 256, epoch cap 200 and development early stopping. Normalize loss
components using their tolerances; freeze weights/stopping before final evaluation.
Linear output leaves positivity/shape to checks and fallback.

Inspect regional value and Greek errors, near-expiry/strike/barrier behavior,
terminal/boundary/shape constraints and outside-domain requests. Compare the full
reference/surrogate route at matched accuracy and resources. A failed gamma gate
rejects replacement for that consumer even with a small average price error.

## Speed needs repeated use and a fallback budget

Offline cost 10,000 seconds, reference 0.02 seconds/call and surrogate 0.0001 give
crossover \(10,000/(0.02-0.0001)\approx502,512.56\), so savings begin above that
call count. If 10% require reference fallback in addition to attempted inference,
effective online cost is 0.0021 and crossover about 558,659.22. Model recalibration
can incur another refresh. These assumed costs are not measured performance.

## Hedge wealth and tail-risk fixtures

Initial premium 5, constant hedge 0.5 over discounted stock prices 100→110→105,
and terminal claim payout 6 give zero-cost terminal surplus
\(5+0.5(10)+0.5(-5)-6=1.5\). Charge initial proportional hedge cost at rate
0.01: \(0.01\times100\times0.5=0.5\); surplus becomes one if terminal liquidation
is excluded. Charging terminal liquidation adds 0.525 and leaves 0.475. Terminal
conventions therefore change the objective even for identical holdings.

Loss zero with 95% probability and 20 with 5% probability has mean one and CVaR
at 0.95 equal to 20; constant loss one has the same mean and CVaR one. For the
first law, the threshold objective is 20 for every z between 0 and 20. An extra
premium p shifts losses and CVaR down by p. A risk-indifference premium compares
optimized risks with/without the claim on the same permitted market; it need not
equal a unique replication price in an incomplete/frictional setting.

First compare no hedge, discrete model delta and a delta/no-trade-band control
under identical capital, dates, cost, law and constraints. A small learned policy
receives current inventory, contract/path state and remaining time. Compare
hedge error, tail loss, turnover, funding and stress-law behavior on independent
paths. Synthetic success leaves actual market dynamics and tails to their own
evidence.
