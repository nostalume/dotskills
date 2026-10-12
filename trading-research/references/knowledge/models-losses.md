# Models, Capacity, Parameters, and Losses

Use this entry after identifying the target and available representation. Select
the loss for the quantity the consumer needs, the model structure for the remaining
relation, and capacity for the independent evidence available to estimate it.
These are related choices with different responsibilities.

## Choose an initial model ladder

For refined timing factors, begin with no-input probabilities, one prespecified
economic score, and a regularized linear probability model. Then compare shallow
boosted trees for threshold effects and modest interactions. For a first-passage
target, predict all completed policy classes. For a frozen-side meta-gate, use a
smaller binary model and narrower panel.

For relative selection, begin with a shared linear score and shallow trees supplied
with available cross-sectional/sector context. Use restrained nonpositional set
attention as the initial relational candidate when the remaining question involves
asset-to-asset interaction. Its structural advantage and incremental value should
be compared against those contextual controls.

For raw sequences or other representations with useful structure still buried,
choose an encoder for that structure. A refined-factor default does not prohibit
representation learning. A missing relation and an appropriately controlled
comparison justify the added structure and capacity.

Define this small ladder in development, keep evaluation dates and outcomes fixed,
and freeze its chosen route before confirmation. A model family's empirical winner
is established by the matched comparison, distinct from a useful starting default.

## Probability losses support probability consumers

