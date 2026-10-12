# Risk Budgets, Environmental Coverage, and Bounded Overlays

Use [portfolio principles](../knowledge/portfolio-risk.md). Calculations are
synthetic; the allocation experiment is unexecuted and is not an investment
recommendation or reproduction of institutional holdings.

## Independent risks distinguish the allocation rules

Two assets have annualized volatility 0.2 and 0.1 and zero correlation. Equal
capital puts 80% of variance contribution in the first asset. Equal-budget ERC
weights are \((1/3,2/3)\); each variance contribution is \(0.0044444\) and total
variance is \(0.0088889\). Minimum-variance unit-budget weights are \((0.2,0.8)\),
because they scale with inverse variance, not inverse volatility.

For any valid covariance Sigma and positive c, if x solves risk budgeting,
\(y=x/\sqrt c\) solves it for c Sigma. Normalization removes the common scale.
Annualizing covariance changes estimated volatility units, not normalized ERC
weights. Singular/indefinite estimates or solver residual failures require repair.

## Asset balance can retain one common shock

Let \(r_1=z+e_1,r_2=z+e_2\), with independent unit-variance components. Covariance
is \(\begin{pmatrix}2&1\\1&2\end{pmatrix}\); symmetry gives equal-weight ERC.
Portfolio return is \(z+(e_1+e_2)/2\), variance 1.5, of which one is the common
shock. Asset contributions are equal, but the shock was not diversified away.
Scenario coverage therefore deserves a separate exposure/stress diagnostic.

## A modest trend overlay changes risk shares

Multiply the independent-assets ERC weights by 1.15 and 0.85 and normalize. New
weights are \((23/57,34/57)\). First-asset variance share becomes
\(4\times23^2/(4\times23^2+34^2)\approx0.6467\), no longer 0.5. A bounded
tilt still changes the base budget. Recompute shares, cash requirements and net
turnover before comparing its incremental value.

## A first All Weather-inspired experiment

Select historically eligible proxies for equities, nominal government duration,
inflation-linked government debt and diversified commodities. Gold is a separately
justified fifth comparison. The supplied four-proxy equity/long-duration/commodity/
gold variant is also a useful control, but it omits explicit inflation-linked
debt and does not map four tickers to four independent economic quadrants.
Resolve currency, distributions, duration, rolls, trading rights and costs first.

Begin with 252 completed sessions, covariance shrinkage toward average sample
variance times identity, positive equal budgets and monthly later-feasible
rebalancing. Freeze a first shrinkage binding (illustratively 0.2) and declare
the development comparison before tuning it. Keep equal capital and inverse-
volatility controls. Use a coordinate or damped-Newton solver with positive iterates
and a risk-share residual tolerance (illustratively \(10^{-6}\)); inspect cash,
exposure caps and any resulting deviation from exact budgets.

Stress growth disappointment, inflation surprise, joint equity/nominal-duration
loss, commodity reversal, real-rate shock, correlation change and funding withdrawal.
Shock labels guide tests; they do not guarantee every asset's sign. Only after
the base comparison, add an optional 50/200-session moving-average overlay with
1.15/0.85 tilts. Treat it as a predictive supplement and independently confirm
net increment. ERC plus an overlay is not unchanged ERC or a macro-free strategy.

Bridgewater's account motivates separate beta/alpha and exposure coverage. The
public experiment above is independently specified. Institutional-source scope is
in [practice accounts](institutional-experience.md).
