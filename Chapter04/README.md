# 4 RANDOM FIELDS

## 4.1 Random Variables

### Random Variables

- A **random variable** is a variable that takes a numerical value for each possible outcome of a statistical experiment. 
- We denote a random variable $X(ω)$ by $X$.
- If X is a random variable, then we cannot predict its value with certainty, but we can assign probabilities to events such as $\lbrace X = 1 \rbrace$ and $\lbrace X > 2\rbrace $, etc.

### Discrete Random Variables

- A random variable $X$ is called **discrete** if all of its possible values can be written down in a list.
- The **probability distribution** of a discrete random variable $X$ is a list of the possible values that $X$ can take (put in increasing order), together with the probabilities that X takes each of these possible values.

### Expected Value of $X$

- The **expected value** of $X$, denoted as $E(X)$, is defined to be:

$$ E(X) = \sum_{x} x P(X=x) $$

- This is a weighted average of the possible values of X where the weights are the corresponding probabilities. 
- $E(X)$ is a measure of the center of the probability distribution.

### Continuous Random Variables

- A **continuous random variable** is a random variable that can take on a continuum of possible values.
- We describe the probability properties of a continuous random variable $Y$ by a function $f(y)$ called the **probability density function (pdf)**.
- Probabilities are given by the relevant area under the probability density function curve.

*Note: Unlike discrete random variables, the probability that a continuous random variable takes on a particular value is zero. Instead, we find probabilities for ranges of values.*

### Expected Value of a Continuous Random Variable $Y$

- Suppose that $Y$ is a continuous random variable.
- The **expected value** of $Y$, denoted $E(Y)$, is defined mathematically as:

$$ E(Y) = \int_{-\infty}^{\infty} y f(y) dy $$

*Note: The expected value of a continuous random variable is also a measure of the center of the probability distribution. However, it is not the same as the most likely value (mode) of the distribution.*

### Variance of $X$

- Suppose that $X$ is a random variable. The **variance of $X$**, denoted $Var(X)$, is defined as:

$$ Var(X) = E[(X-E(X))^2] $$

- The **standard deviation** is defined to be the square root of the variance:

$$ \sigma(X) = \sqrt{Var(X)} $$

*Note: The variance measures how spread out the distribution of X is, while the standard deviation provides a measure of the scale or typical size of the distribution.*
