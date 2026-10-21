# Prediction, Information, and Learnability

Use this entry to decide what a prediction can recover, where its remaining error
comes from, and which research change is worth trying. The objects are observations
available at a decision cutoff, a declared future target, and a loss appropriate
to that target. The conclusions concern that information set and evaluation law.

## Begin with the increment and its consumer

Let today's known price be \(P_t\), tomorrow's price be \(P_{t+1}\), and the
increment be \(W=P_{t+1}-P_t\). Persistence predicts \(P_t\). A proposed price
forecast \(\widehat P_{t+1}\) is an increment forecast
\(\widehat W=\widehat P_{t+1}-P_t\). Compare them on the same opportunities:

\[
L_{\rm persistence}=E[W^2],\qquad
L_{\rm forecast}=E[(W-\widehat W)^2].
\]

A close visual fit to price levels can arise from the known level. Increment
loss, a no-input probability forecast, and the feasible no-trade action provide
different useful controls. Choose the control for the claim being made.
Given \(P_t\), price and increment differ by an invertible translation; their
predictive information is the same when represented at the same resolution.

For an unfinanced position of \(q\) units, gross cash P&L is \(qW\). Costs,
contract multipliers, carry, cash flows, and survival constraints determine the
actual consumer. Resolve these before selecting target detail. The
[decision entry](decisions-labeling.md) develops that choice.

## Locate the information boundary

Suppose the relevant underlying state is \(S\), the observation is \(X=g(S)\),
and the desired quantity is \(Y\). If two admissible states share \(X\) and have
different \(Y\), an \(X\)-based function cannot reconstruct both answers.
For example, observing \(u+v\) leaves \(u-v\) ambiguous. This is an observation
limit. It can coexist with useful conditional probabilities if the states occur
with unequal frequencies. Exact reconstruction and probabilistic prediction are
separate tasks.

For finite labels, evaluate a probability forecast \(q\) by
\(-\log_2 q(Y)\). With true probabilities \(p\), its expected loss is

\[
-\sum_y p_y\log_2 q_y
=-\sum_y p_y\log_2 p_y+\sum_y p_y\log_2(p_y/q_y)
=H(p)+D(p\Vert q).
\]

Here \(H\) is entropy, the best no-input log loss in bits. The divergence \(D\)
is nonnegative: \(\ln z\le z-1\), applied to \(z=q_y/p_y\) and summed with
weights \(p_y\), gives \(-\sum p_y\ln(q_y/p_y)\ge0\). A positive-probability
outcome assigned zero probability has infinite loss. Terms with \(p_y=0\) are
defined by their limit. The optimum is the true distribution.

Apply the same calculation at each observation \(x\) and average:

\[
H(Y\mid X)=E_X H(p(\cdot\mid X)),\qquad
I(X;Y)=H(Y)-H(Y\mid X).
\]

