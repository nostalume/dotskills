# Inference, Validation, and Factor Admission

Use this entry to decide what a selected result supports and how to confirm its
incremental role. The unit of confirmation is the chosen research route: target,
data treatment, representation, fitting, calibration, decision, holding and
execution assumptions used by the claim. Discovery produces candidates;
confirmation evaluates a frozen candidate on appropriately separated evidence.

## Selection changes the question

For \(M\) independent null tests, each with false-positive probability
\(\alpha\), the probability of at least one rejection is
\(1-(1-\alpha)^M\). With arbitrary dependence, the union bound gives an upper
bound \(M\alpha\) (capped at one). A single-test p-value refers to outcomes at
least as extreme under that test's null; it is not the posterior probability of
no edge or a certificate for the winner of a search.

Construct fixed standardized null scores \(Z_j\sim N(0,1)\).
Completing the square gives \(Ee^{aZ_j}=e^{a^2/2}\). For \(a>0\),
\(e^{a\max Z_j}\le\sum_je^{aZ_j}\), and Jensen's inequality yields

\[
E\max_jZ_j\le\frac{\ln M}{a}+\frac a2.
\]

Choose \(a=\sqrt{2\ln M}\) for \(M>1\), giving the upper bound
\(\sqrt{2\ln M}\). Independence is unnecessary for this bound when each
marginal has the specified Gaussian moment. Independent comparable normal trials
have a maximum on this leading scale. Finite samples, dependence and nonnormal
score laws change the empirical null. The expression is a model-based noise
scale, not a universal IC rejection threshold.

**Practical consequence:** record the relevant alternatives before promoting a
winner. Feature windows, sign reversals, labels, universes, cost assumptions,
architectures, rates, calibration, portfolio constraints and failed trials all
belong to the selection history when they affected the chosen route. Economic
priors restrict plausible responses before seeing the winner. Their validity
still requires comparison; a persuasive retrospective story does not erase
selection.

## Derive the cost of unsupported freedom

