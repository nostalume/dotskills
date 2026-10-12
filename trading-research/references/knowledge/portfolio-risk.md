# Portfolio Construction and Risk Allocation

Use this entry to convert a forecast into feasible holdings. The first route is
payoff participation plus capped inverse-volatility size for timing; constrained
active weights for relative selection; stabilized risk budgets for allocation
without a supported mean edge. A solved optimizer cannot make uncertain inputs
accurate. Check the realized holdings and funding path after solving.

## What the optimizer actually uses

For return vector \(r\), holdings as equity-relative return exposures \(w\),
mean \(\mu\) and covariance \(\Sigma\),
\(E[w^Tr]=w^T\mu\) and \(\operatorname{Var}(w^Tr)=w^T\Sigma w\).
The unconstrained quadratic utility
\(w^T\mu-\lambda w^T\Sigma w/2\), \(\lambda>0\), has solution
\(w=\Sigma^{-1}\mu/\lambda\) for positive-definite \(\Sigma\).
Linearizing its first-order condition gives

\[
\delta w\approx\lambda^{-1}\Sigma^{-1}\delta\mu
-\Sigma^{-1}(\delta\Sigma)w.
\]

In an eigenvector with covariance eigenvalue \(d\), mean error is amplified by
\(1/(\lambda d)\). Small sample eigenvalues and thin mean evidence therefore
create unstable large bets. Use a mean estimate when independent evidence
supports its consumer; otherwise begin with a risk-only route. Shrink covariance
as \((1-a)\widehat\Sigma+a\tau I\), with \(0<a\le1,\tau>0\), to bound its
smallest eigenvalue below by \(a\tau\) when the sample estimate is positive
semidefinite. Shrinkage also changes the estimated risks; select it on development
and stress evidence rather than equating conditioning with truth.

## Derive risk budgeting and a checkable solver

Portfolio volatility \(\sigma_p=\sqrt{w^T\Sigma w}>0\) has derivative
\((\Sigma w)_i/\sigma_p\). Its Euler contribution is
\(RC_i=w_i(\Sigma w)_i/\sigma_p\); summing recovers \(\sigma_p\).
For positive budgets \(b_i\) summing to one, seek
\(w_i(\Sigma w)_i=b_iw^T\Sigma w\).

For positive-definite covariance, minimize on \(x_i>0\)

\[
f(x)=\tfrac12x^T\Sigma x-\sum_i b_i\ln x_i.
\]

Stationarity gives \(x_i(\Sigma x)_i=b_i\). Summing yields
\(x^T\Sigma x=1\). Normalize \(w=x/(\mathbf1^Tx)\); both sides of the
risk-budget equations scale quadratically, so the normalized weights have the
desired shares. The Hessian \(\Sigma+\operatorname{diag}(b_i/x_i^2)\) is
positive definite. The objective rises at a zero component and at infinity,
so the unique positive solution is attainable under these assumptions.

A coordinate update holds all other coordinates fixed. Let
\(c_i=\sum_{j\ne i}\Sigma_{ij}x_j\). Solve
\(\Sigma_{ii}x_i^2+c_ix_i-b_i=0\), taking its positive root. For \(c_i\ge0\),
use \(2b_i/(c_i+\sqrt{c_i^2+4\Sigma_{ii}b_i})\) to avoid cancellation;
for negative \(c_i\), the usual quadratic numerator is stable. Cycle within a
declared iteration budget and check stationarity, weight feasibility and risk-share
residuals. Damped Newton with positive iterates and backtracking is another route.
Caps or turnover constraints can prevent exact budgets: report achieved residuals.

With diagonal covariance, budgets give \(w_i\propto\sqrt{b_i}/\sigma_i\).
Equal risk contribution (ERC) therefore uses inverse volatility. Minimum variance
under a unit budget instead uses inverse variance in this diagonal case. Equal
capital, ERC and minimum variance answer different questions.

## Relative forecasts need holding constraints

For benchmark \(w_b\), active weight \(a=w-w_b\), standardized score \(s\)
and drifted current holdings \(w^-\), a first convex construction is

\[
\min_w -s^T(w-w_b)+\tfrac\lambda2a^T\Sigma a
+\kappa\|w-w^-\|_1.
\]

