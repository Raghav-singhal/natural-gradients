# Natural Gradients Presentation
These are slides from a talk I gave at the Courant Institute of Mathematics.

Natural Gradients is an optimization method inspired from Information Geometry, where the central part is played by the Fisher Information Matrix (we refer to it as 'the Fisher').

## The Fisher
The Fisher Information Matrix, $I(\theta)$, is defined as $I(\theta) = \mathbb{E}[\nabla_{\theta} \log p_{\theta}(X) \nabla_{\theta} \log p_{\theta}(X)^T ] $. Note that the Fisher is positive semi-definite meaning that $|| p_{\theta} || = \langle p_{\theta}, I(\theta) p_{\theta} \rangle $ is a valid inner poroduct on the Riemannian Manifold of Parametrized Probability Distributions. As we now have a notion of distance, we can also talk about geodesics. Geodesics are essentially the shortest path between two points on some manifold which is also how different geomteries are characterized. I will not be discussing Information Geometry here, so we now return to some classical aspects.

The Fisher also plays a vital role in classical statistics, I list a few below:

* Asymptotic Normality of Maximum Likelihood. That is $$ \sqrt{n}(\theta_{n} - \theta^{true}) \rightarrow \mathcal{N}(0, I(\theta)^{-1}) $$
where $I(\theta)$ is the Fisher Information Matrix.

* Cramer-Rao Bound
* Consistency of MLE
* Invariant to Reparametrization

## Natural Gradient
If we recall, the direction of the steepest descent for a function $f(x)$ in Euclidean Space is given by its gradient $\nabla_{x} f(x)$, however when we are in this 'Fisher Space', the direction of steepest descent changes since the notion of distance has also changed. The Natural Gradient is defined as $I(\theta)^{-1} \nabla L{\theta}$. There are several reason why one would consider using the natural gradient, for instance Euclidean distance between probability distribution is not appropriate, that also goes for comparing the euclidean distance between the parameters of the probability distributions. Hence, we use KL-Divergence.

A drawback of using KL-Divergence is that it is not a metric as it is not symmetric. However, if we look at it a 'local scale', we can show that it is symmetric(I show this in the slides). We can do this by taking a second-order taylor approximation of the KL-Divergence and we can show that the second-order term is the Fisher Information Matrix and the first term vanishes(under some regularity conditions). This is another derivation of the Fisher Information Matrix.


