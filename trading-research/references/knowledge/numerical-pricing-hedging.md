# Numerical Pricing, Surrogates, and Friction-Aware Hedging

Use this entry to choose a computation for a fixed valuation/risk task or to test
a discrete hedge policy. Establish a reference oracle and consumer tolerances
first. A learned approximation earns replacement through physical-unit error,
coverage, fallback and complete-route cost. A learned hedge earns a role through
its self-financing ledger and specified risk comparison.

## Budget reference errors before creating labels

For independent discounted payoff samples \(Y_j\), estimator
\(\widehat V=N^{-1}\sum_jY_j\) has variance \(\operatorname{Var}(Y)/N\).
An asymptotic normal half-width \(z\widehat s/\sqrt N\) motivates
\(N\gtrsim z^2s^2/\epsilon^2\) at price precision \(\epsilon\). Check its
finite-sample/tail applicability; dependent paths require another uncertainty law.
Time/monitoring discretization bias does not disappear when paths increase.
If verified weak bias behaves as \(Ch^p\), reducing \(h\) addresses it; paired
step refinements estimate the behavior, not a universal order for discontinuous
payoffs. Keep sampling, discretization, derivative and approximation errors separate.

For discretized expectation \(V_h\) and payoff variance \(v_h\),
\(\widehat V-V=(\widehat V-V_h)+(V_h-V)\). Squaring and averaging removes the
cross term because the sample mean is unbiased for \(V_h\), giving
\(E[(\widehat V-V)^2]=v_h/N+(V_h-V)^2\). This is numerical sampling plus bias;
market-model discrepancy is an additional question.

For a control \(Z\) with known mean, use
\(Y-\beta(Z-EZ)\). Expand its variance and minimize the quadratic to get
\(\beta=\operatorname{Cov}(Y,Z)/\operatorname{Var}(Z)\), reducing variance to
\(\operatorname{Var}(Y)(1-\rho^2)\). Estimate beta on a separate pilot or account
for estimation in the result. Antithetic pairing, conditional expectation and
common random numbers for comparisons have different premises. Price labels
retain standard errors and simulation lineage; path count is not a quality label.

## Preserve the derivatives the consumer needs

For a scale-homogeneous contract, \(V(S,K,\tau)=Kf(S/K,\tau)\) can remove a
redundant scale. Differentiate explicitly:
\(\Delta=f_x\), \(\Gamma=f_{xx}/K\). Check homogeneity with all cash flows,
barriers, fees and model inputs; a fixed cash amount can break it.

Value error \(e(x)=\epsilon\sin(\omega x)\) is at most \(\epsilon\), while
derivative errors reach \(\epsilon\omega\) and \(\epsilon\omega^2\). A good
average price fit can therefore fail delta/gamma. If smoothness and parameter-
independent path sampling permit it, differentiate the payoff pathwise and
interchange expectation/derivative under an integrable bound. Nonsmooth events,
moving barriers or parameter-dependent sampling may require likelihood-ratio,
smoothing or controlled finite-difference estimators. Automatic differentiation
does not establish that a simulated derivative is the desired Greek.

A smooth surrogate may use supervised value/Greek losses after each component is
scaled by its declared physical tolerance. Check maximum and regional errors,
near-expiry/strike/barrier cases, positivity, monotonicity/convexity where the
contract implies them, terminal/boundary values and outside-domain refusal.
PDE residual, payoff boundary and shape are separate gates: even a zero residual
with wrong boundary conditions can price the wrong claim. An optimizer changes
fit geometry, not the financial identity or a function-level shape guarantee.
For the classical non-dividend vanilla call, concrete checks include
\(\max(S-Ke^{-r\tau},0)\le V\le S\), \(0\le\Delta\le1\), and
\(\Gamma\ge0\). These follow from the replicable payoff bounds and monotone/
convex payoff expectation in that model. Other products require their own bounds.

## A usual surrogate pilot

