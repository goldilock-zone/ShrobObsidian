# Pascal's Triangle with the binomial coefficients mod 2

Let's construct Pascal's Triangle modulo 2 for 9 rows using LaTeX. In this representation, the entries will be either $1$ or $0$, indicating whether the binomial coefficients are odd or even, respectively. Here is the LaTeX representation for the first 9 rows:

$$
\begin{array}{ccccccccccccc}
&&&&&&& 1 \\
&&&&&& 1 && 1 \\
&&&&& 1 && 0 && 1 \\
&&&& 1 && 1 && 1 && 1 \\
&&& 1 && 0 && 0 && 0 && 1 \\
&& 1 && 1 && 0 && 0 && 1 && 1 \\
& 1 && 0 && 1 && 0 && 1 && 0 && 1 \\
1 && 1 && 1 && 1 && 1 && 1 && 1 && 1 \\
\end{array}
$$

In this triangular arrangement, each row corresponds to a level in Pascal's Triangle. The pattern of $1$s and $0$s is derived from calculating each binomial coefficient modulo 2. This structure is not only mathematically intriguing but also aesthetically pleasing, revealing a fractal-like pattern as more rows are added.

- It's an almost fractal diagram
Here is the LaTeX representation of Pascal's Triangle modulo 3 for 12 rows. In this arrangement, each entry is the corresponding binomial coefficient modulo 3, which can be either $0$, $1$, or $2$:

$$
\begin{array}{*{20}{c}}
&&&&&&&&&&&&1 \\
&&&&&&&&&&&1 && 1 \\
&&&&&&&&&&1 && 2 && 1 \\
&&&&&&&&&1 && 0 && 0 && 1 \\
&&&&&&&&1 && 1 && 0 && 1 && 1 \\
&&&&&&&1 && 2 && 1 && 1 && 2 && 1 \\
&&&&&&1 && 0 && 0 && 2 && 0 && 0 && 1 \\
&&&&&1 && 1 && 0 && 2 && 2 && 0 && 1 && 1 \\
&&&&1 && 2 && 1 && 2&& 1 && 2 && 1 && 2 && 1 \\
&&&1 && 0 && 0 && 0 && 0 && 0 && 0 && 0 && 0 && 1 \\
&&1 && 1 && 0 && 0 && 0 && 0 && 0 && 0 && 0 && 1 && 1 \\
&1 && 2 && 1 && 0 && 0 && 0 && 0 && 0 && 0 && 1 && 2 && 1 \\
\end{array}
$$

In this structure, each row represents a level in Pascal's Triangle, and the numbers $0$, $1$, and $2$ reflect the values of the binomial coefficients modulo 3. As with the modulo 2 version, this triangle reveals interesting patterns and symmetries.

# Binomial Coefficient mod p, and the fractal pattern

To prove the statement that for a prime number $p$, a binomial coefficient $\binom{n}{k} \mod p = 0$ if $p$ divides $\binom{n}{k}$, and that this results in a fractal pattern in Pascal's Triangle modulo $p$, we can use some fundamental principles of number theory and combinatorics.

### Lucas' Theorem:
A key tool for this proof is Lucas' Theorem, which provides a way to compute binomial coefficients modulo a prime. Lucas' Theorem states that if $p$ is a prime and $n$ and $k$ are non-negative integers with base $p$ expansions $n = n_0 + n_1p + n_2p^2 + \cdots$ and $k = k_0 + k_1p + k_2p^2 + \cdots$, then

$$
\binom{n}{k} \equiv \binom{n_0}{k_0} \binom{n_1}{k_1} \binom{n_2}{k_2} \cdots \mod p
$$

### Proving the Zero Condition:

1. **Binomial Coefficients**: The binomial coefficient $\binom{n}{k}$ is defined as $\frac{n!}{k!(n-k)!}$, where $n!$ is the factorial of $n$.

2. **Division by Prime**: If $\binom{n}{k}$ is divisible by a prime $p$, it means $p$ divides the numerator of $\frac{n!}{k!(n-k)!}$ but not the denominator. 