Consider \(K\) candidate functions fixed independently of an assessment sample
of \(n\) IID observations, with loss in \([0,1]\). For one bounded observation
\(Z\), define \(\psi(a)=\ln Ee^{a(Z-EZ)}\). Under exponential tilting,
\(\psi''(a)\) is a variance, bounded by \(1/4\) for a variable in \([0,1]\).
Since \(\psi(0)=\psi'(0)=0\), integration gives \(\psi(a)\le a^2/8\).
Applying Markov's inequality to the sum of independent centered losses and
optimizing its exponent yields
\(\Pr(|\widehat R-R|>\epsilon)\le2e^{-2n\epsilon^2}\).
The union bound over candidates gives

\[
\Pr\!\left(\max_j|\widehat R_j-R_j|>\epsilon\right)
\le2Ke^{-2n\epsilon^2}.
\]

For failure probability \(\delta\), choose
\(\epsilon=\sqrt{\ln(2K/\delta)/(2n)}\). On that event, the empirical winner
\(\widehat j\) obeys
\(R_{\widehat j}\le\widehat R_{\widehat j}+\epsilon
\le\widehat R_{j^*}+\epsilon\le R_{j^*}+2\epsilon\).
This explains one estimation/selection burden behind restraining unsupported
freedom. The bounded-sum result originates in
[Hoeffding's work](https://doi.org/10.1080/01621459.1963.10500830).

Financial rows often violate these premises. Overlapping trades and same-date
stocks are dependent; log loss is unbounded; adaptive candidates are not a fixed
independent list. Clipping/rescaling a loss changes the bounded object. Use this
derivation as its stated theorem contract, and construct temporal/dependence
checks for the actual route. Parameter count is not a general measure of the
function family's freedom.

## Separate development from confirmation along the full route

Use an early training region, later development comparisons and an untouched
later confirmation region as the ordinary predictive route. Record repeated
walk-forward comparisons when useful. Select feature transformations, model
settings, stopping, calibration, payoff estimates and decision policies in
development. Freeze the chosen definitions, fitting/update schedule and evaluator
before confirmation. A scheduled online update can be frozen as a rule even
though its state evolves from mature feedback.

If confirmation is inspected and then used to redesign, it has become part of
development. Preserve its earlier result and selection history; obtain later
independent evidence for the revised claim. This applies to downstream portfolio
or execution tuning as well as predictor parameters.

### Split using availability and outcome intervals

For opportunity \(i\), retain cutoff \(t_i\), entry \(e_i\), trigger
\(\tau_i\), executed exit \(x_i\), and required label/payout availability
\(k_i\). A fit at time \(T\) can use a training outcome only if its necessary
records have arrived by \(T\). Class maturity and net-payout maturity can differ.

A decision-date split can put a row into training even though its future exit
occurs inside assessment. Purging removes training outcome/dependency intervals
that overlap the held assessment region. An embargo adds a declared separation
where lookbacks, shared state or dependence make nearby examples invalid for the
particular comparison. Determine it from these dependencies and inspect boundary
rows. A fixed fraction alone does not prove separation.

For a forward predictive claim, fit with earlier matured data. Purging an
arbitrary cross-validation block does not authorize training on later observations
as though that were the historical model. Fit scalers, encoders and calibrators
on their allowed partitions. Check the whole computation's information path.
The labeling and data entries define the clocks consumed here.

## Match uncertainty to the dependence

For measured \(Z_t\), expand the centered squared mean:

\[
\operatorname{Var}(\bar Z)=n^{-2}\sum_{t,s}\operatorname{Cov}(Z_t,Z_s).
\]

For a covariance-stationary series with variance \(\sigma^2\) and lag
correlations \(\rho_h\), count the \(n-h\) pairs at each lag:

\[
\operatorname{Var}(\bar Z)=\frac{\sigma^2}{n}
\left[1+2\sum_{h=1}^{n-1}(1-h/n)\rho_h\right].
\]

Independent observations recover \(\sigma^2/n\). Positive correlation lowers
effective information; negative correlation can increase it under this stationary
model. Regime drift can invalidate the common covariance law. For cross-sections,
aggregate/cluster by date or another justified shared-shock unit. For overlapping
time outcomes, use a justified dependent-series uncertainty method, such as
contiguous-block resampling or a long-run covariance estimate, and report its
block/bandwidth assumptions and sensitivity. A resampling method estimates
uncertainty under its dependence model; it cannot generate missing regimes.

Assess fixed-route increments on matched dates/opportunities. Paired loss or
net-return differences can be more informative than comparing unrelated aggregate
scores, but their dependence remains part of the uncertainty calculation.

## Sharpe combines estimation and selection

For single-period excess return \(R\), let \(\mu=ER\), \(\sigma^2=\operatorname{Var}R>0\),
and \(S=\mu/\sigma\). Under IID returns and finite fourth moment, define centered
\(X=R-\mu\), skewness \(\gamma_3=EX^3/\sigma^3\), and ordinary kurtosis
\(\gamma_4=EX^4/\sigma^4\). Leading perturbations have

\[
\operatorname{Var}(\delta\mu)=\sigma^2/n,\quad
\operatorname{Var}(\delta v)\approx\sigma^4(\gamma_4-1)/n,\quad
\operatorname{Cov}(\delta\mu,\delta v)\approx\sigma^3\gamma_3/n.
\]

The variance perturbation is the average of \(X^2-\sigma^2\); its covariance
with the mean perturbation uses \(EX^3\). Differentiate \(\mu/\sqrt v\):
\(\delta S\approx\delta\mu/\sigma-\mu\delta v/(2\sigma^3)\). Combining the
two variances and cross term gives

\[
\operatorname{se}(\widehat S)^2\approx
\frac{1-\gamma_3S+(\gamma_4-1)S^2/4}{n}.
\]

This is first-order asymptotic uncertainty, with an additional normal-limit
approximation needed for a Gaussian tail score. Serial dependence or unstable
fourth moments requires another inference route. Annualization must transform
estimate and uncertainty consistently under a valid temporal scaling model.

Searching many trials also raises the null comparator. Under independent
comparable Gaussian trial estimates \(S_j=\mu_0+\tau Z_j\), the maximum has
distribution \(\Phi(z)^M\) and density \(M\phi(z)\Phi(z)^{M-1}\). Hence

\[
S_0=\mu_0+\tau\int_{-\infty}^{\infty}
zM\phi(z)\Phi(z)^{M-1}\,dz.
\]

This supplies an explicit selection-adjusted comparator under the declared trial
law. The deflated Sharpe framework combines a raised benchmark with nonnormal
return uncertainty; a support score has form
\(\Phi[(\widehat S-S_0)/\widehat{\operatorname{se}}]\).
[Bailey and López de Prado](https://www.davidhbailey.com/dhbpapers/deflated-sharpe.pdf)
specify its published benchmark, effective-trial and finite-sample conventions.
Implement those conventions explicitly if reporting their DSR. The reconstruction
above shows the two mechanisms and labels its asymptotic approximation.

Raw attempts, dependent variants and an estimated effective independent count
are distinct quantities. A missing selection history cannot be repaired by
inventing the count. Feeding a DSR-like statistic into search makes it a
development reward. It is neither untouched confirmation nor a posterior
probability of profit. No universal DSR/IC/Sharpe cutoff owns admission alone.

## Admit a factor for a declared consumer

For consuming route \(C\), compare \(Q(C+f)-Q(C)\) under one fixed protocol.
A standalone signal can be redundant; low correlation does not establish
independence. Conditional complements and nonlinear interactions need the actual
incremental comparison. Preserve the factor's formula/operator version, units,
source and timing, opportunity population, target/policy, orientation, search
history, splits, predictive and economic outcomes, uncertainty and failure scope.

Factor-library operation, portfolio allocation, cash/funding replay and lifecycle
require their corresponding domain methods. Before a claim of attainable net
value, trace the selected forecast into
actual holdings, orders, fills, cash, costs, collateral and settlement. A good
prediction can fail at any of those paths. Before a pricing claim, require the
appropriate numerical oracle and value/Greek gates.

## Usual verification path

1. Freeze the claim, opportunities, clocks, metrics, baselines and selected
   definitions. Record the choices used to reach them.
2. Construct chronological training/development/confirmation and inspect mature
   outcome intervals and boundary dependencies. Fit all transformations inside
   their permitted partitions.
3. Assess predictive increment, calibration if consumed, coverage, and net-policy
   result separately. Use matched comparisons and dependence-aware uncertainty.
4. Carry the complete route, including costs, sizing/update rules and exclusions,
   to confirmation. Report adverse regimes and failures, not just the mean score.
5. Test incremental use in the intended consumer and preserve a factor dossier.
   A restricted useful result can be retained with its scope. A failed claim
   returns to the specific target, source, representation, fit, or cash-path
   dependency exposed by the evidence.

The chosen pipeline supplies evidence for its measured population, period,
information set and action. Operational fidelity and the strength of a market
claim remain separate checks.


## Worked applications

[Optimization Search](../examples/optimization-search.md), [Lifecycle Revisions](../examples/lifecycle-revisions.md). Settings illustrate bindings; apply the principles and change criteria above.