1. Bind contract/model/calibration version, domain, state and price/delta/gamma
   tolerances. Use closed form, tree/grid or budgeted Monte Carlo as reference.
2. Create bounded domain training/development/final inputs and independent
   boundary/stress suites. Split parameter regions/path seeds as the intended
   generalization requires. Reference noise receives a smaller error budget.
3. Start with a small smooth network and normalized inputs/value. Add reliable
   derivative supervision where needed, early stop on development and freeze
   loss weights/step/budget before final evaluation. [Pilot bindings](../examples/surrogate-hedging.md)
   give an initial workload, not an optimum.
4. Evaluate each physical consumer and fallback, including matched hedge outcome.
   Failed gamma or boundary gates cannot be excused by small mean value error.
5. Compare full generation, training, refresh, validation, inference and fallback
   cost with the reference at identical tolerances/hardware/batch conditions.

With offline cost \(C_o\), reference cost \(C_r\), surrogate cost \(C_s<C_r\),
adoption saves work after \(N>C_o/(C_r-C_s)\) calls. If a fraction \(\rho\)
requires reference fallback in addition to attempted inference, replace \(C_s\)
by \(C_s+\rho C_r\); a nonpositive remaining saving means no crossover.
Batch throughput and single-request latency are different observations. Claimed
proprietary speeds need a matched benchmark/model card before adoption.

## Derive a hedge objective from actual wealth

For a sold claim discounted payoff \(\widetilde H\), initial capital \(v_0\),
hedge units \(q_k\) chosen before the next shock, and discounted hedge prices,

\[
E_T=v_0+\sum_{k=0}^{m-1}q_k(\widetilde S_{k+1}-\widetilde S_k)
-C(q)-\widetilde H.
\]

One proportional cost model is
\(C(q)=\sum_kc\widetilde S_k|q_k-q_{k-1}|\), \(q_{-1}=0\). State whether
terminal liquidation is charged; cash interest, collateral and other hedge assets
need their own ledger. The gain identity follows from self-financing inventory
updates, not from adding mark-to-market changes after subtracting notional again.
Set loss \(L=-E_T\). Mean-square loss and a tail-risk objective express different
desk preferences; capital and constraints remain user/project-owned.

For tail probability \(1-\alpha\), minimize over threshold \(z\)

\[
z+\frac{1}{1-\alpha}E[(L-z)^+].
\]

Its derivative away from atoms is
\(1-\Pr(L>z)/(1-\alpha)\), so an interior optimum is an \(\alpha\)-quantile.
Substitution yields the upper-tail average for a continuous law. With atoms use
subgradients and the generalized conditional-value-at-risk definition. Simulation
tail counts and law misspecification govern uncertainty; a trained policy does
not certify an unseen crisis.

Adding premium \(p\) changes loss to \(L-p\). Substitute \(y=z+p\) in the
threshold objective: it becomes the old objective at y minus p. Thus CVaR shifts
by \(-p\). If optimized risks with and without the short claim are \(R_H,R_0\)
before extra premium, \(p=R_H-R_0\) equalizes this criterion on the same permitted
market. This risk-indifference value depends on preferences and constraints;
frictionless complete replication can have a different valuation scope.

**First comparison:** discrete model delta, with the same dates, costs, initial
capital and risk/cash constraints. Give a proposed policy current hedge inventory,
remaining time, attainable market/model state and relevant path accumulator.
An inventory-aware band is a low-complexity friction control. Compare cost, hedge
error, tail loss, collateral and boundary behavior on independent paths and stress
laws. Train or adjust only when that control leaves a meaningful supported gap.

Examples: [surrogate and hedge pilot](../examples/surrogate-hedging.md).
Background: [Huge and Savine](https://arxiv.org/abs/2005.02347),
[Raissi et al.](https://arxiv.org/abs/1711.10561),
[Bühler et al.](https://arxiv.org/abs/1802.03042), and
[Rockafellar and Uryasev](https://doi.org/10.21314/JOR.2000.038).