3. **Lucas' Theorem Application**: According to Lucas' Theorem, for $\binom{n}{k} \mod p$ to be zero, there must be at least one term in the base $p$ expansion where $k_i > n_i$. This is because $\binom{n_i}{k_i} = 0$ if $k_i > n_i$.

4. **Implication in Pascal's Triangle**: In Pascal's Triangle, each entry is a binomial coefficient $\binom{n}{k}$. When applying Lucas' Theorem, the condition of $k_i > n_i$ leading to a zero directly creates a pattern because it depends on the base $p$ representation of $n$ and $k$. This pattern is repeated every $p$ rows, creating a fractal-like structure.

### Fractality in Pascal's Triangle Modulo $p$:

- The fractal pattern emerges because the condition of having a zero (or non-zero) value depends on the base $p$ digits of $n$ and $k$. This pattern is inherently recursive, much like the structure of a fractal.

- The repetition of the pattern every $p$ rows in the triangle is a direct result of the properties of the base $p$ expansions of $n$ and $k$. As $n$ increases, the higher-order digits in the base $p$ expansion come into play, replicating the pattern at a larger scale.

In conclusion, the binomial coefficient $\binom{n}{k}$ modulo a prime $p$ results in zeros whenever $p$ divides $\binom{n}{k}$, and this creates a fractal pattern in Pascal's Triangle. This phenomenon is fundamentally tied to the properties of numbers in base $p$ and the combinatorial structure of binomial coefficients.

# Highest power of a prime number $p$ that divides a given factorial $n!$

To determine the highest power of a prime number $p$ that divides a given factorial $n!$, we use a method based on the Legendre's formula. This method systematically accounts for the multiples of $p$, $p^2$, $p^3$, etc., that contribute to the prime factorization of $n!$.

### Theorem (Legendre's Formula):
The highest power of a prime $p$ that divides $n!$ is given by the sum of the integer quotients of $n$ divided by $p^i$, where $i$ ranges from $1$ to the largest integer for which $p^i \leq n$. Mathematically, this is expressed as:
$$
\text{The highest power of } p \text{ dividing } n! = \sum_{i=1}^{\infty} \left\lfloor \frac{n}{p^i} \right\rfloor
$$
However, this series terminates when $p^i > n$, as all subsequent terms will be zero.

### Proof:
1. **Counting Multiples**: Consider the multiples of $p$ up to $n$. There are $\left\lfloor \frac{n}{p} \right\rfloor$ such multiples. Each contributes at least one factor of $p$ to $n!$.

2. **Higher Powers of $p$**: Multiples of $p^2$ contribute an additional factor of $p$, beyond the first accounted for in step 1. There are $\left\lfloor \frac{n}{p^2} \right\rfloor$ such multiples.

3. **Continuing the Process**: This process continues for $p^3$, $p^4$, and so on. Each time, we count the multiples of $p^i$ that contribute an extra factor of $p$ not already counted in previous steps.

4. **Summation and Termination**: The total number of times $p$ divides $n!$ is the sum of all these contributions. The series naturally terminates as $\left\lfloor \frac{n}{p^i} \right\rfloor = 0$ for large $i$ ($p^i > n$).

### Algorithmic Method:
Given a prime $p$ and a number $n$, the highest power of $p$ dividing $n!$ can be found as follows:

1. Initialize a variable, say `power`, to 0. This will hold the sum of the quotients.

2. For each $i$ starting from 1, calculate $\left\lfloor \frac{n}{p^i} \right\rfloor$.

3. Add this quotient to `power`.

4. Repeat steps 2 and 3 until $\frac{n}{p^i} < 1$.

5. Return `power` as the result.

### Example:
Let's find the highest power of $2$ that divides $10!$.

- For $i = 1$: $\left\lfloor \frac{10}{2} \right\rfloor = 5$
- For $i = 2$: $\left\lfloor \frac{10}{4} \right\rfloor = 2$
- For $i = 3$: $\left\lfloor \frac{10}{8} \right\rfloor = 1$
- For $i = 4$: $\left\lfloor \frac{10}{16} \right\rfloor = 0$ (stop here)

