# Volatility, Exposure Span, and Path State

Use this entry when uncertainty, nonlinear exposure or payoff history is the
quantity of interest. Start with a past-only persistence forecast for variance,
the hedge exposures the contract needs, and the smallest sufficient path state.
Add a volatility model or richer path representation for a demonstrated remaining
distinction, with its calibration, cost and error comparison.

## Mean and variance have different estimation scales

For independent Gaussian observations of mean \(\mu\), variance \(\sigma^2\)
and count \(n\), the mean estimate has variance \(\sigma^2/n\). The unbiased
sample variance has variance \(2\sigma^4/(n-1)\), from the squared-normal sum
after estimating the mean. Their relative errors depend on \(\mu/\sigma\), so
a tiny drift can remain uncertain while risk scale is usable.

For Brownian log increments over step \(h\), sample average divided by \(h\)
estimates the annualized drift with standard error approximately \(\sigma/\sqrt T\)
at total span \(T=nh\). More finely sampling the same span does not create extra
drift history. Variance estimation can gain from more increments under the ideal
model; market microstructure noise and dependence limit that gain in actual data.
Define whether the target is future realized variance, instantaneous latent
variance or option-implied variance. They are different quantities.

Use a rolling/EWMA past-only variance control for risk and future-realized-variance
comparison. EWMA \(v_t=(1-a)v_{t-1}+a r_t^2\), \(0<a\le1\), has observation
weights \(a(1-a)^j\); its decay half-life solves
\(j=\ln(1/2)/\ln(1-a)\) for \(a<1\). Declare return demeaning, sampling,
units, overnight treatment and horizon. Add covariates or a stochastic-volatility
model when controlled out-of-sample risk/valuation comparisons justify it.

## A smile concerns quotes; hedging concerns spanning

Implied volatility is the constant-volatility model input that matches one
observed quote. A strike/maturity smile means one constant input does not fit the
whole quote surface. Add structure according to the missing behavior: jumps for
discontinuities/tails, stochastic volatility for another random volatility state,
local volatility for a state/time surface. Calibration quality, dynamic hedge
quality and physical forecasting are separate comparisons. Enforce relevant price
bounds/shape and check the observed domain before interpreting a calibrated model.

If \(dS=a_Sdt+b_1dW_1+b_2dW_2\) and a separate volatility state has different
shock loadings, a claim's Itô random exposure involves both price and volatility
derivatives. One stock holding can cancel only an exposure in its span. Write
the claim and hedge shock-loading matrix, solve for reachable exposures and inspect
the residual. Additional option hedges introduce their own costs, liquidity and
model risks. Naming a stochastic model does not make its market complete.

For a smooth claim priced with variance \(\sigma_{imp}^2\) but an underlying
path with instantaneous variance \(\sigma_{real}^2\), the delta-hedged gain net
of the model cash carry is, locally under continuous diffusive assumptions,

\[
\tfrac12\Gamma_t S_t^2(\sigma_{real,t}^2-\sigma_{imp,t}^2)dt.
\]

Substitute actual quadratic variation into Itô's rule, cancel delta's stock gain,
and use the pricing PDE for the remaining drift. Integrate with changing gamma
and subtract actual hedge costs. An unweighted average variance comparison omits
where gamma exposure occurred. Discrete gaps/jumps and discrete hedging add errors.

## Construct sufficient state before a large history encoder

An arithmetic Asian average on \(m\) monitoring dates needs current price,
running sum \(A_k=\sum_{j\le k}S_j\), count \(k\), remaining schedule and model
state; update \(A_{k+1}=A_k+S_{k+1}\). A barrier needs hit status and monitoring
terms; a lookback needs a running extremum. An endpoint cannot recover these.
A sufficient-state recursion can be cheaper and more faithful than a sequence
network. A proposed whole-path derivative must specify how the history is
perturbed and continued; it is not automatically an ordinary spot derivative.

For ordered finite-variation information, define
\(S^{ij}=\int_{u<v}dX^i_u\,dX^j_v\). Two linear segments with increments
\(a,b\) contribute two same-segment triangles and one cross-segment rectangle:

\[
S^{ij}=a^ia^j/2+a^ib^j+b^ib^j/2.
\]

Paths moving coordinate 1 then 2 and coordinate 2 then 1 have the same endpoint
but different \(S^{12}\). Ordered integrals form a path signature. At dimension
\(d\), truncation level \(m\) contains \(\sum_{k=1}^md^k\) nonconstant
coordinates. A single finite-variation coordinate gives only
\((\Delta X)^k/k!\); add time or necessary other coordinates to encode order.
Specify interpolation, scales and missing observations. Start at level two against
simple accumulators/multiscale summaries. Finite truncation is not lossless, and
stochastic/rough paths need a specified integration convention.

## Roughness is not automatically long memory

Increment scaling \(E[(X_{t+h}-X_t)^2]=ch^{2H}\) gives typical size \(h^H\).
In fractional Brownian motion, unit increments separated by lag \(k\) have
covariance \([(k+1)^{2H}-2k^{2H}+(k-1)^{2H}]/2\). Taylor expansion cancels
constant/odd terms and leaves \(H(2H-1)k^{2H-2}\) at large lag. For
\(H<1/2\), this is negative with summable absolute tail; for \(H>1/2\), positive
and nonsummable. Short-scale roughness and persistent positive long memory are
different properties. Empirical rough-volatility motivation concerns studied data,
not every asset. History-dependent dynamics can still be simulated with a bound
on discretization/history cost; they need not admit a small Markov pricing PDE.

## Usual practice path

Define variance/payoff/hedge target → build persistence and sufficient-state
controls → identify surface, exposure or order gap → choose the smallest
extension → calibrate/fit on admitted data → check risk/value/Greek/path errors
and consumer increment. Independent prediction evidence is needed before using
a risk representation as directional alpha.

Worked paths and exposures: [pricing/path examples](../examples/pricing-paths.md).
Background: [Cont and Fournié](https://arxiv.org/abs/1002.2446),
[signature primer](https://arxiv.org/abs/1603.03788), and
[Gatheral, Jaisson and Rosenbaum](https://arxiv.org/abs/1410.3394).
