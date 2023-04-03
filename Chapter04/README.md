# 4 RANDOM FIELDS

## 4.1 Random Variables

- A **random variable** is a variable that takes a numerical value for each possible outcome of a statistical experiment. 
- We denote a random variable $X(ω)$ by $X$.
- If X is a random variable, then we cannot predict its value with certainty, but we can assign probabilities to events such as $\lbrace X = 1 \rbrace$ and $\lbrace X > 2\rbrace $, etc.

### 4.1.1 Discrete Random Variables

- A random variable $X$ is called **discrete** if all of its possible values can be written down in a list.
- The **probability distribution** of a discrete random variable $X$ is a list of the possible values that $X$ can take (put in increasing order), together with the probabilities that X takes each of these possible values.

### 4.1.2 Expected Value of $X$

- The **expected value** of $X$, denoted as $E(X)$, is defined to be:

$$ E(X) = \sum_{x} x P(X=x) $$

- This is a weighted average of the possible values of X where the weights are the corresponding probabilities. 
- $E(X)$ is a measure of the center of the probability distribution.

### 4.1.3 Continuous Random Variables

- A **continuous random variable** is a random variable that can take on a continuum of possible values.
- We describe the probability properties of a continuous random variable $Y$ by a function $f(y)$ called the **probability density function (pdf)**.
- Probabilities are given by the relevant area under the probability density function curve.

*Note: Unlike discrete random variables, the probability that a continuous random variable takes on a particular value is zero. Instead, we find probabilities for ranges of values.*

### 4.1.4 Expected Value of a Continuous Random Variable $Y$

- Suppose that $Y$ is a continuous random variable.
- The **expected value** of $Y$, denoted $E(Y)$, is defined mathematically as:

$$ E(Y) = \int_{-\infty}^{\infty} y f(y) dy $$

*Note: The expected value of a continuous random variable is also a measure of the center of the probability distribution. However, it is not the same as the most likely value (mode) of the distribution.*

### 4.1.5 Variance of $X$

- Suppose that $X$ is a random variable. The **variance of $X$**, denoted $Var(X)$, is defined as:

$$ Var(X) = E[(X-E(X))^2] $$

- The **standard deviation** is defined to be the square root of the variance:

$$ \sigma(X) = \sqrt{Var(X)} $$

*Note: The variance measures how spread out the distribution of X is, while the standard deviation provides a measure of the scale or typical size of the distribution.*

### 4.1.6 Properties of $E(X)$ and $Var(X)$

Suppose that X and Y are random variables, and a and b are numbers. Then:

- $E(a) = a$
- $E(bX) = bE(X)$
- $E(X + Y) = E(X) + E(Y)$
- $Var(aX + b) = a^2Var(X)$

*Note: The expected value is a linear operator, meaning that it satisfies the properties of linearity. That is, it behaves like a linear function of its arguments. The variance of a linear transformation of X is equal to the square of the scaling factor times the variance of X.*

## 4.2 Time Series

- Observations of random variables over time typically display dependence. 
- It is this dependence that we model by using time series models.
- We use the notation $\lbrace X_t(\omega): t\in T\rbrace$ (for simplicity, $X_t$) to denote a time series, where T (usually $\mathbb{N}$, $\mathbb{Z}$ or $\mathbb{R}$) is the index set.

*Note: Time series models are used to describe the behavior of a sequence of random variables over time, where the observations are typically dependent on past observations. This dependence is often referred to as "serial correlation" or "autocorrelation."*

|<img width="1024" alt="image" src="https://user-images.githubusercontent.com/19381768/229432904-6db84c2e-69ba-4dd1-ad51-391b1d3e0eaa.png">|
|:--:|
|Time series|

### 4.2.1 Interpolation and Extrapolation in Time Series Analysis

Time series data is different from other data types in terms of interpolation and extrapolation because we are typically interested in predicting values that are outside the range of the observed data, which is known as extrapolation. 

- Other data types often involve interpolation, where the goal is to estimate missing values within the observed range of the data. 
- Interpolation is commonly used, for example, to estimate missing data points in images or to smooth out noisy signals.
- Because time series data is typically used for forecasting and prediction, it is important to be aware of the limitations of extrapolation and to use appropriate statistical methods that take these limitations into account. 
- In particular, it is important to be aware of issues such as overfitting and model selection bias when making predictions based on time series data.

### 4.2.2 Weakly Stationary Time Series

A time series $\lbrace X_t\rbrace$ is said to be **weakly stationary** if:

- $E(X_t)$ does not depend on $t$.
- For every integer s, $E[X_t X_{t-s}]$ does not depend on $t$. Or in other words, the autocovariance function $γ(s) = E[(X_t - E(X_t))(X_{t-s} - E(X_{t-s}))]$ does not depend on $t$ for any lag $s$.

For a weakly stationary time series $\lbrace X_t\rbrace$, we define:

