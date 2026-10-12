# Cash, Inventory, Capacity, and Funding Fixtures

Synthetic fixtures consume [execution/funding](../knowledge/execution-funding.md)
and [carry relations](../knowledge/arbitrage-events.md).

## Same-price exchange preserves wealth

Hold cash 500 and five units marked at 100: equity is 1,000. Buy two at 100 with
no fees: cash becomes 300 and holdings seven, still equity 1,000. A fee of 3 gives
997. A dividend of 2 per held unit later adds 14 cash under this fixture; the
appropriate ex-dividend mark adjustment remains separate. A total-return series
that already includes that payment must not also receive it as an extra return.

Start equal capital weights in two assets. Returns +10% and 0 give total value
1.05 of initial capital and drifted weights 11/21 and 10/21. Returning to 0.5 each
needs trades, despite no change in target weights. Target-to-target turnover
would incorrectly report zero.

## Futures variation and collateral are distinct

Two long linear futures with multiplier 10 move from settlement 100 to 103:
variation is \(2\times10\times3=60\). Starting cash/equity 1,000 becomes 1,060
before fees. Posting 200 collateral moves cash between accessible and pledged
buckets; consolidated equity is still 1,060. Do not also add a 60 futures asset
after that gain was settled. A replacement contract at another price has its own
variation basis, not an automatic roll-gap receipt.

## A two-leg spread can become an outright risk

Buy one unit A at 100, intending to short equivalent B at 101. If B is rejected,
the position is long A, not a locked one-unit spread. An A fallback sale at 98
realizes -2 before costs. Freeze residual-exposure limits, order timeouts and hedge/
cancel actions. Removing this opportunity from the dataset would favor the policy
using future knowledge of its failed execution.

## A terminal hedge can miss the cash deadline

Assume a spot gain of 30 is held on venue A but cannot be transferred before a
short-contract venue B calls for 25 additional cash. B has only 10 accessible.
Consolidated marks may be favorable, yet the 15 shortfall forces B's prescribed
action. A later accessible gain cannot retroactively fund the deadline. Include
borrow/transfer limits and custody freezes in stress, not only total delta.

## Funding arithmetic and adverse mutation

For long spot/short compatible linear perpetual, opening basis 2, closing basis
0.5, signed funding received 0.8 and costs 0.4 give payoff 1.9. Closing basis 5
and funding -0.3 instead give -3.7. The same opening observation leaves two
possible paths. Actual funding clocks/rates, marks, collateral and liquidation
follow the selected product, not this fixture's simple arithmetic.

## Capacity and trading bands

In synthetic currency units, net expected gain is \((g-c)q-aq^2\). For
\(g=0.03,c=0.01,a=0.0001\), optimal nonnegative quantity before caps is 100
and expected net gain is 1. Increasing c to 0.04 makes zero quantity optimal.
The fitted impact/edge uncertainty and actual liquidity determine a real size
ladder; this quadratic is a teaching model.

With desired holding 10, current 9.5, deviation coefficient k=2 and proportional
cost c=2, no-trade half-width is c/k=1: keep 9.5. If current is 8, buy toward
9 rather than all the way to 10 under this objective. These are inventory-aware
decisions, not a mandate to trade each updated forecast.
