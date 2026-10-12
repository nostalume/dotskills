# Optimization and Factor Search

Use this entry to select a search operation from the feedback the objective
supplies, and to set update parameters from numerical geometry and noise.
Optimizing a development score, expressing a relation, and confirming financial
use are separate achievements. The [validation entry](inference-validation.md)
owns selection and confirmation.

## Fix the object, objective, and feedback

For continuous parameters \(\theta\), minimize declared objective \(J(\theta)\).
For legal factor expressions \(f\in\mathcal A\), maximize development score
\(Q_D(f)\). Probability loss, rank correlation and net-policy return measure
different things. A score is not automatically usable information.

Feedback order describes the available operation: zero-order supplies function
values, first-order supplies gradients, second-order supplies curvature. Use
actual derivatives for differentiable fitting. Use bounded typed genetic
programming as the initial automatic symbolic search. Compare learned proposal
policies when sharing motifs can justify their additional cost. These choices
follow the feedback and candidate structure.

## Derive a stable gradient step

For \(g=\nabla J(\theta)\), a small displacement has local change
\(g^Td\). At fixed Euclidean length \(h\), Cauchy-Schwarz gives
\(g^Td\ge-h\|g\|\), attained by \(d=-hg/\|g\|\). Hence the gradient direction
is steepest under this displacement metric. Parameter units or a preconditioner
change the metric and can change the appropriate direction.

Suppose gradients satisfy \(\|\nabla J(a)-\nabla J(b)\|\le L\|a-b\|\) along
the proposed segment. Integrating its gradient gives

\[
J(\theta+d)-J(\theta)-g^Td
=\int_0^1[\nabla J(\theta+sd)-g]^Td\,ds
\le\tfrac L2\|d\|^2.
\]

With \(d=-\alpha g\),
\(J(\theta-\alpha g)\le J(\theta)-\alpha(1-L\alpha/2)\|g\|^2\).
For full exact gradients, \(0<\alpha\le1/L\) gives a simple descent scale;
the displayed upper bound remains strictly descending for nonzero gradient
when \(0<\alpha<2/L\). A curvature bound is about this objective and parameter
representation.

When no credible bound is available, full-gradient backtracking can test
\(J(\theta-\alpha g)\le J(\theta)-c\alpha\|g\|^2\), \(0<c<1\), shrinking
\(\alpha\) by a fixed factor. Under local smoothness a sufficiently small
step satisfies it. Give the procedure a lower-step/retry limit and a numerical
failure outcome. Comparing noisy scores from different minibatches does not
establish this deterministic acceptance test.

