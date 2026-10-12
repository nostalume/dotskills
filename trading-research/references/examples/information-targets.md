# Worked Information and Target Comparisons

These are constructed examples, not market estimates. General decisions live in
[prediction](../knowledge/prediction-information.md) and
[target design](../knowledge/decisions-labeling.md).

## A price fit can merely repeat today's level

At current price 100, let tomorrow's increment be equally likely +1 or -1.
Persistence predicts 100 and has mean squared error one. A predictor that repeats
the level also has that error, regardless of how closely its curve follows a
long, wandering price chart. A true increment prediction must improve the
appropriate independent comparison. Known price translation adds no forecast
information. No trade is an economic control, not a numerical forecast score.

## Weak Gaussian signal: precision versus direction

Let independent \(X,U\sim N(0,1)\), \(Z=0.05X+\sqrt{1-0.05^2}U\), and use
bin width \(\delta/\sigma=0.02\) for a fine numerical target. The governing
entry derives:

| Quantity | Calculation/result |
|---|---|
| Fine-bin entropy approximation | \(\tfrac12\log_2(2\pi e)-\log_2(0.02)=7.69095\) bits |
| Continuous information | \(-\tfrac12\log_2(1-0.05^2)=0.00180563\) bits |
| Sign information | \(1-E[h_2(\Phi(0.05X/\sqrt{1-0.05^2})))]\approx0.00114897\) bits |
| Optimal sign hit rate | \(1/2+\arcsin(0.05)/\pi=0.515922\) |
| Normalized information gain | \(0.00114897/(0.00180563/7.69095)\approx4.894\) |

The continuous information approximates the finite-grid information here; they
are not definitionally identical. Deterministic quadrature can evaluate the sign
integral. The reduced burden supports a direction-layer starting design while
discarding information some numerical consumers need. These figures do not
estimate IC, hit rate or profitability for a real market. Higher costs can make
this same forecast unusable.

## Breadth with and without dependence

For 100 equal-risk bets with per-bet mean/standard deviation ratio 0.05,
independence gives total ratio 0.5. Common pairwise correlation 0.1 gives effective
breadth \(100/(1+99\times0.1)=9.1743\), hence ratio about 0.15145. This valid
positive-correlation model shows why 100 stock rows are not 100 independent bets.
Different horizons, holdings and common exposures change the covariance model.

## A numerical consumer overrides the coarse default

Two proposed positions may have the same direction probability but different
conditional loss tails and required collateral. The class forecast can govern
participation, while magnitude/tail models govern payment and survival. Similarly,
an option hedge requires derivatives of a numerical value map. Replacing that
map by a sign class would remove its required operation. See
[price/Greek counterexample](pricing-paths.md).