So, the highest power of $2$ dividing $10!$ is $5 + 2 + 1 = 8$.

This method provides a rigorous and algorithmic approach to finding the highest power of a prime number that divides a factorial.

# Bounds for the Binomial Coefficient
To analyze the bounds of the binomial coefficient $\binom{n}{k}$, we can use the relationship between binomial coefficients and powers of 2, specifically $2^n$. This approach leverages the fact that the sum of the binomial coefficients over $k$ equals $2^n$:

$$
\sum_{k=0}^{n} \binom{n}{k} = 2^n
$$

This identity arises from the expansion of $(1+1)^n$ using the binomial theorem. 

### Upper Bound

For an upper bound, observe that each term in the sum is non-negative. Therefore, each binomial coefficient is less than or equal to the sum:

$$
\binom{n}{k} \leq \sum_{k=0}^{n} \binom{n}{k} = 2^n
$$

This provides a simple upper bound for the binomial coefficient.

### Lower Bound

For a lower bound, consider the middle term of the binomial expansion when $n$ is even, which is $\binom{n}{n/2}$. This term is known to be the largest among all $\binom{n}{k}$.

When $n$ is odd, the two middle terms $\binom{n}{\lfloor n/2 \rfloor}$ and $\binom{n}{\lceil n/2 \rceil}$ are the largest. In either case, since these terms collectively contribute significantly to the sum $2^n$, a lower bound can be established. A rough lower bound, for large $n$, is:

$$
\binom{n}{k} \geq \frac{2^n}{n+1}
$$

This is a crude estimate but useful in understanding the growth behavior of $\binom{n}{k}$.

### Proof of the Binomial Theorem Identity

The identity $\sum_{k=0}^{n} \binom{n}{k} = 2^n$ can be proven using the binomial theorem. The binomial theorem states that for any non-negative integer $n$:

$$
(a + b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k}b^k
$$

By setting $a = b = 1$, we obtain:

$$
2^n = (1 + 1)^n = \sum_{k=0}^{n} \binom{n}{k} 1^{n-k}1^k = \sum_{k=0}^{n} \binom{n}{k}
$$

This elegant result from the binomial theorem provides a fundamental understanding of the relationship between binomial coefficients and powers of 2, and is instrumental in establishing bounds for $\binom{n}{k}$.

# Stirling's Formula
Stirling's formula is a powerful tool for approximating factorials, particularly useful for large values of $n$. It provides a way to estimate $n!$ (the factorial of $n$) with a function that grows more slowly than the factorial itself.

### Stirling's Formula

The classic form of Stirling's formula is:

$$
n! \approx \sqrt{2 \pi n} \left( \frac{n}{e} \right)^n
$$

Here, $e$ is Euler's number, approximately equal to $2.71828$.

### Rationale Behind Stirling's Formula

Stirling's formula is based on approximating the logarithm of the factorial function and then exponentiating the result. The approximation is remarkably accurate for large $n$ and is often used in fields like statistics, physics, and combinatorics.

### Extended Stirling's Formula

An extended version of Stirling's formula provides a more accurate approximation by including additional terms. It is typically written as:

$$
n! \approx \sqrt{2 \pi n} \left( \frac{n}{e} \right)^n \left( 1 + \frac{1}{12n} + \frac{1}{288n^2} - \frac{139}{51840n^3} - \frac{571}{2488320n^4} + \cdots \right)
$$

This extension involves a series in powers of $1/n$. Each term in the series provides a correction that makes the approximation closer to the true value of $n!$. As $n$ grows larger, even the first few terms of this series yield a very precise approximation.

### Application of Stirling's Formula

Stirling's formula is particularly useful in asymptotic analysis, such as estimating the behavior of sequences or the computational complexity of algorithms. It's also instrumental in deriving other mathematical results where factorials appear, such as in the analysis of binomial coefficients or the gamma function.

### Mathematical Importance

The formula's significance lies in its ability to approximate a rapidly growing function like the factorial with a function that grows more slowly and is more manageable analytically. This makes Stirling's formula a cornerstone in the field of asymptotic analysis.

