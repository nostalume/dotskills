# Restrained Model and Loss Pilots

These are unexecuted experiment bindings. Principles and change criteria are in
[models/losses](../knowledge/models-losses.md), [optimization](../knowledge/optimization-search.md)
and [validation](../knowledge/inference-validation.md). Bind actual library versions
and budgets before running; no setting is a financial optimum.

## A regularized probability control is numerically inspectable

For logistic mean loss with design rows \(x_i\), responses \(y_i\), fitted
probabilities \(p_i\), and coefficient penalty \(\lambda\|\theta\|^2/2\),
gradient is \(X^T(p-y)/n+\lambda\theta\). A curvature bound is
\(L=\lambda_{max}(X^TX)/(4n)+\lambda\). A full-gradient step no larger than
\(1/L\) is a reproducible first scale when \(L>0\). Check loss descent and
gradient finite differences; scaling/penalty choices belong to development.
Use no-input probabilities and a simple economic score as additional controls.

## Initial nonlinear comparisons

| Consumer | Objective/structure | Initial binding and its role |
|---|---|---|
| Engineered timing state | Binary/three-class probability trees | Depth 3; shrinkage 0.03; cap 300 rounds; minimum child Hessian weight 20; leaf L2 2; row/column sampling 0.8 |
| Frozen-side participation | Binary gate on forward primary candidates | Depth 2; shrinkage 0.03; cap 150 rounds; child weight 50; leaf L2 4 |
| Same-date relative relations | Shared/context controls, then nonpositional set attention with pairwise loss | Two blocks; width 64; four heads; dropout 0.2; date-grouped development stopping |

Depth restricts interactions; child weight restricts objective curvature support,
not a universal sample count; L2 shrinks leaf response; shrinkage and rounds govern
accumulated additive fit. Date grouping preserves the relative object and avoids
randomly splitting the same target cross-section between train and test.
Set structure includes shared rowwise operations and correctly permuted masks.
Remove position dependence and test equivariance; many correlated rows do not
justify unlimited capacity.

For the small set pilot, start Adam at \(10^{-3}\), cap fifty epochs and stop
after five epochs without development improvement. A bounded AdamW rate comparison
\(10^{-4},3\times10^{-4},10^{-3}\) uses the same architecture, mean-loss units,
batch/date semantics and budget. Freeze smoothing/decay conventions so the first
comparison is interpretable. These adaptive rates do not inherit the logistic
full-gradient \(1/L\) guarantee.

## Loss and calibration mutations

With true success probability 0.2 and positive-class weight 4 versus negative
weight 1, weighted log loss is minimized at
\(4\times0.2/(4\times0.2+0.8)=0.5\). That output is not the original event
probability. Recalibrate on an unweighted, appropriately separated development
distribution before a payment threshold, or fit the probability loss unweighted.
Class balance can affect estimation; it cannot silently redefine economic p.

For a pair with higher/lower true relative outcomes, scores 1.2 and 0.4 give
difference 0.8. Pairwise logistic loss \(\ln(1+e^{-0.8})\) is about 0.37110;
its difference derivative is \(-1/(1+e^{0.8})\), about -0.31003. Ranking rewards
the relative margin. A probability gate requires a separately valid calibrated
outcome probability; an excellent ordering alone cannot supply it.

## What changes the first design

Unstable fitting prompts units/derivative/step inspection. A growing train–development
gap prompts stopping or capacity/regularization review. Stable fit with no independent
increment prompts target/state/evidence review. Add capacity or a set relation for
a measured expression gap, and count the added comparison. Freeze selected model,
calibration and consumer before final confirmation; evaluate net holdings separately.