Mutual information is the reduction in optimal probability loss supplied by
\(X\). For a deterministic feature \(F=\phi(X)\), a predictor with \(X\)
can compute \(F\) and imitate any predictor using it. Thus
\(H(Y\mid X)\le H(Y\mid F)\) and \(I(F;Y)\le I(X;Y)\). This data-processing
argument concerns unrestricted predictors. A restricted model can benefit greatly
from the transformation, as the [representation entry](data-representation.md)
shows. The classical definitions are developed in
[Shannon's original paper](https://people.math.harvard.edu/~ctm/home/text/others/shannon/entropy/entropy.pdf).

## Separate irreducible, expression, and fitting error

For a numerical target with finite second moment, write
\(m(X)=E[Y\mid X]\). Conditional expectation is the average outcome among
cases with the same observation. Expanding a square gives

\[
E[(Y-f(X))^2\mid X]
=E[(Y-m(X))^2\mid X]+(m(X)-f(X))^2.
\]

The cross term vanishes because \(E[Y-m(X)\mid X]=0\). Averaging yields
\(R(f)=E\operatorname{Var}(Y\mid X)+E[(m(X)-f(X))^2]\).
If fitted functions belong to family \(\mathcal F\), define
\(R^*_{\mathcal F}=\inf_{f\in\mathcal F}R(f)\). For the realized trained
function \(\widehat f\), add and subtract this quantity:

\[
R(\widehat f)=
\underbrace{E\operatorname{Var}(Y\mid X)}_{\text{information floor}}
+\underbrace{R^*_{\mathcal F}-E\operatorname{Var}(Y\mid X)}_{\text{expression gap}}
+\underbrace{R(\widehat f)-R^*_{\mathcal F}}_{\text{fitting/estimation gap}}.
\]

All terms are nonnegative for a fixed evaluation law and a fitted function in the
family. Optimization, finite samples, and training/evaluation drift can contribute
to the last term. Its exact population value is generally unknown.

**Research decision:** establish numerical fitting and temporal comparison first.
Then repair the diagnosed gap. Missing observations call for a new source or a
weaker target. A relation a rowwise learner cannot express calls for an engineered
state or appropriate structure. Unstable optimization calls for units, derivative,
and step repair. More capacity addresses an expression gap when evidence supports
it; it cannot resolve indistinguishable inputs.

Independence implies zero information, but zero conditional mean has a narrower
meaning. With independent fair sign \(U\) and \(X\in\{1,2\}\),
\(Y=XU\) has \(E[Y\mid X]=0\) while \(|Y|=X\). Direction can be unpredictable
and risk highly predictable. Market efficiency arguments need the information
set, payoff, and restriction they concern. A random-looking price curve supplies
no proof of independence.

## Compare target precision with the signal's help

Discretize a Gaussian increment of standard deviation \(\sigma\) into bins of
width \(\delta\). For fine bins, \(p_k\approx f(w_k)\delta\). Substituting
in entropy and replacing the sum by an integral gives

\[
H(W_\delta)\approx -\int f(w)\log_2 f(w)\,dw-\log_2\delta
=\tfrac12\log_2(2\pi e\sigma^2)-\log_2\delta.
\]

The Gaussian result follows by taking the expected negative log density and using
\(E[W^2]=\sigma^2\). The approximation uses a sufficiently fine quantization
with the tails represented. Its meaning depends on \(\delta/\sigma\), units,
and support conventions. Continuous differential entropy by itself is neither
a unit-free target burden nor necessarily nonnegative.

Construct standardized signal and outcome
\(Z=\rho X+\sqrt{1-\rho^2}U\), with independent standard-normal \(X,U\).
The conditional variance of \(Z\) is \(1-\rho^2\), so subtraction of the two
Gaussian entropies gives

\[
I(X;Z)=-\tfrac12\log_2(1-\rho^2).
\]

For a finite price grid the relevant quantity is \(I(X;W_\delta)\), bounded
above by the continuous increment information and approaching it as the grid is
refined under this model. The numerical comparison below uses continuous
information as that fine-grid approximation.

For direction \(B=1[Z>0]\), symmetry gives \(H(B)=1\). Conditional probability
is \(p(x)=\Phi(\rho x/\sqrt{1-\rho^2})\), where \(\Phi\) is the standard-normal
distribution function. Hence
\(I(X;B)=1-E[h_2(p(X))]\), with binary entropy \(h_2\).
For small \(\rho\), \(p(x)-1/2=\rho x/\sqrt{2\pi}+O(\rho^3)\), and the
entropy expansion is
\(h_2(1/2+u)=1-2u^2/\ln2+O(u^4)\). Using \(E[X^2]=1\),

\[
I(X;B)=\frac{\rho^2}{\pi\ln2}+O(\rho^4),\qquad
I(X;Z)=\frac{\rho^2}{2\ln2}+O(\rho^4).
\]

Direction retains about \(2/\pi\) of the weak-signal information while reducing
the target to at most one bit. With \(\rho=0.05\) and \(\delta/\sigma=0.02\),
the fine target entropy is about 7.69 bits, full increment information 0.001806
bits, and sign information about 0.001149 bits. The normalized signal-to-target
fraction rises about 4.9 times. These are constructed-model quantities.

The optimal sign decision is the sign of \(\rho X\). To derive its hit rate,
write \(X=r\cos\theta\), \(U=r\sin\theta\). Rotational symmetry makes angle
uniform; \(Z=r\cos(\theta-\arccos\rho)\). Opposite signs occupy angular fraction
\(\arccos\rho/\pi\). Reversing the signal for negative \(\rho\) gives
\(\Pr(\text{correct})=1/2+\arcsin(|\rho|)/\pi\), about 51.59% here.

**Design conclusion:** start a trend direction layer with coarse outcome
probabilities. This decision has both an action argument and an information
argument. Retain numerical magnitudes where payouts, scale, risk, or hedging use
them. A lower target entropy improves the formulation's fit to the task; it
does not establish market predictability or net profit.

## Use restricted information as a comparative diagnostic

For a declared predictive family \(\mathcal V\), any distribution it can emit
at an input is also available as a constant forecast on all inputs and without
input. This is the optional-ignorance condition. Write its attainable no-input
and input forecasts as \(\mathcal V_0\) and \(\mathcal V_F\):

\[
H_{\mathcal V}(Y)=\inf_{q\in\mathcal V_0}E[-\log_2q(Y)],\quad
H_{\mathcal V}(Y\mid F)=\inf_{q\in\mathcal V_F}E[-\log_2q(Y\mid F)].
\]

An infimum is the greatest lower bound of attainable losses; an optimum need
not be attained. These quantities measure the family's best population loss,
not the loss of a particular finite-sample fitted model. Define

\[
I_{\mathcal V}(F\to Y)=H_{\mathcal V}(Y)-H_{\mathcal V}(Y\mid F),\qquad
\mathcal L_{\mathcal V}=1-\frac{H_{\mathcal V}(Y\mid F)}{H_{\mathcal V}(Y)}.
\]

For discrete labels and a finite positive baseline, nonnegative log loss and the
ignore-input option give \(0\le\mathcal L_{\mathcal V}\le1\). A zero baseline
makes the ratio undefined. The denominator equals Shannon entropy when the
baseline can represent true marginal probabilities. Family, representation, label,
and evaluation law all matter; the ratio is not a data-only property.
[Xu et al.](https://arxiv.org/abs/2002.10689) formalize predictive families and
usable information under observer restrictions.

Held-out fitted loss differences estimate a realized comparison, not these
population infima. They can be negative. Hold baseline, label, fitting budget,
and splits fixed for a representation comparison; use the
[validation entry](inference-validation.md) for selection and uncertainty.

## A usual first research path

1. Bind instrument, available observations, allowed action, horizon/exit, and
   realized payment. Select direction, policy outcome, or relative rank for that
   decision using the decision entry.
2. Construct persistence/no-input/no-trade controls appropriate to each claim.
3. Build the small state panel in the representation entry. Fit its regularized
   probability/relative-score control, then the task-shaped restrained candidate
   in the model entry.
4. Compare probability or rank loss, calibration where needed, and economic
   action separately on chronological development data.
5. Freeze the selected route and confirm its incremental value. If stable fitting
   brings no independent increment, revisit target, state, and evidence before
   extending optimizer or capacity searches.

Risk premia, slow information diffusion, constraints and behavioral frictions
can motivate a candidate relation. Their signs and persistence require the
particular comparison. Under independent equal-risk net bets with mean \(a\),
standard deviation \(s\), the total mean/standard-deviation ratio is
\(\sqrt N\,a/s\). With valid common pairwise correlation \(c\) and positive
\(1+(N-1)c\), variance becomes
\(s^2N[1+(N-1)c]\), giving effective breadth \(N/[1+(N-1)c]\).
Overlapping trades and common shocks therefore limit breadth. A count of asset
rows is an opportunity count, not an independent-bet certificate.

The familiar \(\mathrm{IR}\approx\mathrm{IC}\sqrt B\) relation needs a forecast/
allocation model as well. IC, the information coefficient, is forecast-return
correlation here; IR is the resulting mean-to-standard-deviation ratio. For
\(B\) independent equal-risk bets with standardized forecast \(s_i\), return
\(R_i\), and \(E[s_iR_i]=\mathrm{IC}\), the linear
portfolio \(B^{-1/2}\sum_i s_iR_i\) has mean \(\sqrt B\,\mathrm{IC}\) and
variance \(\operatorname{Var}(sR)\). For jointly normal standardized \((s,R)\),
write \(R=\mathrm{IC}\,s+\sqrt{1-\mathrm{IC}^2}U\). Expanding the square and
using \(E[s^4]=3\), \(E[s^2U^2]=1\) gives
\(\operatorname{Var}(sR)=1+\mathrm{IC}^2\). The ratio is therefore
\(\mathrm{IC}\sqrt B/\sqrt{1+\mathrm{IC}^2}\), close to the familiar expression
for weak skill. Constraints, costs, common exposures and unstable skill change
its applicability. Breadth amplifies a supported per-bet increment; it does not
turn a zero or unconfirmed increment into an edge.


## Worked applications

[Information Targets](../examples/information-targets.md). Settings illustrate bindings; apply the principles and change criteria above.