# Number of primes less that n
[[Lecture 2 - Survey of the Course#^c16ae1]]
## Weak form of the prime number theorem using binomial coefficients
The prime number theorem, in its simplest form, states that the number of primes less than or equal to a number $n$, denoted as $\pi(n)$, is approximately $\frac{n}{\ln(n)}$ as $n$ becomes large. There are many ways to approach this theorem, each with varying degrees of complexity and mathematical sophistication. One interesting approach is through the use of binomial coefficients. This proof, while not entirely elementary, is more accessible than some of the deep analytic methods involving complex analysis.

Here is a sketch of the proof using binomial coefficients:

1. **Central Binomial Coefficients:** We start by considering the central binomial coefficient $\binom{2n}{n}$. This coefficient counts the number of ways to choose $n$ items from a set of $2n$ items and grows rapidly as $n$ increases.

2. **Prime Number Distribution:** The key idea is to relate the growth rate of $\binom{2n}{n}$ to the distribution of prime numbers. Specifically, we use the fact that the prime factorization of $\binom{2n}{n}$ involves primes less than or equal to $2n$.

3. **Estimating $\binom{2n}{n}$:** We use the fact that $\binom{2n}{n} = \frac{(2n)!}{(n!)^2}$ and estimate $(2n)!$ and $(n!)^2$ by using prime number bounds. For example, using the factorial's prime factorization, we can show that the number of times a prime $p$ appears in $(2n)!$ is about twice the number of times it appears in $(n!)^2$ for large $n$. 

4. **Logarithmic Estimates:** By taking logarithms, we can relate the estimates of $\binom{2n}{n}$ to sums involving the prime counting function $\pi(x)$. The logarithm of a factorial can be linked to the sum of logarithms of primes, leading to expressions involving $\pi(x)$.

5. **Approximations and Limits:** The final step involves delicate approximations and limit arguments to show that $\pi(x)$ must behave like $\frac{x}{\ln(x)}$ for large $x$. This is often done by considering upper and lower bounds for the growth rate of $\binom{2n}{n}$ and showing that these bounds force $\pi(x)$ to be close to $\frac{x}{\ln(x)}$.

6. **Conclusion:** By piecing together these estimates and bounds, we arrive at the conclusion that $\pi(n) \sim \frac{n}{\ln(n)}$ as $n \to \infty$, which is the statement of the prime number theorem in its weak form.

This sketch glosses over many technical details and rigorous justifications needed for a complete proof. The actual proof requires careful handling of the estimates and limits, as well as a deep understanding of the properties of prime numbers and binomial coefficients.

## Combinatorial Approach to the Binomial Theorem
A more combinatorial approach to a weak form of the prime number theorem, which leverages the interesting property that a prime $p$ divides $\binom{2n}{n}$ exactly once for $n < p \leq 2n$. This approach, while not giving the full strength of the prime number theorem, does offer a fascinating insight into the distribution of prime numbers. Let's sketch this proof:

1. **Property of Binomial Coefficients:** First, we consider the binomial coefficient $\binom{2n}{n}$, and note that if $p$ is a prime such that $n < p \leq 2n$, then $p$ divides $\binom{2n}{n}$ exactly once. This is because the factor $p$ appears in the numerator of $\binom{2n}{n}$ (as part of $(2n)!$) but not in the denominator (since $n!$ has no factor of $p$ and $(n!)^2$ therefore cannot cancel it out).

2. **Counting Primes in a Range:** For a given $n$, we count the number of primes in the range $n < p \leq 2n$. Each of these primes divides $\binom{2n}{n}$ exactly once. As $n$ increases, the number of such primes gives us a lower bound on the number of primes up to $2n$.

3. **Estimating $\binom{2n}{n}$:** We use known estimates for the size of $\binom{2n}{n}$. For instance, using Stirling's approximation, we can show that $\binom{2n}{n}$ is approximately $\frac{4^n}{\sqrt{\pi n}}$ for large $n$.

4. **Connecting Prime Counts to Binomial Coefficient:** The fact that each prime in the interval $(n, 2n]$ divides $\binom{2n}{n}$ exactly once implies that the product of these primes is a divisor of $\binom{2n}{n}$. This provides a way to connect the magnitude of $\binom{2n}{n}$ with the count of primes in a specific range.

5. **Deriving a Bound on Prime Counting Function:** By comparing the size of $\binom{2n}{n}$ with the product of primes in the range $(n, 2n]$, we can establish a lower bound on the number of such primes. This leads to a lower bound on $\pi(2n) - \pi(n)$, the number of primes between $n$ and $2n$. 

6. **Conclusion:** The result is a weak form of the prime number theorem. It does not directly show that $\pi(n) \sim \frac{n}{\ln(n)}$, but it does demonstrate that there are a significant number of primes in every interval of the form $(n, 2n]$, especially as $n$ becomes large. This aligns with the intuition that primes, though they become less frequent as numbers grow larger, are nonetheless not too sparse.

This approach is quite elegant in that it uses a combinatorial fact about binomial coefficients to derive information about the distribution of prime numbers. However, it should be noted that this method does not yield the precise asymptotic formula for $\pi(n)$ that the full prime number theorem provides.

# Lower Bound for Primes
To use a combinatorial approach with binomial coefficients for finding a lower bound for the number of primes, we can proceed with the following steps:

1. **Property of Prime Numbers and Binomial Coefficients**: We begin by noting a crucial property related to prime numbers and binomial coefficients. For a prime number $p$ and any integer $n$ such that $p \leq n < 2p$, the prime $p$ divides the binomial coefficient $\binom{2n}{n}$. This is because in the prime factorization of the numerator of $\binom{2n}{n} = \frac{(2n)!}{n!n!}$, the prime $p$ will appear, but it will not be completely cancelled out by the factors in the two $n!$ in the denominator, as $n < 2p$ ensures $p$ appears only once in each $n!$.

2. **Counting Primes Using Binomial Coefficients**: For a given $n$, consider the binomial coefficient $\binom{2n}{n}$. We know that every prime $p$ with $n < p \leq 2n$ divides this binomial coefficient exactly once. This observation is key.

3. **Estimating $\binom{2n}{n}$**: Utilize an estimate for $\binom{2n}{n}$. Stirling's approximation is a common choice for this. It gives us an asymptotic form for $n!$, leading to an approximate value for $\binom{2n}{n}$ which grows exponentially with $n$.

4. **Establishing a Lower Bound on Prime Count**: The product of all primes $p$ such that $n < p \leq 2n$ must divide $\binom{2n}{n}$. Given that $\binom{2n}{n}$ grows exponentially, this implies that the number of such primes is significant. Specifically, if we denote by $P(n, 2n)$ the product of all primes in the interval $(n, 2n]$, then $P(n, 2n) \leq \binom{2n}{n}$.

5. **Deriving the Lower Bound**: We can use the inequality $P(n, 2n) \leq \binom{2n}{n}$ and our estimate for $\binom{2n}{n}$ to derive a lower bound on the number of primes between $n$ and $2n$. 

6. **Conclusion**: This provides a combinatorial proof that there are infinitely many primes and also gives a rough lower bound on the density of primes. However, it doesn't directly provide the precise asymptotic density of primes as in the prime number theorem, $\pi(n) \sim \frac{n}{\ln(n)}$. 

In summary, this combinatorial approach with binomial coefficients is a beautiful way to understand some aspects of the distribution of prime numbers, highlighting the deep connections between different areas of mathematics, such as combinatorics and number theory. However, for the exact distribution as described by the prime number theorem, more advanced tools from complex analysis and number theory are required.

## Rigorous Proof for the lower bound
A self-contained proof for a lower bound on the number of primes between $n$ and $2n$ using binomial coefficients, considering the information provided.

**Theorem**: For sufficiently large $n$, there exists a positive number of prime numbers in the interval $(n, 2n]$.

**Proof**:

We start by considering the central binomial coefficient $\binom{2n}{n}$. It's known that for any prime $p$, if $n < p \leq 2n$, then $p$ divides $\binom{2n}{n}$ exactly once. This is because $p$ will appear in the numerator $(2n)!$ but not twice in the denominator $n!n!$, since $n < p$ and there is no other prime to pair with $p$ to cancel it out from the numerator.

Let's define $P(n, 2n)$ as the product of all prime numbers in the interval $(n, 2n]$. Then each of these primes divides $\binom{2n}{n}$ exactly once. Therefore:

$$ P(n, 2n) \leq \binom{2n}{n}. $$

Using Stirling's approximation, we can estimate $\binom{2n}{n}$ as follows:

$$ \binom{2n}{n} \approx \frac{4^n}{\sqrt{\pi n}}. $$

Taking logarithms on both sides, we get:

$$ \log(P(n, 2n)) \leq \log\left(\binom{2n}{n}\right) \approx n \log 4 - \frac{1}{2}\log(\pi n). $$

The left side, $\log(P(n, 2n))$, can be expanded to the sum of the logarithms of all the primes in the interval $(n, 2n]$. Now, since $\log(x)$ is an increasing function, and $\log(p) > \log(n)$ for all $p$ in the interval $(n, 2n]$, we can say:

$$ \sum_{n < p \leq 2n} \log(p) \geq \sum_{n < p \leq 2n} \log(n). $$

If there are $k$ primes in the interval $(n, 2n]$, then the sum on the right-hand side is just $k \log(n)$, giving us:

$$ \log(P(n, 2n)) \geq k \log(n). $$

Combining our inequalities, we have:

$$ k \log(n) \leq n \log 4 - \frac{1}{2}\log(\pi n). $$

Solving for $k$, we get a lower bound for the number of primes in $(n, 2n]$:

$$ k \geq \frac{n \log 4 - \frac{1}{2}\log(\pi n)}{\log(n)}. $$

As $n$ grows, the term $\frac{1}{2}\log(\pi n)$ becomes insignificant compared to $n \log 4$, so we can approximate further that:

$$ k \geq \frac{n \log 4}{\log(n)} - \text{small error term}. $$

Hence, for sufficiently large $n$, $k$ is positive, meaning there are at least a few primes in the interval $(n, 2n]$. This provides a combinatorial proof of a weak form of the prime number theorem, showing that the number of primes is not too sparse, especially in the intervals of the form $(n, 2n]$.

**QED**.

This proof does not give the exact count or the distribution of the primes as in the prime number theorem but provides a lower bound showing that primes are relatively numerous, even as we go to larger intervals.

# Middle Binomial Coefficient and the Catalan Numbers


The binomial coefficient $\binom{2n}{n}$ represents the number of ways to choose $n$ items from a set of $2n$ items. The sequence of central binomial coefficients starts as $1, 2, 6, 20, 70, \ldots$ for $n=0, 1, 2, 3, 4, \ldots$ respectively.

The image notes that $\binom{2n}{n}$ is divisible by $n+1$. This is indeed a property of the central binomial coefficient because of the symmetry in Pascal's triangle. To show this formally, we can write the binomial coefficient as:

$$ \binom{2n}{n} = \frac{(2n)!}{(n!)^2} = \frac{2n \cdot (2n-1) \cdot \ldots \cdot (n+1)}{n!}. $$

From this form, it's clear that there's a factor of $n+1$ in the numerator which is not canceled by any term in the denominator, thus ensuring divisibility by $n+1$.

Now, the sequence $1, 1, 2, 5, 14, \ldots$, represents the Catalan numbers. Catalan numbers are a sequence of natural numbers that have many applications in combinatorics. The $n$-th Catalan number is given by the formula:

$$ C_n = \frac{1}{n+1} \binom{2n}{n}. $$

Catalan numbers can be used to count various combinatorial structures, one of which is mentioned in the image: the number of different ways to correctly bracket a product of $n+1$ factors. The proof that the $n$-th Catalan number counts the number of ways to correctly bracket a product of $n+1$ factors can be seen through a recursive construction known as Dyck paths, but that's beyond the scope of what's provided in the image.

**Proof that $C_n$ is an integer**:

Given the above formula for $C_n$, a priori it is not obvious that $C_n$ is an integer. However, we know that $\binom{2n}{n}$ is divisible by $n+1$ due to the symmetry in Pascal's triangle mentioned earlier. Hence, when we divide $\binom{2n}{n}$ by $n+1$, we are guaranteed to get an integer, which we define as the Catalan number $C_n$.

Therefore, we can conclude that $C_n$ is indeed an integer for all natural numbers $n$, and it gives the count for the number of ways to bracket a product of $n+1$ factors, among other combinatorial structures.

**QED**.

In conclusion, the central binomial coefficient $\binom{2n}{n}$ is closely related to the Catalan numbers, and both play significant roles in combinatorics. The proof that $\binom{2n}{n}$ is divisible by $n+1$ is straightforward and is used to show that the Catalan numbers, which have many interesting combinatorial interpretations, are always integers.

# Generating functions and Catalan Numbers 

1. **Catalan Numbers Recurrence Relation**:
   The recurrence relation for Catalan numbers is given by:
   $$ C_n = C_0C_{n-1} + C_1C_{n-2} + \ldots + C_{n-1}C_0 $$

2. **Generating Function for Catalan Numbers**:
   The generating function $f(x)$ for Catalan numbers is expressed as a series:
   $$ f(x) = C_0 + C_1x + C_2x^2 + \ldots $$

3. **Functional Equation for the Generating Function**:
   A functional equation based on the generating function and the recurrence relation is derived:
   $$ f(x)^2 = C_0^2 + (C_0C_1 + C_1C_0)x + (C_0C_2 + C_1C_1 + C_2C_0)x^2 + \ldots $$

4. **Closed-Form Equation of the Generating Function**:
   By using the properties of the generating function and the recurrence relation, a closed-form equation for $f(x)$ is derived:
   $$ 1 + xf(x)^2 = f(x) $$
   This leads to the quadratic equation:
   $$ xf(x)^2 - f(x) + 1 = 0 $$
   Solving for $f(x)$, we get:
   $$ f(x) = \frac{1 \pm \sqrt{1 - 4x}}{2x} $$
   Since the generating function must be a power series starting with $1$, we discard the negative root, leading to the correct formula:
   $$ f(x) = \frac{1 - \sqrt{1 - 4x}}{2x} $$


# Uses of Catalans
Catalan numbers, a sequence of natural numbers with extensive applications in combinatorial mathematics, are famously discussed in Richard Stanley's work. Named after the Belgian mathematician Eugène Charles Catalan, these numbers have a beautiful and recurring presence in various counting problems, particularly those involving recursive structures and binary operations.

The $n$-th Catalan number is denoted as $C_n$ and can be expressed using the formula:

$$ C_n = \frac{1}{n+1} \binom{2n}{n} = \frac{(2n)!}{(n+1)!n!} $$

This formula elegantly encapsulates the recursive nature of these numbers. They can also be defined recursively as:

$$ C_0 = 1 \quad \text{and} \quad C_{n+1} = \sum_{i=0}^{n} C_i C_{n-i} \text{ for } n \geq 0 $$

Richard Stanley, a prominent figure in combinatorics, has explored and expanded upon the applications and properties of Catalan numbers in his works. His elucidations bring forth the depth and versatility of these numbers in contexts such as:

1. **Counting Binary Trees**: The number of distinct binary trees with $n$ nodes is given by the $n$-th Catalan number.
2. **Parentheses Matching**: Catalan numbers enumerate the ways of correctly matching $n$ pairs of parentheses.
3. **Polygon Triangulation**: They also count the number of ways to divide a convex polygon with $n+2$ sides into triangles by non-intersecting diagonals.
4. **Paths in Grids**: In a square lattice, Catalan numbers describe the number of paths along the edges of squares that do not cross above the diagonal.

The poetic beauty of Catalan numbers lies in their ability to intertwine simplicity and complexity, weaving through numerous combinatorial problems with a graceful, recursive dance. Stanley's work illuminates these aspects, showcasing how foundational mathematical concepts can resonate across varied and complex scenarios.