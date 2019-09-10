# STAT 333

## Day 1

#### Basic Review

Conditional probability:
$$
P(A|B) = \frac{P(A \cap B)}{P(B)} \\
    P(A \cap B) = P(A|B)P(B)
$$
Law of total probability:
$$
P(A) = \sum_{i=1}^{n}P(A|B_i)P(B_i)
$$
Baye's Rule:
$$
P(B|A) = \frac{P(A|B)P(B)}{P(A)}
$$
**Example 1.2**

> Show that when $n$ is large and  $p$ is small, the $BIN(n, p)$ distribution may be approximated by a $POI(\lambda)$ distribution where $\lambda =np $.

$$
\lim_{n \to \infty} \lim_{p \to 0} BIN(n,p) \\= \lim_{n \to \infty} \lim_{p \to 0} {n \choose x}(p)^x(1-p)^{n-x} \\
= \lim_{n \to \infty} \lim_{p \to 0} \frac{n(n-1)...(n-x+1)}{x!}(\frac{\lambda}{n})^x(1-\frac{\lambda}{n})^{n-x} \\
= \lim_{n \to \infty} \lim_{p \to 0} \frac{n(n-1)...(n-x+1)}{n^x}\frac{\lambda^x}{x!}\frac{(1-\frac{\lambda}{n})^{n}}{(1-\frac{\lambda}{n})^{x}} \\
= \frac{\lambda^x}{x!}e^{-\lambda} \\
\lambda = np \implies \lim_{n \to \infty} \lim_{p \to 0} BIN(n,p) = POI(\lambda)
$$

## Day 2



We define a random variable as $F(x) = P(X \leq x) = \int_{-\infty}^{x}f(y)dy$, where $f$ is the probability density function (PDF). We also have $P(x \in B) = \int_{x \in B} f(x)dx$.

**Special Continuous Distributions**

- Uniform: $f(x) \frac{1}{b-a}$
- Beta: $f(x) = \frac{(m+n-1)}{(m-1)(n-1)}x^{m-1}(1-x)^{n-1}, 0 < x < 1$
- Erlang: $f(x) = \frac{\lambda^nx^{n-1}e^{-\lambda x}}{(n-1)!}$, a special case of the gamma distribution
- Exponential: $f(x) = \lambda e^{-\lambda x}$, is erlang distribution with $n=1$

**Expectation**

The expected value of a random variable $E[g(X)] = \sum g(x)p(x)$ for the discrete case or $E[g(X)] = \int_{-\infty}^{\infty}g(x)p(x)$ in the continuous case. We can think of this value as a weighted average of the random variable.

**Moments**

If we take $E[X^n]$ we receive the $n^{th}$ moment of $X$. For $n=0$ we receive $1$ and for $n=1$ we receive the mean of $X$. 

**Variance**

We define the variance of random variable $X$ as $E[(X - E[X])^2]$ which is also expressed as $E[X^2] - E[X]^2$.  We define the standard deviation as $\sigma = \sqrt{Var(X)}$.

**Linear Function of a Random Variable**

If we take $E[aX + b]$ then the variance wouldn't change due to $b$ since th distribution is only shifted by it, but it is affected by $a$. The mean will also be linearly transformed to be $aE[X]+b$.

**Moment Generating Functions**

We define the MGF for a random variable $X$ as $E[e^{tX}], t \in R$. We also find that if $t=0$ then we get the MGF to be $1$. We also fund the following
$$
\phi_X(T) = E[e^{tX}] \\
= E[\sum_{n=0}^{\infty}\frac{(tX)^n}{n!}] \\
= E[X^0]\frac{t^0}{0!}+E[X^1]\frac{t^1}{1!}+...E[X^n]\frac{t^n}{n!}\\
$$
To find the $n^{th}$​ moment:

1. Find the MGF
2. Take the $n^{th}$ derivative
3. Take the limit as $t$ goes to $0$

**Ex.** Find MGF of $Bin(n,p)$ and use it to find $E[X]$ and $Var(X)$
$$
\phi_X(t) \\
= E[e^{tX}] \\
= \sum_{x=0}^n e^{tx}{n \choose x}p^x(1-p)^{n-x} \\
= \sum_{x=0}^n {n \choose x}(pe^{t})^x(1-p)^{n-x} \\
= (pe^{t} + 1 - p)^n
$$
We now take the $1^{st}$ and $2^{nd}$ derivate of $\phi_X(t)$.
$$
\phi_X^{'}(t) = npe^{t}(pe^{t} + 1 - p)^{n-1} \\
\phi_X^{''}(t) = npe^{t}(pe^{t} + 1 - p)^{n-1} + npe^{2t}(n-1)(pe^{t} + 1 - p)^{n-2} \\
$$
Thus we now have the following. Note that expectation is the $1^{st}$ moment and variance is the $2^{nd}$.
$$
E[X] = \phi_X^{'}(0) = np \\
Var(X) = E[X^2]-E[X]^2 \\
= \phi_X^{''}(0)-(np)^2 \\
= np + np(n-1) -(np)^2\\
=n^2p(1 - p) \\
$$
**Covariance**

We define the covariance between random variables $X$ and $Y$ as $Cov(X, Y)=E[(X-E[X])(Y-E[Y])]$ which is also written as $E[XY] - E[X]E[Y]$.

**Joint Moment Generating Functions**

A joint MGF would look like $E[e^{sX+tY}]$. 

**Independence**

Random variables $X$ and $Y$ are independent only if we probability with respect to each random variable interacting may be calculating indepdendtly and then multiplied together. Another way to view this is that events in the sample space for each random variable don't inform us of the event in the sample space for the other random variable. We also have $Cov(X, Y) = 0 \iff X \and Y$ are independent. 