Newton minimizes the local quadratic \(g^Td+d^THd/2\), solving \(Hd=-g\)
for positive-definite Hessian \(H\). For a quadratic with very unequal positive
curvatures, it removes the common-step imbalance. Nonlinear objectives require
safeguards for indefinite curvature, approximations and solve cost.
[Bottou, Curtis and Nocedal](https://arxiv.org/abs/1606.04838) provide the broader
optimization context. Numerical convergence gives no independent market support.

## Learning rate trades progress against fluctuation

For fixed empirical objective \(J=N^{-1}\sum_iJ_i\), averaging gradients from
uniformly sampled indices gives \(E[\widehat g\mid\theta]=\nabla J(\theta)\).
This is an empirical-gradient statement. The future population law can differ.
Independent sample gradient noise with variance \(v\) averages to \(v/B\).
Dependent terms instead have variance
\(B^{-2}\sum_{i,j}\operatorname{Cov}(\xi_i,\xi_j)\).

Construct \(J(w)=a(w-w_*)^2/2\), \(a>0\), and error \(e_k=w_k-w_*\).
Let gradient noise have conditional mean zero and variance \(v/B\), with no
cross term with current error. Then

\[
e_{k+1}=(1-\alpha a)e_k-\alpha\xi_k,
\quad E[e_{k+1}]=(1-\alpha a)E[e_k],
\quad E[e_{k+1}^2]=(1-\alpha a)^2E[e_k^2]+\alpha^2v/B.
\]

The mean contracts when \(0<\alpha a<2\). At a stationary second moment \(s\),
solve \(s=(1-\alpha a)^2s+\alpha^2v/B\):

\[
s=\frac{\alpha v}{Ba(2-\alpha a)}.
\]

A small step slows contraction and reduces late fluctuation under these
assumptions. Larger batches reduce the independent-noise term but have additional
work and can change update count within a fixed budget. A constant step retains
a noise floor. This construction supplies a quantitative reason for step and
averaging decisions, rather than a universal preference for tiny rates.

**Information does not set the step's units.** For Gaussian
\(Y=\beta X+\epsilon\) with independent centered terms,
\(I(X;Y)=\frac12\ln[1+\beta^2\operatorname{Var}(X)/\operatorname{Var}(\epsilon)]\).
Multiplying the fitted loss by \(c>0\) leaves that information unchanged and
multiplies gradient and curvature by \(c\). Dividing the gradient step by \(c\)
preserves the original update. Weak information motivates careful estimation,
representation, capacity and confirmation; numerical curvature/noise govern rate.

## Understand smoothing, adaptation, and decay

For \(m_k=\beta m_{k-1}+(1-\beta)g_k\), expanding gives geometric weights
\((1-\beta)\beta^j\) on history. Under stationary independent gradient noise
of variance \(v\),
\(\operatorname{Var}(m)=v(1-\beta)^2\sum_{j\ge0}\beta^{2j}
=v(1-\beta)/(1+\beta)\). The history scale is roughly \(1/(1-\beta)\) updates,
so smoothing also introduces lag when the mean direction changes. This is an
averaging calculation, not a universal momentum convergence guarantee.

Adam also tracks squared gradients:

\[
m_k=\beta_1m_{k-1}+(1-\beta_1)g_k,\quad
v_k=\beta_2v_{k-1}+(1-\beta_2)g_k^2,\quad
\theta^+=\theta-\alpha\frac{m_k/(1-\beta_1^k)}
{\sqrt{v_k/(1-\beta_2^k)}+\varepsilon}.
\]

Operations are coordinatewise. Bias correction compensates zero-initialization
attenuation for stationary moments. The denominator concerns gradient scale,
distinct from market volatility. \(\varepsilon\), averaging horizons and rate
all affect numerical movement. See the
[original Adam paper](https://arxiv.org/abs/1412.6980). Scaling every gradient by
\(c>0\) scales the first moment by \(c\) and second moment by \(c^2\). Their
normalized ratio is unchanged if \(\varepsilon\) also scales by \(c\); a fixed
\(\varepsilon\) can break that equality. Apply the actual adaptive update,
rather than automatically transferring the plain-gradient \(\alpha/c\) rule.

With decoupled decay, designated coefficients additionally receive factor
\(1-\alpha\lambda\). L2 inserted into an adaptive gradient changes its moments
and coordinate scaling, so it is generally a different operation; see
[Loshchilov and Hutter](https://arxiv.org/abs/1711.05101). Specify which coefficients,
intercepts and normalization gains receive decay.

**Usual rate path:** normalize inputs, specify mean versus sum loss and gradient
weighting, inspect finite values/derivatives, and fit a modest baseline. Use a
curvature bound/backtracking for an applicable full-gradient model. For an
adaptive neural route, compare a narrow predeclared rate pilot with the same
architecture, batch/date policy, update budget and stopping. Freeze smoothing,
decay and numerical conventions during that comparison. Numeric pilot presets
belong to the experiment library.

Instability calls for numerical repair. A widening development gap calls for
stopping or capacity/regularization review. Stable fitting without confirmed
increment calls for target, observation, representation or evaluator review.
These diagnoses prevent endless step reductions from substituting for research.

## Score-only search buys directions with evaluations

Central coordinate differences approximate derivative \(i\) by
\([J(\theta+he_i)-J(\theta-he_i)]/(2h)\). For smooth functions, truncation error
falls with \(h\); cancellation and observation noise can grow as \(h\) shrinks.
A complete coordinate gradient uses \(2d\) evaluations. Reverse-mode derivatives
avoid those separate coordinate evaluations for a differentiable scalar objective,
although their total work still depends on model size.

Gaussian perturbations differentiate a smoothed function:
\(J_\sigma(\theta)=E_\epsilon J(\theta+\sigma\epsilon)\),
\(\epsilon\sim N(0,I_d)\). Writing a Gaussian density centered at \(\theta\)
and differentiating it gives score \((z-\theta)/\sigma^2\). With justified
interchange of derivative and integral,

\[
\nabla J_\sigma(\theta)=\sigma^{-1}
E[J(\theta+\sigma\epsilon)\epsilon].
\]

The sample estimate is unbiased for the declared smoothed gradient, rather than
automatically for \(\nabla J\). An independent constant baseline removes an
irrelevant level; antithetic differences can reduce noise.
For linear \(J(\theta)=a^T\theta\), the centered one-direction estimate is
\((a^T\epsilon)\epsilon\). Its mean is \(a\) and summed coordinate variance
is \((d+1)\|a\|^2\): rotate \(a\) to the first axis and use
\(E[\epsilon_1^4]=3\), \(E[\epsilon_1^2\epsilon_j^2]=1\) for \(j\ne1\).
Averaging \(m\) independent directions divides this variance by \(m\).
This exposes a dimension cost even in a simple objective. General score noise
and smoothing bias need their own analysis.
[Salimans et al.](https://arxiv.org/abs/1703.03864) study perturbation search.

## Construct the first symbolic factory

A legal factor tree has available observations as leaves and typed operations
as nodes. Addition needs compatible units; ratios need denominator/domain rules;
window operators need declared lookbacks and cutoff-valid inputs. Set depth/node
limits, economic seeds and a small window set before search. Division by zero,
invalid domains and missing records produce explicit statuses, with consistently
defined handling in the scorer.

Use selection, type-safe subtree mutation and crossover to generate candidates.
Freeze score, budget, attempt/evaluation caps, seeds, complexity treatment and
shortlist rule. Cache exact duplicate/shared computations with keys covering
input snapshot, universe, timing, expression/operators, label and scoring version.
Record invalid and failed attempts as well as completed evaluations. These are
real work and part of the search history.

The first output is a frozen shortlist for independent and incremental
confirmation. High development IC or net return remains a selected score.
Choose a larger search or different generator when a measured bottleneck or
useful shared motifs justify its resource and selection cost.

## Learned proposals preserve black-box evaluation

For finite grammar and fixed reward \(R(f)\), a generator \(\pi_\theta(f)\)
has objective \(E_{\pi_\theta}R\). Differentiate its finite sum:

\[
\nabla\sum_f\pi_\theta(f)R(f)
=\sum_f\pi_\theta(f)R(f)\nabla\ln\pi_\theta(f).
\]

A candidate-independent baseline \(b\) preserves expectation because
\(\sum_f\nabla\pi_\theta(f)=\nabla1=0\). For sequential tokens, the log
probability gradient is the sum of conditional token log gradients. One terminal
reward supplies noisy credit to the whole expression. Take an ascent step for
reward maximization, or negate the reward when fitting a minimization objective.
Grammar masks enforce
legality when consistently included in generation probabilities.

The derivative passes through generation probabilities; sorting, fills and the
backtest reward remain black-box evaluations. Compare learned proposals with GP
under the same legal set, scorer, budgets, shortlist and confirmation, including
pretraining/updating overhead. A gradient estimator gives an update mechanism;
its sample efficiency and financial superiority require the comparison.

## Keep three meanings of learning rate separate

Gradient \(\alpha\) controls parameter movement in objective geometry. Boosting
\(\nu\) controls accumulated additive score contributions. Expert \(\eta\)
in \(w_i\propto e^{-\eta L_i}\) converts cumulative loss differences to trust
ratios: \(\ln(w_i/w_j)=-\eta(L_i-L_j)\). Thus loss units and memory/comparator
determine its interpretation. Online aggregation also specifies its comparator,
mature-feedback schedule and memory mechanism.
Information in bits describes another quantity. Name the parameter, objective,
units and update rule whenever discussing a rate.


## Worked applications

[Optimization Search](../examples/optimization-search.md). Numerical settings are illustrative experiment bindings; the principles and change criteria above govern their use.
