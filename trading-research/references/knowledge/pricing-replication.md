# Replication, Pricing Measures, and Unspanned Risk

Use this entry for valuation from a contract's cash flows and tradable hedges.
Start with a finite replication and cash ledger. A pricing map under a fixed model
can be computed accurately even when tomorrow's realized market price is hard to
forecast. The contract, market calibration and unhedgeable risks determine what
that model price means.

## Two equations construct the first price

Let today's non-dividend stock price be \(S>0\), next prices \(Su,Sd\),
\(u>d\), and the cash account's gross growth factor \(R>0\). A claim pays
\(H_u,H_d\). Holding \(\Delta\) stock units and \(B\) currency in cash gives

\[
\Delta Su+BR=H_u,\qquad \Delta Sd+BR=H_d.
\]

Subtract to obtain \(\Delta=(H_u-H_d)/[S(u-d)]\), then
\(B=(uH_d-dH_u)/[R(u-d)]\). The replicating cost is

\[
V=\Delta S+B=R^{-1}[p_QH_u+(1-p_Q)H_d],
\qquad p_Q=(R-d)/(u-d).
\]

Under two-sided frictionless stock/cash trading, no arbitrage requires
\(d<R<u\), so \(0<p_Q<1\). This probability is forced by traded prices and
replication; the physical up probability does not enter this cost. If the claim
trades differently, the opposing claim/replicating holdings form an arbitrage in
this complete model. Borrow, costs and constraints can prevent that trade.

Backward induction repeats these equations at each node with its remaining claim
values. Holdings are chosen using information at the node, before the next shock.
Exercise, barriers, dividends or accumulated path state change the node's contract
and boundary conditions. A tree's convergence and monitoring treatment need
separate numerical checks; writing a recursion alone does not prove accuracy.

## Derive the continuous model's extra second-order term

In the classical model \(dS=\mu S\,dt+\sigma S\,dW\), Brownian increments
over disjoint intervals are independent normal variables of variance \(dt\).
For a uniform partition, \(\sum(\Delta W)^2\) has mean \(T\) and variance
\(2T\,dt\), so it converges in mean square to \(T\). Ordinary Taylor expansion
therefore retains the quadratic random term. For a sufficiently smooth price
\(V(t,S)\), Itô's rule in this model is

\[
dV=(V_t+\mu SV_S+\tfrac12\sigma^2S^2V_{SS})dt
+\sigma SV_SdW.
\]

The random increment is of size \(\sqrt{dt}\); its square is of size \(dt\).
The smoothness/integrability requirements matter at kinks; apply the pricing
solution for \(t<T\) and impose the possibly nonsmooth terminal payoff.

An ideal self-financing replicator with stock units \(\Delta=V_S\) and cash
\(V-\Delta S\) has gain \(\Delta dS+r(V-\Delta S)dt\). Equating this with
\(dV\) cancels the stock shock and physical drift, leaving

\[
V_t+\tfrac12\sigma^2S^2V_{SS}+rSV_S-rV=0,
\qquad V(T,S)=H(S).
\]

Trading costs, discrete hedge times, jumps and missing hedge instruments reopen
replication assumptions. Rebalancing \(\Delta\) is financed through cash; simply
differentiating \(\Delta S\) without the cash adjustment would add spurious gains.

## The normal calculation gives the call formula

In the constant-rate/volatility non-dividend model, remaining time \(\tau>0\)
under the pricing law has
\(S_T=S\exp[(r-\sigma^2/2)\tau+\sigma\sqrt\tau Z]\), \(Z\sim N(0,1)\).
For \(H=(S_T-K)^+\), the event \(S_T>K\) is \(Z>-d_2\), where
\(d_2=[\ln(S/K)+(r-\sigma^2/2)\tau]/(\sigma\sqrt\tau)\).
Write the expectation as the stock part minus the strike part. Completing the
square in the normal density gives

\[
E[e^{aZ}1_{Z>c}]=e^{a^2/2}\Phi(a-c),
\quad V=S\Phi(d_1)-Ke^{-r\tau}\Phi(d_2),
\quad d_1=d_2+\sigma\sqrt\tau.
\]

This is a pricing result under specified dynamics and frictionless replication.
It neither supplies a directional alpha nor proves that a constant volatility
matches all market option quotes. Delta, gamma and model/input sensitivities need
their own [numerical gates](numerical-pricing-hedging.md).

## Distributional distances have a bounded interpretation

For two normal log increments with the same variance \(\sigma^2h\) and means
separated by \((\mu-r)h\), integrating their log-density ratio gives divergence
\((\mu-r)^2h/(2\sigma^2)\) in natural-log units. The stochastic-square terms
cancel except the squared mean difference. Independent steps add over a horizon.
This measures distance between the chosen physical and pricing laws. It is not
\(I(\text{past};\text{future})\), forecast accuracy or post-cost edge.

For constant \(\theta=(\mu-r)/\sigma\), the density
\(L_T=\exp(-\theta W_T-\theta^2T/2)\) has expectation one by the normal
exponential moment. On a finite partition it factors into independent step
densities; completing each square shifts \(\Delta W\)'s mean to \(-\theta h\)
and leaves variance \(h\). Thus \(W_t+\theta t\) is Brownian under the resulting
law and the stock drift becomes \(r\). This construction applies to the stated
constant-coefficient model. General stochastic changes of law require a genuine
integrable density martingale and equivalence conditions. A density martingale
has \(E[L_t\mid\mathcal F_s]=L_s\) for \(s\le t\), preserving conditional
probability normalization over time. A formal exponential
with a state-dependent coefficient is insufficient by itself.

## Incomplete markets leave a valuation obligation

For finitely many states, collect attainable traded payoffs as columns of matrix
\(A\) and prices in vector \(p\). Replication solves \(Ax=H\), with cost
\(p^Tx\). If \(H\) is outside that span, traded instruments do not fix a unique
price. Positive state-price vectors \(q\) satisfying \(A^Tq=p\) can disagree
on \(q^TH\). Their extrema give no-arbitrage bounds under the admitted trading
model; preferences, calibration or additional instruments can select a value
within the remaining obligation. A larger pricing network cannot create a missing
hedge instrument or identify an unsupported risk premium.

## Usual practice path

Contract terms/state and cash flows → finite replication and feasibility → admitted
pricing dynamics/calibration → closed-form/tree/grid control → boundary and cash
fixtures → error-budgeted numerical method → value/Greek/hedge consumers.
Keep the model price, market quote and physical forecast as separate outputs.
For unspanned risk, report the additional assumption or bound that sets valuation.

Worked tree, state-price and derivative cases: [pricing examples](../examples/pricing-paths.md).
Background: [Black and Scholes](https://doi.org/10.1086/260062) and
[Pavliotis's author-hosted stochastic-process text](https://www.ma.imperial.ac.uk/~pavl/PavliotisBook.pdf).
