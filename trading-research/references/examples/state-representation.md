# Representation, Availability, and Concept Fixtures

Constructed examples support [data/representation](../knowledge/data-representation.md)
and [concept construction](../knowledge/market-concepts.md).

## A transform can expose an otherwise inaccessible distinction

Let \(X\) take -1, 0, +1 equally and \(Y=1[|X|=1]\). A one-threshold classifier
on X cannot isolate both positive endpoints from the middle. Transforming to
\(F=|X|\) lets a threshold at 0.5 classify perfectly. No Shannon information was
created: Y was deterministic in X throughout. The restricted predictor gained
access to that information. Compare transformed and raw inputs under the same
family and confirmation protocol; model expansion is a different comparison.

## As-of versions change the actual feature

Assume a release records value 4 for period March, first available 10 April.
A revision to 7 becomes available 5 May. At a 20 April decision, March's value
is 4, not the revised 7 and not an observation timestamped 31 March. An event
ending 30 April but published 2 May is not mature training feedback on 1 May.
Rebuild the historical view from availability/version times; a final-value table
does not contain that view merely because it has a date column.

## A roll gap is not inventory profit

One expiring future is at 100 and the replacement at 110, with no price change
during the roll. Closing the first and opening the second transfers the contract
identity; there is no ten-unit profit from joining the prices. Subsequent variation
belongs to the held replacement with its multiplier. Back-adjusted series can
remove the gap for signal calculation, but their levels are not execution prices.
Reconcile costs and collateral on both actual contracts.

## Small reconstruction error can discard the target

Take two independent feature coordinates with variances 100 and 0.01. Let the
direction target be the sign of the second. A one-dimensional variance-maximizing
compression keeps the first and loses the target completely, despite explaining
almost all variance. A supervised task comparison asks what useful distinction
survives, rather than how much raw reconstruction variance is retained.

## Equal trade flow, different replenishment

At one price level, start with displayed depth 100. Both histories execute 80.
History A adds 90 and cancels 10; remaining depth is 100. History B adds 0 and
cancels 10; remaining depth is 10. Trade volume is identical, yet displayed stock
and replenishment differ. Use aligned submissions/cancellations/executions and
level migration to study replenishment; neither history identifies who submitted
orders without an actor observation. A price/volume predictor can still be tested
while that mechanism remains open.

## First nested economic panels

Hold target, learner and temporal protocol fixed. Panel A contains one-day log
return, relative range, twenty-return scale, volume anomaly, momentum at
1/5/10/20/60 sessions and average deviations at 5/10/20/60. Panel B adds simultaneous
near/far slope per year, stable-pair basis change and available open-interest
change. Inventory releases need usable version history. Panel C adds admitted
fine-session quantity, signed imbalance and spread/depth/persistence summaries.
Unknown/stale states are explicit. Fit linear scaling on training only; preserve
as-of coverage and eliminate exact duplicates/constants.

For same-date equity ranking, add relative sector/market state and remove only
the named unwanted exposures. A shared rowwise tree remains equivariant when rows
are reordered. A set model also needs masks to move with their assets; reordering
features without masks changes the represented set. Neutralized features can
still produce nonneutral holdings after selection, so check the actual portfolio.

These panels and windows are first-experiment bindings. Incremental task and net
consumer evidence selects additions; column count is not an information estimate.
