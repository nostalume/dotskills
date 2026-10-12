# Online Learning and Signal Aggregation

Use this entry when confirmed forecasts need a shared, sequential trust rule.
First make the experts predict the same outcome, in the same orientation, with
the same information cutoff. An expert is a factor plus its forecasting rule;
changing that rule changes the expert. Start with equal-weight probabilities,
then cumulative exponential weighting. Test deliberate memory separately when
recovery after reversal is the objective.

## Soft selection has a precise comparator

Let \(L_i\) be expert \(i\)'s cumulative revealed loss before the next decision.
For \(K\) experts, minimize over the probability simplex

\[
\sum_i w_iL_i+\eta^{-1}\sum_iw_i\ln w_i,\qquad \eta>0.
\]

Negative entropy rewards dispersion. A multiplier for \(\sum_iw_i=1\) gives
\(L_i+(\ln w_i+1)/\eta+a=0\), hence
\(w_i=\exp(-\eta L_i)/\sum_j\exp(-\eta L_j)\).
The Hessian's diagonal entries \(1/(\eta w_i)>0\) establish the interior minimum
for finite losses. This is Hedge. Each revealed loss adds \(-\eta\ell_i\) to
log weight. Subtract the maximum log weight before exponentiating and normalizing.
Scaling losses by \(c>0\) and \(\eta\) by \(1/c\) leaves trust unchanged.

Follow-the-leader can fail even with perfect historical loss accounting: alternating
loss vectors \((1,0),(0,1)\), with ties resolved toward the first expert, make it
lose every round while each fixed expert loses half. Soft trust controls this
selection cost; it supplies no guarantee of positive economic return.

## Derive the fixed-expert regret bound

Assume immediate full feedback and losses in \([0,1]\). With unnormalized
\(v_{1,i}=1\), let \(W_t=\sum_iv_{t,i}\) and
\(\widehat\ell_t=\sum_iw_{t,i}\ell_{t,i}\). The bounded exponential-moment
inequality derived in [validation](inference-validation.md) gives

\[
\ln(W_{t+1}/W_t)=\ln\sum_iw_{t,i}e^{-\eta\ell_{t,i}}
\le-\eta\widehat\ell_t+\eta^2/8.
\]

Summing gives \(\ln W_{T+1}\le\ln K-\eta\sum_t\widehat\ell_t+\eta^2T/8\).
The best fixed expert's final weight is included in that sum, so
\(\ln W_{T+1}\ge-\eta\min_i\sum_t\ell_{t,i}\). Combining yields

\[
\sum_t\widehat\ell_t-\min_i\sum_t\ell_{t,i}
\le\frac{\ln K}{\eta}+\frac{\eta T}{8}.
\]

Balancing terms gives \(\eta=\sqrt{8\ln K/T}\) and bound
\(\sqrt{T\ln K/2}\). This sequence-wise argument requires no independent market
dates. It compares one fixed expert over the whole interval, not the best expert
each day. For \(K=1\), use its forecast without a selection update.

## Make the actual output inherit the loss comparison

Combine orientation-aligned binary probabilities \(p_i\) as \(p=\sum_iw_ip_i\).
Use Brier loss \(\ell_i=(p_i-B)^2\). For true success probability \(p^*\),
\(E[(p-B)^2]=(p-p^*)^2+p^*(1-p^*)\), so this is a proper probability loss.
Expanding both squares gives

\[
\sum_iw_i(p_i-B)^2-(p-B)^2=\sum_iw_i(p_i-p)^2\ge0.
\]

Thus the mixture's actual Brier loss is no greater than the weighted loss in the
proof. For class probabilities, use half the squared distance to the one-hot
outcome; it is bounded by one and has the same convex bridge. Thresholded sign
errors do not inherit this identity. Apply the [payoff gate](decisions-labeling.md)
to the mixture, then size and execute using their own rules.

Freeze how missing expert outputs are handled: an unconditional probability
fallback can preserve a fixed expert stream; renormalizing over available experts
changes the comparator and requires its own analysis. Keep decision-time outputs,
versions and availability masks. Only mature, observable outcomes update trust.
An immediate-feedback teaching stream can wait for each policy to finish before
issuing another decision. Overlapping daily predictions use a maturity queue;
their delay-dependent comparison cannot be certified by the immediate proof.
Hypothetical fills after abstention need a valid replay before scoring net-payoff
experts. An observable market label and an unobserved counterfactual fill differ.

## Choose memory deliberately

If A has \(m\) fewer cumulative losses, its odds relative to B are \(e^{\eta m}\).
After reversal, one unit of advantage per round for B takes \(m\) rounds to erase
that gap. Increasing \(\eta\) increases concentration, not this catch-up count.
For a revival floor, compare the normalized update \(\bar w\) with

\[
w_{t+1,i}=(1-\gamma)\bar w_{t+1,i}+\gamma/K,\qquad 0<\gamma<1.
\]

Sharing, discounting and restarting are different memory policies. Their tracking
comparators, switching cost and effective memory must be specified separately;
the preceding static bound is for cumulative Hedge. Selection of memory parameters
belongs to the whole-route trial history.

## Continuous allocation has different geometry

For convex loss \(\ell_t(w)\) on a closed convex set of diameter \(D\), with
gradient norm at most \(G\), projected gradient uses
\(w_{t+1}=\Pi(w_t-\eta g_t)\). Projection cannot increase distance to a feasible
comparator \(u\). Expand the pre-projection square, rearrange, and use convexity:

\[
2\eta[\ell_t(w_t)-\ell_t(u)]
\le\|w_t-u\|^2-\|w_{t+1}-u\|^2+\eta^2G^2.
\]

Telescoping gives \(D^2/(2\eta)+\eta G^2T/2\); choose
\(\eta=D/(G\sqrt T)\). This OGD result concerns Euclidean movement.
Exp-concavity, meaning \(e^{-a\ell}\) concave on the stated domain, can support
logarithmic static regret with a suitable online Newton algorithm. In one
dimension it requires \(\ell''\ge a(\ell')^2\); differentiating the exponential
establishes the condition. Squared probability loss on \([0,1]\) satisfies it
for \(a\le1/2\). Arbitrary thresholded trading losses need not be convex.

## Usual practice path

1. Admit a comparable confirmed expert library, outcome, feedback clock and fixed
   availability rule. Use equal-weight probabilities as the first control.
2. Implement cumulative log-weight Hedge with bounded Brier loss and a declared
   horizon/rate. Hand-check one update and a reversal.
3. Compare a small sharing or restart alternative when drifting relative skill
   motivates it. Keep payout, risk and execution the same across comparisons.
4. Measure probability loss, calibration, adaptation lag, concentration and net
   consumer increment separately. Shared exposures or funding distress are
   [holding/realization](execution-funding.md) problems even with low regret.
5. Confirm the selected library/update/consumer route. Add interaction modeling
   only for a measured remaining relation, not merely to make aggregation strong.

Worked updates and maturity mutations: [expert examples](../examples/expert-memory.md).

Professional background: [Freund and Schapire](https://doi.org/10.1006/jcss.1997.1504),
[Zinkevich's online convex programming](https://www.cs.cmu.edu/~maz/publications/techconvex.pdf),
and [Hazan, Agarwal and Kale](https://doi.org/10.1007/s10994-007-5016-8).
