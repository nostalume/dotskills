# Decisions, Targets, and Attainable Labels

Use this entry to choose what the predictor answers and how that answer becomes
an action. Begin with an opportunity, information cutoff, instrument, executable
entry, permitted actions, exit policy, and payment unit. A target is a map from
future outcomes to the distinctions this decision needs.

## Construct the smaller decision problem

Let future outcome be \(Z\), action be \(a\), observation be \(F\), and loss be
\(\ell(a,Z)\). Suppose label \(Y=g(Z)\) preserves the action loss:
\(\ell(a,Z)=\widetilde\ell(a,g(Z))\) for every permitted action and admissible
outcome. Grouping conditional probabilities by label yields

\[
E[\ell(a,Z)\mid F]
=\sum_y\widetilde\ell(a,y)\Pr(Y=y\mid F).
\]

The minimizing action can therefore be computed from label probabilities. Exact
outcome digits within a class add no decision distinction under these premises.
This is the constructive reason to coarse-grain. If magnitude changes the loss
inside a class, retain its conditional class payout or the necessary numerical
state. Sizing, collateral and hedging often require such additions.

For a newly designed **trend direction layer**, use direction probabilities as
the initial forecast. For a **profit/stop/timeout policy**, use the policy's
first-passage outcomes. For **relative selection**, use feasible-horizon ranks
or pairwise relative outcomes. For **contract valuation or sensitivity**, retain
the numerical values and derivatives the consumer requires. This task-based
selection replaces an unordered classification/regression menu.

Price rounding alone supplies no theorem that the smaller task is tradable.
The [information entry](prediction-information.md) supplies the Gaussian
comparison and its assumptions. Economic participation still uses payments.

## Derive participation from probabilities and payments

For a fixed long policy, let \(p(F)\) be its positive-outcome probability,
\(G(F)>0\) mean gross gain in that class, \(L(F)>0\) mean gross loss magnitude
otherwise, and \(c(F)\) mean total cost, all in the same units. Conditional
expectation grouped by class is

\[
A(F)=p(F)G(F)-(1-p(F))L(F)-c(F).
\]

Against a zero-return abstention baseline, rearrangement gives
\(A>0\iff p>(L+c)/(G+L)\). This threshold follows from the policy, not from
the convention that a majority vote exceeds one half. A threshold above one
means the declared policy cannot have positive expectation under those payments.
Risk, capital and uncertainty can demand an additional margin of safety; name
its role separately from the expected-value calculation.

Start with completed training outcomes' class-average realized payouts and a
declared cost model. Compare conditional payout estimates when within-class
variation changes participation materially. This adds the magnitude needed by
the action rather than returning automatically to full-price prediction.
Compare long, short and flat using each policy's own payout law. Asymmetric
stops, borrow or funding can prevent obtaining the short by negating a long label.

## Define first passage with explicit clocks

At decision cutoff \(t\), select executable entry time \(e\), horizon deadline
\(v\), and a frozen scale estimate \(\widehat\sigma_t\). For simple-return
barriers choose positive distances \(u=k_u\widehat\sigma_t\) and
\(d=k_d\widehat\sigma_t\). On the declared monitoring grid, define

\[
\tau_+=\inf\{s>e:P_s/P_e-1\ge u\},\quad
\tau_-=\inf\{s>e:P_s/P_e-1\le-d\},\quad
\tau=\min(\tau_+,\tau_-,v).
\]

An empty hit set has time infinity. The first upper hit gives the upper class;
the first lower hit gives the lower class; reaching the deadline without a hit
gives timeout. Freeze the last-observation/tie convention. A horizon beyond the
available dataset is unfinished, distinct from a completed timeout.

Equal endpoints can have opposite hit orders. First passage therefore retains
the path distinction the selected exit uses. It need not increase predictive
information compared with another label; its positive justification is policy
alignment. Three completed classes have entropy at most \(\log_2 3\), while
their predictability depends on observations and the policy.

Estimate historical one-step dispersion from \(w\) available same-instrument
returns:

\[
\bar r_t=w^{-1}\sum_{j=0}^{w-1}r_{t-j},\qquad
\widehat\sigma_t^2=(w-1)^{-1}\sum_{j=0}^{w-1}(r_{t-j}-\bar r_t)^2.
\]

Under independent equal-variance returns, expand the centered sum around the
population mean: \(\sum(r_j-\bar r)^2=\sum(r_j-\mu)^2-w(\bar r-\mu)^2\).
Its expectation is \(w\sigma^2-w\sigma^2/w=(w-1)\sigma^2\), explaining the
denominator. Under dependence or changing variance the formula remains a local
dispersion statistic; its unbiasedness proof no longer applies.

The units are consequential. For additive increments,
\(\operatorname{Var}(\sum r_j)=\sum\operatorname{Var}(r_j)+2\sum_{i<j}
\operatorname{Cov}(r_i,r_j)\). Equal variances and zero covariance imply
\(\sigma\sqrt h\) for the horizon standard deviation. Log returns add exactly;
simple returns compound, with their sum a small-return approximation. State
whether a barrier uses one-step or horizon dispersion, its return convention,
and when its scale is frozen. Reject unusable scales explicitly.

### Monitoring and execution describe different events

A close-observed prototype scans completed observations and exits at the next
declared executable opportunity. A resting intraday stop is a different policy.
Record trigger \(\tau\), executed exit \(x\), fill, costs, and payout separately.
An upper trigger followed by a lower fill can have a smaller or negative realized
payment. A gap may skip the ideal stop price.