Require the budget, available long/short permissions, name bounds, turnover limit
and chosen exposure constraints \(B^Ta=0\). A rank score is an ordering, not
an expected-return unit: fix its scaling before interpreting \(\lambda,\kappa\).
Feature neutralization does not guarantee neutral holdings after nonlinear
selection and caps. Check exposures on solved and actually filled positions.
Compare with a feasible ranked basket and benchmark, net of the same costs.

## Environmental balance: apply the All Weather insight

Bridgewater's institutional account separates cash, beta and alpha and motivates
balancing exposures to growth and inflation surprises. It includes inflation-linked
bonds as a distinct exposure. This provides a structural allocation rationale,
not a public specification of proprietary holdings.
[Bridgewater's account](https://www.bridgewater.com/research-and-insights/the-all-weather-story).

The allocation's economic rationale is diversified exposure to compensated risks,
with protection chosen for the investor's needs. Risk premia are expected
compensation for bearing risk, not certain next-period receipts. Asset/contract
evidence and long-horizon comparisons must support that rationale; covariance
balancing itself creates no expected return. Lack of a confirmed tactical mean
forecast therefore motivates a risk-budget baseline rather than implying that
every asset has zero premium. Compare cash or the feasible policy benchmark
according to the investor's declared objective.

Construct an exposure diagnostic \(r=Az+\epsilon\), where \(z\) contains
economic surprises and \(g=A^Tw\). Then explanatory risk is
\(g^T\operatorname{Cov}(z)g\). With independent shock coordinates it becomes
\(\sum_k d_kg_k^2\). Residual risk and cross-covariances remain in total risk.
Asset ERC equalizes Euler asset contributions; it need not equalize this shock
risk or losses in four scenarios. Two assets \(r_1=z+\epsilon_1\),
\(r_2=z+\epsilon_2\), all independent unit-variance components, have equal-weight
ERC but retain full exposure to \(z\).

**Starting allocation:** cover distinct economic sensitivities first, stabilize
covariance and compute equal risk budgets second, then stress common adverse
shocks, liquidity and financing. A four-ETF equity/bond/commodity/gold baseline
is an inspectable approximation, not four independent quadrants; gold is not a
universal deflation payoff. Inflation-linked debt can expose a missing inflation
dimension but retains real-rate/duration risk. Historical co-losses and omitted
shocks determine whether additional coverage is needed.

A trend overlay is a predictive policy. Multiplying ERC weights by bounded trend
tilts and renormalizing changes risk contributions. Recompute them and compare
base versus overlay with the same costs. Leverage scales asset contributions
proportionally before funding effects; it also introduces cash-path constraints.
No structural balance ensures small drawdowns in every environment.

## Size after participation

For exposure \(q\), \(\operatorname{sd}(qR)=|q|\widehat\sigma\), motivating
\(|q|=v/\widehat\sigma\) for target risk \(v\), subject to leverage, liquidity
and cash caps. Futures contract count is approximately \(qE/(mP)\), with equity
\(E\), multiplier \(m\) and positive price \(P\); round under a fixed rule.
Small/invalid volatility never removes caps. For a stylized binary wealth gamble
with gain multiple \(b>0\), fraction \(f\) and success \(p\), expected log growth
is \(p\ln(1+bf)+(1-p)\ln(1-f)\). Differentiation gives
\(f^*=[pb-(1-p)]/b\), clipped to the permitted domain. This Kelly construction
depends on the complete payout law and repeated wealth model. Probability alone
does not specify live size; uncertain probabilities, loss tails and deadlines
require more restrained exposure and stress checks.

## Usual practice path

Bind payout and feasible holdings → choose timing, active or risk-budget route →
estimate past-only risk with stabilization → solve and check residuals → use
drifted inventory for actual trades → replay cash/collateral → compare feasible
controls and confirm the complete route. Diagnose excessive common exposure,
estimate instability and cash shortfall separately before adding forecasts.

Worked allocations: [ERC, environmental coverage and overlays](../examples/risk-allocation.md).
Professional context: [Markowitz](https://doi.org/10.1111/j.1540-6261.1952.tb01525.x),
[Ledoit and Wolf](https://www.ledoit.net/Well-conditioned2004.pdf),
[risk-budget formulations](https://portfoliooptimizationbook.com/book/11.6-vanilla-convex-formulations.html),
and [Kelly](https://doi.org/10.1002/j.1538-7305.1956.tb03809.x).
