# Replication, Path State, and Greek Counterexamples

Synthetic contracts use [replication](../knowledge/pricing-replication.md),
[path state](../knowledge/volatility-paths.md) and
[numerical consumers](../knowledge/numerical-pricing-hedging.md).

## One-period call: physical probability is absent from cost

Stock 100 moves to 120 or 80. Cash gross factor is 1.05; call strike is 100,
paying 20 or zero. Replication holds delta 0.5 and cash
\(B=-40/1.05=-38.095238\). Cost is 11.904762. The pricing up weight is
\((1.05-0.8)/(1.2-0.8)=0.625\); discounted expected payoff is
\(0.625\times20/1.05=11.904762\). Both state payoffs reconcile exactly.
Changing the physical up probability changes forecasting but not this complete,
frictionless replicating cost. Costs/borrow constraints can reopen the construction.

## An unspanned payoff admits different prices

Three states have stock payoffs (80,100,120), current stock 100 and zero-rate cash.
Positive state weights (0.25,0.5,0.25) and (0.4,0.2,0.4) both price cash at one
and stock at 100. A payoff only in the middle state has prices 0.5 and 0.2.
Stock/cash do not span it. A unique estimate requires an additional traded claim
or explicit valuation assumption; network capacity does not close the market.

## Same endpoint, different Asian payoff

Monitor three prices, including the starting observation for this declared
contract. Paths (100,80,100) and (100,120,100) end alike; averages are 93.3333
and 106.6667. At strike 100, call payoffs are zero and 6.6667. Current spot alone
cannot price the remaining claim after the second observation. Running sum, count
and remaining schedule preserve the required distinction.

## Ordered integrals retain an order an endpoint loses

Two-coordinate path A moves (1,0) then (0,1); path B reverses the segments.
Both end at (1,1). The level-two formula gives A's \(S^{12}=1,S^{21}=0\),
and B's \(S^{12}=0,S^{21}=1\). One coordinate alone has level-two value
\((\Delta X)^2/2\) for either path, losing this distinction. At dimension three,
levels one through three require 3+9+27=39 coordinates, so retaining more order
has a representation/estimation cost. Specify interpolation and time before using
this as a market feature.

## Tiny price errors can carry unacceptable gamma

Let approximation error be \(0.001\sin(1,000x)\) on a normalized coordinate.
Value error is at most 0.001; first derivative error reaches one and second
derivative error reaches 1,000. Check physical units through the coordinate map.
With homogeneous value \(V=Kf(S/K)\), gamma is \(f_{xx}/K\); a small normalized
error cannot be accepted solely from its mean price score.

## Extra volatility exposure needs an instrument

Suppose stock shock loading is (1,0) and the claim's loadings are (0.5,2) in two
independent Brownian directions. Holding 0.5 stock cancels the first and leaves
two units of the second. A hedge option with loading (0.2,1) can span the missing
direction with two units, while stock adjusts to 0.1. The arithmetic identifies
exposure span; option liquidity, cost and model error still determine feasibility.

For fractional Brownian increments at H=0.25, lag-one covariance is
\((\sqrt2-2)/2\approx-0.292893\). This rough-increment example has anti-
correlation, not positive long-range dependence. It is a mathematical model,
not a fitted exponent or trading signal for any asset.
