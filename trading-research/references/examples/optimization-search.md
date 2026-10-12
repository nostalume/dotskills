# Learning-Rate and Factor-Search Examples

These constructed calculations and initial experiment settings consume
[optimization/search](../knowledge/optimization-search.md) and
[confirmation](../knowledge/inference-validation.md).

## A scalar step has curvature and noise units

For \(J(w)=2(w-w^*)^2\), curvature is \(a=4\). Starting error 1 with full-
gradient step \(\alpha=0.2\) becomes 0.2; at \(\alpha=0.6\), it becomes -1.4
and expands. Stability needs \(0<\alpha<2/a\). A conservative smooth-descent
choice \(\alpha\le1/a\) also supplies the standard bound.

With conditional independent mean-zero gradient noise of variance \(v/B\),
steady squared error for the stable recurrence is
\(\alpha v/[Ba(2-\alpha a)]\). For \(v=9,B=16,\alpha=0.2\), it is 0.0234375.
Doubling B halves that value under the stated independent noise model; correlated
gradients require the covariance sum. Smaller steps reduce the stationary noise
floor but slow the deterministic contraction. Learning rate therefore controls
a numerical trade-off rather than representing the signal's information bits.

Multiply J and its gradient/noise by 100. Curvature becomes 400 and gradient-noise
variance becomes \(100^2v\). Divide the plain step by 100 to reproduce every
update under coupled noise. Mutual information did not change. Adam normalization
scales its moments differently and its epsilon/decay conventions also matter;
the plain-step rule cannot be copied unchanged to every optimizer.

## Three rates that share a name

In a local linearized tree-response approximation, 300 additive rounds at shrinkage
0.03 and 600 at 0.015 have the same total nominal contribution scale 9. Their
actual later residuals/trees can differ, so stopping and regularization must be
compared, not inferred from that product. In Hedge, multiplying losses by 100
requires dividing eta by 100 to keep weight odds. In full-gradient descent it
preserves the update because gradients scale. The two equalities have different
objects and guarantees.

## First bounded symbolic factory

Use immutable, as-of development data and a fixed future policy label. Leaves are
available log returns, scale, volume anomaly and admitted carry/context. Operator
types distinguish levels, changes, dimensionless values and window outputs; a
window consumes only known history. Protected division has an explicit denominator
domain/failure rule. Illegal units, unavailable history, nonfinite values and zero
variation produce recorded invalid status, not a convenient zero score.

An initial teaching binding is 100 legal candidates, ten generations, maximum
depth three, fifteen nodes and windows 5/10/20. Cap attempted scored proposals at
1,000, including invalid attempts; separately count usable evaluations and cache
hits. Retain five elites and choose parents by tournaments of three. Split remaining
proposals equally between type-safe crossover and mutation; freeze seed 42 and
these probabilities before the run. Copies/elites do not automatically consume a
new score when a valid cache can reuse it.

Freeze chronological development folds, scorer/consuming model, complexity penalty
and shortlist rule before search. For a probability consumer, an illustrative reward
is mean fold Brier improvement over the frozen baseline minus 0.001 times node
count. The penalty is in Brier units and is a development binding; report net costs
separately unless included in the reward. A return/rank consumer can instead use
a defined signed IC reward, with its own penalty units. Do not correlate arbitrary
class identifiers as though their code values were money. Orientation chosen in
development is frozen on confirmation. Retain trial/status/source lineage
and confirm only the frozen small shortlist and complete consumer route. The
budget specifies work, not a claim to have found useful factors.

For a learned-proposal comparison, hold data/scorer/attempt and usable-evaluation
budgets/confirmation fixed. The generator gradient is through log proposal
probabilities times the reward; the backtest remains a score-only black box.
Charge warmup/pretraining and inference where the efficiency claim needs them.
A lower cost per proposal or first-order parameter update is not, by itself,
evidence of better net factors.

## Selection accounting changes trust

With 1,000 independent zero-mean unit-normal candidate scores, the upper bound on
expected maximum is \(\sqrt{2\ln1000}=3.7169\). Independence is not required
for that mgf upper bound if each candidate has the specified marginal law; this
is not an exact expected maximum. A high selected score can arise without a true
effect. For bounded losses, one-sided uniform deviation scale at confidence
parameter 0.05, count 100 and independent sample n=1,000 is
\(\sqrt{\ln(100/0.05)/(2,000)}\approx0.06165\). Dependent/adaptive financial
trials require their actual confirmation design instead of substituting row count.