If an OHLC bar contains both hits, its extremes do not determine their order.
Use finer admitted observations, mark ambiguity, or apply a development-frozen
conservative convention. An unavailable exit permission, missing hedge leg, or
liquidation before the favorable endpoint changes the attainable outcome. Define
eligibility from the applicable instrument and historical contract, not from a
generic market label.

Retain status: valid, unfinished, ambiguous, untradable, invalid-data, or a
specified forced-exit class. Class maturity waits for the required observations;
economic payout maturity additionally waits for execution and cost records.
Use those clocks in [temporal validation](inference-validation.md).

## Convert first-passage probabilities to an economic comparison

Let class probabilities be \(p_+,p_-,p_0\). With signed conditional mean realized
gross payouts \(a_k(F)\), the score is

\[
A(F)=\sum_{k\in\{+, -,0\}}p_k(F)a_k(F)-c(F).
\]

Integer label codes identify classes; they are not payment sizes. A timeout
may have a nonzero payout. The shortcut \(g(p_+-p_-)-c\) requires symmetric
fixed payments \(a_+=g,a_-=-g,a_0=0\). Use the general grouping when fills,
timeouts or conditional magnitudes differ. Net class payouts already contain
costs and require no second cost subtraction.

For multiclass scores \(z_k\), softmax gives
\(p_k=\exp(z_k)/\sum_j\exp(z_j)\). Subtract the largest score for stable
arithmetic. A reference score removes the common-additive-constant ambiguity.
For observed class \(y\), \(\ell=-z_y+\ln\sum_j e^{z_j}\), so
\(\partial\ell/\partial z_k=p_k-1[y=k]\). Fit probability loss, inspect
calibration on held-out development predictions, and use independently assessed
payouts. These steps give probabilities the meaning the gate consumes.

## Separate a frozen direction from participation

Meta-labeling preserves a primary side \(s(F)\) and predicts whether its proposed
trade should be taken. Generate its opportunities with the primary policy, replay
the actual side/exit, and define success from a declared criterion, such as
positive realized net payout. Forward-generate predictions and candidates when
the primary rule itself is fitted; an in-sample primary fit would give the gate
unavailable information about how opportunities were selected.

With mean net gain \(G_m\) on success and net loss magnitude \(L_m\) otherwise,
\(A_m=p_mG_m-(1-p_m)L_m\); the threshold is \(L_m/(G_m+L_m)\).
The gate can retain, restrict or reject opportunities, while the primary side
remains fixed for this comparison. A changing primary model defines a new route
whose full selection history belongs in validation.

Use a smaller state panel and restrained probability gate. Compare net outcomes
and coverage to taking all primary candidates, on the same opportunities. A gate
that keeps one fortunate observation has little coverage even if its reported
average looks attractive. Check adverse events and retained exposure.

## Relative selection and numerical consumers

For the historical eligible cross-section, let \(R_i\) be the return under the
feasible entry/exit policy. A deterministic midrank convention can encode
\(Y_i=(\operatorname{midrank}(R_i)-1/2)/n\); ties share rank. The target orders
relative outcomes. If all stocks rise, signs can be identical while relative
returns differ. Fit and assess by dates, including a declared benchmark and
eventual holding constraints. Rank supplies neither cash alpha nor sell rights.

For contract values, payout magnitudes, margin or hedging, a class summary can
erase a required distinction. Add the numerical component at that consumer.
For instance, approximations \(\widehat V(x)=V(x)+\varepsilon\sin(\omega x)\)
can have value error at most \(\varepsilon\) and derivative error as large as
\(\varepsilon\omega\). A value tolerance supplies no sensitivity guarantee.
The full pricing and financing methods are later knowledge owners; preserve
their required numerical checks when choosing a foundation target.

## Usual practical construction

1. Specify eligibility, cutoff, entry, permitted action, monitoring, exit,
   payment unit and the no-trade comparison.
2. Choose the target for that policy. Freeze zero/tie, timeout, ambiguity,
   forced-exit and unfinished conventions.
3. Hand-replay upper/lower/timeout paths, an incomplete horizon, an adverse gap,
   and an unavailable exit. Confirm trigger and payout maturity separately.
4. Generate the outcome record with policy version, observed scale, time
   intervals, fills, signed payouts, costs and statuses.
5. Fit the restrained probability/ranking control in
   [models and losses](models-losses.md); evaluate prediction, calibration,
   participation and coverage separately.
6. Add conditional magnitudes or policy states when they alter the decision.
   Freeze the revised route before [confirmation](inference-validation.md).

Barrier multipliers, horizons and numerical experimental presets belong to the
particular experiment. Their general selection criteria are the holding role,
available monitoring/fills, relative movement units, and recorded development
comparison. Broader or narrower barriers create different events and trade
durations; tune them as policy choices, with their search history retained.

## Professional references

- Marcos López de Prado, [*Advances in Financial Machine Learning*](https://www.wiley-vch.de/en/areas-interest/finance-economics-law/finance-investments-13fi/finance-investments-special-topics-13fiz/advances-in-financial-machine-learning-978-1-119-48208-6), Wiley, 2018. Financial labeling, meta-labeling and overlapping outcomes; see Chapters 3, 4 and 7. The execution/maturity constructions above explicitly bind the selected policy.
- James et al., [*An Introduction to Statistical Learning*](https://www.statlearning.com/), second edition, 2021. Classification and model assessment background.


## Worked applications

[Payouts Barriers](../examples/payouts-barriers.md), [First Experiments](../examples/first-experiments.md). Settings illustrate bindings; apply the principles and change criteria above.
