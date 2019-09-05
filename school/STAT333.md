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
\lim_{n \to \infty} \lim_{p \to 0} BIN(n,p) = \lim_{n \to \infty} \lim_{p \to 0} {n \choose x}(p)^x(1-p)^{n-x} \\
= \lim_{n \to \infty} \lim_{p \to 0} \frac{n(n-1)...(n-x+1)}{x!}(\frac{\lambda}{n})^x(1-\frac{\lambda}{n})^{n-x} \\
= \lim_{n \to \infty} \lim_{p \to 0} \frac{n(n-1)...(n-x+1)}{n^x}\frac{\lambda^x}{x!}\frac{(1-\frac{\lambda}{n})^{n}}{(1-\frac{\lambda}{n})^{x}} \\
= \frac{\lambda^x}{x!}e^{-\lambda} \\
\lambda = np \implies \lim_{n \to \infty} \lim_{p \to 0} BIN(n,p) = POI(\lambda)
$$





## Day 2









