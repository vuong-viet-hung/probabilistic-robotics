
---
Probability density function (PDF): $$p(x)=p(X=x)$$
Random variable: $X$, $p(X=x) \ge 0$

| Discrete                 | Continuous        |
| ------------------------ | ----------------- |
| $\sum\limits_x p(X=x)=1$ | $\int p(x)\,dx=1$ |

---
Normal distribution: $\mathcal{N}(x;\mu,\sigma^2)$

|          | Scalar form                                                                              | Vector form                                                                                       |
| -------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| PDF      | $p(x)=(2\pi\sigma^2)^{-\frac{1}{2}}\text{exp}\{-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\}$ | $p(x)=\text{det}(2\pi\Sigma)^{-\frac{1}{2}}\text{exp}\{-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu)\}$ |
| Mean     | $\mu$                                                                                    | $\mu$                                                                                             |
| Variance | $\sigma^2$                                                                               | $\Sigma$ (covariance matrix)                                                                      |
$\Sigma$ is a positive semidefinite and symmetric matrix.

---
Joint distribution: $$p(x,y)=p(X=x\text{ and }Y=y)$$
If $X$ and $Y$ are independent: $$p(x,y)=p(x)\,p(y)$$

---
Conditional probability: $$p(x \mid y)=\frac{p(x,y)}{p(y)}$$
If $X$ and $Y$ are independent: $$p(x \mid y)=\frac{p(x,y)}{p(y)}=\frac{p(x)\,p(y)}{p(y)}=p(x)$$
Theorem of total probability:

| Discrete                                | Continuous                        |
| --------------------------------------- | --------------------------------- |
| $p(x)=\sum_\limits{y}p(x \mid y)\,p(y)$ | $p(x)=\int p(x \mid y)\,p(y)\,dy$ |

---
Bayes rule:

| Discrete                                                                                            | Continuous                                                                                           |
| --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| $p(x \mid y)=\frac{p(y \mid x)\,p(x)}{p(y)}=\frac{p(y \mid x)\,p(x)}{\sum_{x'}p(y \mid x')\,p(x')}$ | $p(x \mid y)=\frac{p(y \mid x)\,p(x)}{p(y)}=\frac{p(y \mid x)\,p(x)}{\int p(y \mid x')\,p(x')\,dx'}$ |

- Prior probability distribution: $p(x)$
- Posterior probability distribution: $p(x \mid y)$
- Generative model: $p(y \mid x)$
- Normalizer: $\nu=p(y)^{-1}$
- Data: $y$
Bayes rule allows us to inferring a quantity $x$ from sensor data $y$.

---
Conditional independence: $$p(x \mid y,z)=\frac{p(y \mid x,z)\,p(x \mid z)}{p(y \mid z)}$$$$p(x \mid z)=p(x \mid z,y)$$$$p(y \mid z)=p(y \mid z,x)$$
Conditional independence does not imply absolute independence: $$p(x,y \mid z)=p(x \mid z)\,p(y \mid z) \nRightarrow p(x,y)=p(x)\,p(y)$$Absolute independence does not imply conditional independence: $$p(x,y)=p(x)\,p(y) \nRightarrow p(x,y \mid z)=p(x \mid z)\,p(y \mid z)$$

---
Statistics:

|             | Discrete                                                               | Continuous                                                       |
| ----------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Expectation | $E[X]=\sum_\limits{x}x\,p(x)$                                          | $E[X]=\int x\,p(x)\,dx$                                          |
| Covariance  | $Cov[X]=E[X-E[X]]^2=E[X^2]-E[X]^2$                                     | The same                                                         |
| Entropy     | $H_p(x)=E[-\text{log}_2 p(x)]=-\sum_\limits{x}p(x)\,\text{log}_2 p(x)$ | $H_p(x)=E[-\text{log}_2 p(x)]=-\int p(x)\,\text{log}_2 p(x)\,dx$ |

The expectation is a linear function of a random variable: $E[aX + b] = aE[X] + b$

___
Summary: Discrete vs. Continuous

|                              | Discrete                                                                                            | Continuous                                                                                           |
| ---------------------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
|                              | $\sum\limits_x p(X=x)=1$                                                                            | $\int p(x)dx=1$                                                                                      |
| Theorem of total probability | $p(x)=\sum_\limits{y}\,p(x \mid y)\,p(y)$                                                           | $p(x)=\int p(x \mid y)\,p(y)\,dy$                                                                    |
| Bayes rule                   | $p(x \mid y)=\frac{p(y \mid x)\,p(x)}{p(y)}=\frac{p(y \mid x)\,p(x)}{\sum_{x'}p(y \mid x')\,p(x')}$ | $p(x \mid y)=\frac{p(y \mid x)\,p(x)}{p(y)}=\frac{p(y \mid x)\,p(x)}{\int p(y \mid x')\,p(x')\,dx'}$ |
| Expectation                  | $E[X]=\sum_\limits{x}x\,p(x)$                                                                       | $E[X]=\int x\,p(x)\,dx$                                                                              |
| Covariance                   | $Cov[X]=E[X-E[X]]^2=E[X^2]-E[X]^2$                                                                  | The same                                                                                             |
| Entropy                      | $H_p(x)=E[-\text{log}_2 p(x)]=-\sum_\limits{x}p(x)\,\text{log}_2 p(x)$                              | $H_p(x)=E[-\text{log}_2 p(x)]=-\int p(x)\,\text{log}_2 p(x)\,dx$                                     |



