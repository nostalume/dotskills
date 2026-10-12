# Expert Mixtures, Reversals, and Delayed Feedback

Synthetic forecasts demonstrate [online aggregation](../knowledge/online-aggregation.md).

## One Brier update

Two experts forecast probabilities 0.9 and 0.1; initial trust is 0.5 each and the
observed binary outcome is zero. Their Brier losses are 0.81 and 0.01. Weighted
expert loss is 0.41; the mixture predicts 0.5 and loses 0.25. Difference 0.16 is
the weighted variance of probabilities, matching the convex-loss identity.

At eta 0.5, new A/B odds are \(e^{-0.5(0.81-0.01)}=e^{-0.4}\), giving weights
about 0.401312/0.598688. The next mixed probability is about 0.421050. It is
computed after the first outcome, never substituted retrospectively into the
first prediction. Save forecast versions before outcomes mature.

## Nonzero weight can still mean slow revival

After an accumulated 20-unit advantage for A at eta 0.5, A/B odds are \(e^{10}\).
If B then gains one unit per completed round, equal odds arrive after 20 rounds,
regardless of eta. With sharing gamma 0.02 and K=2, the normalized update places
at least 0.01 trust on each expert. This floor helps revival but continually pays
for weak experts and changes the comparison to evaluate. Cumulative Hedge's static
bound cannot be relabeled a switching-expert bound.

For K=20 and T=252 completed immediate-feedback rounds, first eta is
\(\sqrt{8\ln20/252}\approx0.30839\), and worst-case average static regret bound
\(\sqrt{\ln20/(2\times252)}\approx0.07710\) in bounded-loss units. With K=1,
there is no expert selection. These units are not annual return or Sharpe.

## Delay changes the admitted guarantee

Issue a ten-session policy on day 1 and another on day 2. The first ends on day 11,
with reported payout available on day 12. Day-2 weights cannot use that payout.
A maturity queue may update on day 12; naming that queue completion “round 1”
does not make the day-2 forecast an immediate-feedback round. A theorem-matched
teaching stream waits for maturity before the next issue; a daily stream needs a
delay-aware comparator and lag accounting.

## First adaptive comparison

Use equal probability weights, cumulative log-weight Hedge and uniform-share Hedge
at illustrative gamma 0.02. Keep expert availability, mature Brier outcomes,
participation threshold, risk and fill policy fixed. Compare probability loss,
calibration, recovery lag, concentration, realized turnover and net payment.
All experts can lose money while aggregate loss regret is small. Cost/funding
deterioration with unchanged forecast loss prompts a realization repair, not
automatic trust reassignment.