- $m = E(X_t)$ (for simplicity, we often use $m = 0$).
- The **autocovariance function** $γ$ by $γ(s) = E[X_t X_{t-s}]$ for all integer $s$.
- The **autocorrelation function** $ρ$ by $ρ(s) = \frac{γ(s)}{γ(0)}$ for all integer $s$.

*Note: Weak stationarity is a common assumption in time series analysis. It implies that the mean and variance of the time series are constant over time, and that the autocovariance and autocorrelation functions depend only on the time lag between observations and not on the absolute time at which they occur. Weak stationarity simplifies the analysis of time series and makes it possible to use many powerful tools from classical statistics.*

- Intuitively, weak stationarity means that the statistical properties of the time series do not change over time. 
- The mean is constant, and the autocovariance function depends only on the time lag and not on the absolute time at which the observations occur.

Examples of weakly stationary time series include:

- White noise: a time series of independent and identically distributed (iid) random variables with mean zero and constant variance.
- Random walk: a time series where the value at each time point is the sum of the previous value and a random increment. Random walks are not weakly stationary because the mean and variance change over time.
- Moving average: a time series that is constructed by taking a weighted average of past and present random shocks. Moving average processes can be weakly stationary if the weights satisfy certain conditions.
- Autoregressive: a time series where the value at each time point depends linearly on the past values of the series. Autoregressive processes can be weakly stationary if the coefficients satisfy certain conditions.

*In practice, weak stationarity is a common assumption in time series analysis. It simplifies the analysis of time series and makes it possible to use many powerful tools from classical statistics, such as the Fourier transform, the autoregressive integrated moving average (ARIMA) model, and spectral analysis.*

## 4.3 Random Fields

A **random field** is a generalization of a time series to higher-dimensional spaces or other index sets. It is a collection of random variables indexed by an index set that can take on values in a multidimensional space, on a surface, or in any other domain. A time series is a particular case of random fields, where $T$ is a one-dimensional space.

We will use the same notation $X_t$ for random fields as for time series. But you should remember that the index **t** can be multidimensional. 

- However, because of randomness, $X_t$ is a function of two variables, i.e. $X_t = X(t,ω)$. 
- For a fixed $ω∈Ω$, the function $X(t,ω)$ is a non-random function of **t**. 
- This deterministic function is usually called a sample path (or sample function) or a realization. 
- This is what we usually observe in our experiments or datasets.
- For simplicity, we denote $X(t,ω)$ by $X_t$.

*Note: Random fields are used to describe the behavior of a collection of random variables over a multidimensional space or other index set. Random fields generalize the concept of time series to higher-dimensional spaces, making it possible to analyze and model data that varies over multiple dimensions.*

Random fields are used to model and analyze data that varies over multiple dimensions, such as spatial data, images, or signals. They are also used in physics, engineering, and other fields to model stochastic processes in space and time.