For binary label \(b\), score \(z\) gives
\(p=1/(1+e^{-z})\). Natural-log loss is
\(\ell=-b\ln p-(1-b)\ln(1-p)\). The derivative
\(p'=p(1-p)\) gives

\[
\frac{d\ell}{dz}=p-b,\qquad
\frac{d^2\ell}{dz^2}=p(1-p).
\]

The [information entry](prediction-information.md) proves that population log
loss is minimized by the true probabilities. Binary squared probability loss
(Brier loss) also has that property: if the true fraction is \(a\),
\(E[(b-q)^2]=a(1-a)+(q-a)^2\). Choose a proper probability loss for the
participation gate and inspect held-out calibration as well as predictive loss.
Near-zero assigned probabilities make log loss highly sensitive to realized
surprises; document any clipping convention.

Class weighting changes the probability being estimated. Weighted binary log
loss has derivative zero at
\(q=w_1a/[w_1a+w_0(1-a)]\). Unless weights coincide, this is a tilted
probability rather than the original class frequency. Start a calibrated
participation consumer with the original opportunity distribution and unit class
weights. If sampling or weighting changes it, recover or recalibrate the required
probabilities using held-out development predictions and the known design.

### A concrete regularized fitting operation

Let \(M\) have \(N\) feature rows with an intercept column, and coefficient
vector \(\theta\). Penalize selected coefficients through diagonal matrix
\(R\), with zero on the intercept and one on penalized coordinates:

\[
J(\theta)=N^{-1}\sum_i\ell((M\theta)_i;b_i)
+\tfrac\lambda2\theta^TR\theta,
\quad \nabla J=M^T(p-b)/N+\lambda R\theta.
\]

Its Hessian is \(M^TDM/N+\lambda R\), where
\(D_{ii}=p_i(1-p_i)\le1/4\). For every vector \(v\),

\[
v^T\nabla^2Jv\le[\|M\|_{\rm op}^2/(4N)+\lambda]\|v\|^2.
\]

Here the operator norm is the largest stretch of a unit vector. This gives a
credible full-gradient curvature bound \(L_0\). The
[optimization entry](optimization-search.md) derives descent with step
\(1/L_0\) or safeguarded backtracking. The penalty changes the fitted objective;
the step changes how it is solved. Select penalty and stopping through a small
recorded development comparison. Check convergence and avoid penalizing an
intercept unintentionally.

## Understand shallow boosting through its updates

A boosted score adds a tree response:
\(S_m(F)=S_{m-1}(F)+\nu h_m(F)\). Each binary depth-\(d\) tree has at most
\(2^d\) leaves, but many trees can express far more combined distinctions.
Depth limits local interactions; rounds and stopping limit accumulated fit.

For binary log loss, sum gradient and curvature over a proposed leaf:
\(G=\sum(p_i-b_i)\), \(H=\sum p_i(1-p_i)\). The local second-order objective
for a constant score change \(w\), with leaf penalty \(\lambda\), is

\[
Gw+\tfrac12(H+\lambda)w^2.
\]

Differentiation gives \(w^*=-G/(H+\lambda)\) when its denominator is positive.
The applied increment is scaled by \(\nu\). The Taylor approximation explains
the update; it is not an exact logistic-loss equality. The formulation is
developed in [Chen and Guestrin's XGBoost paper](https://arxiv.org/abs/1603.02754).

| Control | What it changes | Usual design responsibility |
|---|---|---|
| Depth/leaves | Number and order of within-tree partitions | Limit unsupported local interactions |
| Shrinkage \(\nu\) | Contribution of each new tree | Select jointly with rounds and stopping |
| Round cap/early stopping | Accumulated adaptation | Use chronological development checkpoint policy |
| Leaf L2 or split penalty | Objective preference for smaller responses/partitions | Constrain weakly supported responses |
| Child Hessian-weight threshold | Curvature support of child leaves | Interpret in the selected objective and weighting |
| Row/column sampling | Inputs used during each round | Assess robustness without treating rows as independent |

In the unit-weight binary example, \(h_i\le1/4\). A child total \(H\ge h_0\)
therefore requires at least \(4h_0\) rows; probabilities near zero/one require
more. A different objective or weighting changes that interpretation. The
[official parameter reference](https://xgboost.readthedocs.io/en/stable/parameter.html)
defines `min_child_weight` in Hessian units. Bind implementation details to the
actual recorded version when running a prototype.

If every tree added the same constant \(a\), accumulated change would be
\(M\nu a\). Smaller shrinkage can be offset by more rounds. Consequently,
shrinkage is evaluated as part of a fitting route, not as a standalone safeguard.
Missing-value routing and feature importance describe computational behavior;
their economic meaning requires the appropriate representation/use comparison.

Use a monotone constraint when a predeclared economic relation and relevant
scope justify its orientation. Compare the restriction to an unconstrained
control. A monotone prior can reduce unsupported freedom or remove a genuine
state reversal. Its justification precedes inspection of the winning fit.

## Give relative structure a suitable loss

For scores \(s_i\) and feasible returns \(R_i\) on one date, centered Pearson
IC is
\(\sum_i(s_i-\bar s)(R_i-\bar R)/(\|s-\bar s\|\|R-\bar R\|)\).
Require nonzero dispersions and a declared constant-score rule. Negative IC
can be a training objective, but its scale invariance gives no payout magnitude
or calibrated probability. Spearman rank correlation uses ranks and is generally
nondifferentiable; optimizing Pearson IC is a different numerical operation.

A concrete ranking objective uses outcome order
\(d_{ij}=\operatorname{sign}(R_i-R_j)\) for unequal pairs and loss

\[
\ell_{ij}=\ln(1+e^{-d_{ij}(s_i-s_j)}).
\]

Differentiating with respect to \(s_i\) gives
\(-d_{ij}/[1+e^{d_{ij}(s_i-s_j)}]\); the \(s_j\) derivative is its negative.
Thus the update corrects pair order without fitting unused return digits.
Declare tie handling, pair sampling and per-date normalization. Whole-date
loss averaging preserves the chosen date-weighting when set sizes vary.

MSE is appropriate when the numerical conditional mean is the consumer's object,
such as a necessary payout component. The direction or ranking layer instead
starts with the corresponding probability or relative objective. Directly
optimizing portfolio Sharpe introduces holding, cost and dependence choices into
the objective; it needs the whole-route confirmation and path checks, not a
presumption that the training metric equals attainable profit.

## Construct a relation-preserving asset-set model

Let \(X\in\mathbb R^{n\times d}\) hold asset rows and let permutation matrix
\(P\) reorder them. Scores should obey \(f(PX)=Pf(X)\). This is permutation
equivariance: outputs retain asset identity under arbitrary row order. A shared
rowwise linear model or tree already satisfies it. Attention adds learned
cross-row comparisons.

With shared \(W_Q,W_K\in\mathbb R^{d\times d_k}\) and
\(W_V\in\mathbb R^{d\times d_v}\), define

\[
Q=XW_Q,\quad K=XW_K,\quad V=XW_V,\quad
A(X)=\operatorname{softmax}_{\rm row}(QK^T/\sqrt{d_k})V.
\]

The score matrix is \(n\times n\); each row normalizes comparisons with all
available counterparts and returns a \(d_v\)-dimensional response. Under
permutation its scores become \(PSP^T\). Rowwise exponentiation/normalization
commutes with this reordering, giving
\(\operatorname{softmax}(PSP^T)=P\operatorname{softmax}(S)P^T\) and
\(A(PX)=PA(X)\). Shared rowwise transforms and residuals preserve the equality.
The [Set Transformer work](https://proceedings.mlr.press/v97/lee19d.html) develops
attention for set interactions.

Use genuine asset attributes as features, leave out arbitrary row positions,
and permute availability masks with their assets. An arbitrary-order causal mask
breaks the intended relation. Evaluate deterministic predictions with dropout
disabled. For a unit-variance independent product model, a dot product's variance
grows as \(d_k\); dividing by \(\sqrt{d_k}\) supplies a numerical score scale,
not an assertion that assets are independent.

Start with a shallow/narrow relation candidate, limited heads, explicit residual
widths, date-grouped batches, regularization and development stopping. Compare
shared context-aware controls. Strong shrinkage/dropout can erase a thin useful
component. Low-rank constraints bound expressible matrix directions; RMS
normalization controls per-row numerical scale. Neither has a universal financial
optimal setting. Select them for the diagnosed relation and fitting gap, with a
recorded budget. The exact teaching architecture is a separate experiment binding.

## Make capacity decisions from evidence

Date-level shocks and overlapping outcomes make asset-date count a poor proxy
for independent sample size. A larger family offers more response patterns and
more opportunities to fit accidental detail. The finite-family bound and
selection calculation in [validation](inference-validation.md) explain that
tradeoff; raw parameter count is not a general capacity measure.

Restrict the unsupported dimensions through structure, modest depth/width,
regularization and stopping. Increase capacity when stable fitting and residual
comparisons identify a relation the cheaper route misses, and confirmation
supports its incremental use. A training improvement alone selects a development
candidate. An information limit, inadequate observation map or sparse adverse
event history requires a different repair.

## Usual fitting and comparison path

1. Freeze target policy, opportunity population and available state. Establish
   no-input, economic-score and regularized linear controls.
2. Choose probability loss for participation or date-grouped relative loss for
   selection. Keep numerical components where the economic consumer needs them.
3. Compare shallow nonlinear fitting; for cross-row relations compare a restrained
   set candidate to contextual shared controls.
4. Bind scaling, weighting, parameter meanings, fitting budget and checkpoint
   policy. Run a narrow chronological development comparison.
5. Diagnose instability, development overfit, probability miscalibration, and
   absence of independent increment separately. Repair the corresponding owner.
6. Freeze the whole chosen route, including calibration and downstream actions,
   before confirmation. Evaluate prediction, coverage and economic outcome in
   their own units.

## Professional references

- Chen and Guestrin, [*XGBoost: A Scalable Tree Boosting System*](https://arxiv.org/abs/1603.02754), KDD 2016; [official parameters](https://xgboost.readthedocs.io/en/stable/parameter.html). Tree objective and implementation parameter semantics.
- Lee et al., [*Set Transformer*](https://proceedings.mlr.press/v97/lee19d.html), ICML 2019. Set interaction architectures.
- James et al., [*An Introduction to Statistical Learning*](https://www.statlearning.com/), second edition, 2021. Statistical learning and assessment background.


## Worked applications

[Model Pilots](../examples/model-pilots.md). Numerical settings are illustrative experiment bindings; the principles and change criteria above govern their use.
