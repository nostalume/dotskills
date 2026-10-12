# Executable Relations, Spread State, and Event Payments

These calculations are constructed. General methods are in
[arbitrage/events](../knowledge/arbitrage-events.md) and
[instrument context](../knowledge/market-instruments.md).

## Midpoints can hide an untradeable equality

Identical deliverable claims have A bid/ask 101/103 and B bid/ask 100/102, with
crossing cost 0.2. Selling A and buying B gives \(101-102-0.2=-1.2\), even
though A's midpoint exceeds B's. If A bid becomes 103, executable quoted gain is
0.8 before quantity, failed-leg, borrow and settlement constraints. Identical
reference names alone do not establish identical claims.

For a synthetic A→B→C→A currency cycle, executable rates are 2 B/A, 3 C/B and
0.17 A/C. Product is 1.02 A/A. A 1% fee per conversion gives
\(1.02\times0.99^3=0.98970498\), below one. Directions and units, not arbitrary
midpoint inversions, select the relevant conversion rates.

## Correlation does not establish convergence

Let B be a random walk U and A be U plus independent random walk V with small
innovation variance. The common component can make correlation high while
A−B remains a random walk. For an independently admitted AR(1) residual with
phi 0.8, center zero and current spread 3, seven-step conditional mean is
\(3\times0.8^7=0.6291456\), with mean half-life about 3.1063 steps.
The innovation sum remains, so neither value promises a hit or cash exit.

## Hysteresis requires holding state and quantities

Initial binding: flat entry beyond z=±2; held exit when |z|≤0.5; separate maximum
horizon, cash/loss/relation-break responses. At z=1, a flat state waits; a prior
short-spread state continues under this policy. Freeze thresholds and horizon in
development and retain rejected/no-fill cases.

At A=100, B=50 and log-spread coefficient beta=1.5, exposure scale k=1,000 maps
locally to ten A units and -30 B units. Using (1,-1.5) shares would not represent
that declared log-spread sensitivity. Currency, multiplier, distributions and
rebalancing need the actual ledger.

## Completion probability is not enough without failure value

An event stock is 90, success pays 100, failure 60 and fixed-horizon cost is 2.
Required probability is \((90+2-60)/(100-60)=0.8\). At p=0.85, expected net
payment is 2. If failure value falls to 40 with the same p, expected payment is
-1, so the decision changes. Located text can establish offered terms; calibrated
probability and failure/time assumptions need their own evidence.

For dated payments, use discount factors and outcome-specific times. A six-month
lockup and a one-month resolution consume different financing and capital even
when nominal expected payment matches. A model trained after the historical event
may know the resolution; an old source excerpt does not erase model-knowledge
leakage. Restrict the model to auditable extraction or use a defensible time-bound
prediction route.

## A wrapper discount may be a stale hedge reference

Assume a token trades at 95 while its economically linked share's last close is
100. The share market is closed and no contractual share conversion is presently
available. Tomorrow's share quote can open at 94; shorting the old 100 was never
an attainable hedge. Before labeling a hard arbitrage, resolve issuer claim,
conversion fees/permissions, distributions, live executable reference and both
settlement clocks. Without them, retain a descriptive discount and uncertain
convergence hypothesis. The same procedure applies to future-linked tokens whose
expiry/roll differs from the quoted reference contract.