|![image](https://user-images.githubusercontent.com/19381768/229489696-73b90b9e-e595-4247-aff9-9a7a496afb5a.png)|
|:--:|
|Random field|

Examples of random fields include:

- A temperature map of the earth's surface, where the temperature at each point is a random variable.
- A three-dimensional image of a material, where the intensity at each point is a random variable.
- A time-frequency representation of a signal, where the amplitude at each time-frequency point is a random variable.

In the example of a temperature map of the earth's surface, the variable $t$ might represent the two-dimensional location on the surface, and the variable $ω$ might represent the time at which the temperature is observed or recorded. Thus, for a fixed value of $ω$ (i.e., a fixed time), the temperature at each point on the surface can be considered a **realization of a random field**, with each temperature value corresponding to a different value of the index t (i.e., a different location on the surface).

Overall, random fields can be used to estimate the spatial or temporal dependence of the data, to detect patterns or anomalies, or to make predictions about future values of the data. They can also be used to generate realistic simulations of the data, which can be useful for testing models or evaluating algorithms.

In practice, the analysis and modeling of random fields often involves the use of advanced statistical methods, such as spatial statistics, spectral analysis, or machine learning techniques.

### 4.3.1 Expectation and Covariance of Random Fields

The expectation of a random field is defined as:

$$m(t) = E[X_t]$$

The (auto-)covariance function is defined by:

$$C(t, s) = Cov[X_t, X_s] = E[X_tX_s] - m(t)m(s),$$

whereas the variance is: $σ^2(t) = C(t, t)$.

The (auto-)correlation function of a random field is defined as:

$$ρ(t, s) = Corr[X_t, X_s] = \frac{C(t, s)}{σ(t)σ(s)}$$

The covariance/correlation function describes the spatial or temporal dependencies between observations at different locations or time points. 

*Note that the expectation, covariance, and correlation of a random field can be estimated from a finite set of observations using standard statistical methods. These estimates can be used to model and analyze the behavior of the random field, and to make predictions or inferences about future or unobserved values of the field.*

### 4.3.2 Autocovariance and Autocorrelation Functions

The autocovariance function $C(t, s)$ of a random field describes the covariance between the values of the field at two different locations (or time points) $t$ and $s$. 

Intuitively, the autocovariance function measures how similar the values of the field are at different locations (or time points), with positive values indicating positive dependence (i.e., values tend to be similar), negative values indicating negative dependence (i.e., values tend to be dissimilar), and zero values indicating independence (i.e., values are unrelated).

The autocorrelation function $ρ(t, s)$ of a random field is a standardized version of the autocovariance function, and measures the linear relationship between the values of the field at two different locations (or time points). 

The autocorrelation function is calculated by dividing the autocovariance function by the product of the standard deviations of the field at the two locations (or time points), which ensures that the autocorrelation function takes values between -1 and 1. Positive values of the autocorrelation function indicate positive linear dependence, negative values indicate negative linear dependence, and zero values indicate no linear dependence.

The autocovariance and autocorrelation functions are important tools for analyzing and modeling random fields, as they provide information about the spatial or temporal dependence of the data. They can be estimated from a finite set of observations using standard statistical methods, and used to fit models or make predictions about the behavior of the field.

### 4.3.3 Trend and Covariance Functions

- The expectation $m(t)$ of a random field represents a spatial trend in the data, which can be modeled by any function. 
- In practice, it is common to use a parametric trend function, which can be controlled by a small number of parameters. 
- Popular trend functions include constant, polynomial, exponential, and logistic functions.

To fit a trend function to the data, one needs to estimate the unknown values of the parameters. This can be done using standard regression techniques, such as ordinary least squares (OLS) or maximum likelihood estimation (ML).

- Selecting an appropriate covariance function is a more challenging problem. 
- Not every function can be used as a covariance function, as it must satisfy certain mathematical properties, such as being positive definite. 
- In practice, a common approach is to choose a covariance function from a class of known functions that have desirable properties, such as being stationary or isotropic. 
- Some popular covariance functions include the Gaussian, exponential, and Matérn functions.

Estimating the parameters of the covariance function from data can be done using maximum likelihood estimation or other methods. Once the parameters are estimated, the covariance function can be used to model and simulate the behavior of the random field, and to make predictions or inferences about future or unobserved values of the field.

### 4.3.4 Positive Definite Functions

A function $f(x_1, x_2, ..., x_n)$ is said to be positive definite if it satisfies the following conditions:

1. $f(x_1, x_2, ..., x_n) = f(x_1 - y_1, x_2 - y_2, ..., x_n - y_n)$ for all $x_1, x_2, ..., x_n$ and $y_1, y_2, ..., y_n$.

2. The matrix $A = [f(x_i, x_j)]_{n×n}$ is positive semidefinite, i.e., for any vector $a = (a_1, a_2, ..., a_n)$ of length $n$, the quadratic form $a^T A a ≥ 0$.

Intuitively, a positive definite function is a function that assigns a positive value to any set of inputs, and that satisfies certain mathematical properties that ensure it behaves well in certain contexts, such as when used as a covariance function.

In the context of random fields, the covariance function must be positive definite to ensure that the resulting covariance matrix is positive semidefinite, which is a necessary condition for the model to be valid and well-behaved. Many popular covariance functions, such as the Gaussian and Matérn functions, are positive definite and have desirable mathematical properties that make them suitable for modeling spatial or temporal dependence in data.

### 4.3.5 Positive Definite Functions Definition and Properties

A function of two variables $B(·, ·)$ is positive definite if it satisfies the following condition:

$$ \sum_{k=1}^n \sum_{l=1}^n c_k \bar{c}_l B(t_k , t_l ) ≥ 0 $$

for any positive integer $n$, sequences $t_k ∈ T$ and complex numbers $c_k \in \mathbb{C}$. ($\bar{c}_k$ denotes a
complex conjugate of $c_k$).

Positive definite functions have several useful properties, including:

- They are symmetric, i.e., $B(t, s) = B(s, t)$ for all $t$, $s$ in $T$.
- They are continuous and bounded.
- They are closed under linear combinations.
- They are closed under multiplication by positive constants.
- They can be used to construct new covariance functions from known ones using standard operations such as addition, multiplication, and convolution.

Let $P_T$ be the class of positive functions on $T$.
1. $B(t, s) ∈ P_T , α ≥ 0 ⇒ α · B(t, s) ∈ P_T $
2. $B_1(t, s) ∈ P_T , B_2(t, s) ∈ P_T ⇒ B_1(t, s) + B_2(t, s) ∈ P_T$
3. $α_1 ≥ 0, ..., α_n ≥ 0$; $B_1(t, s), ..., B_n(t, s) ∈ P_T ⇒ \sum_{k=1}^n α_kB_k (t, s) ∈ P_T$
4. $B_1(t, s) ∈ P_T, B_2(t, s) ∈ P_T ⇒ B_1(t, s) · B_2(t, s) ∈ P_T$
5. $B_n(t, s) ∈ P_T ⇒ lim_{n→∞} B_n(t, s) ∈ P_T$

The concept of positive definiteness is fundamental in many areas of statistics, data science, and mathematics, and plays a central role in the theory and practice of random fields and related topics.


