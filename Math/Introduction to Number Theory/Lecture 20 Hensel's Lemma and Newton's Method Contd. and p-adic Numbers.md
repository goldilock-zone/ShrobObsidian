Hensel's Lemma is a result in number theory that allows one to lift solutions of congruences from a modulus $p$ to a modulus $p^n$ under certain conditions. Specifically, if you have a polynomial $f(x)$ with integer coefficients, and you find a solution $x_0$ to the congruence $f(x) \equiv 0 \mod p$, under certain conditions you can find a unique solution $x_n$ to the congruence $f(x) \equiv 0 \mod p^n$ which is congruent to $x_0$ modulo $p$.

Newton's method is an iterative numerical method used to approximate the roots of a real-valued function. It can be adapted to work in modular arithmetic to find solutions to $f(x) \equiv 0 \mod p^n$ given an initial solution $x_0$ to $f(x) \equiv 0 \mod p$. The adaptation of Newton's method in modular arithmetic involves iteratively applying the formula:

$$
x_{i+1} = x_i - \frac{f(x_i)}{f'(x_i)}
$$

where $f'(x_i) \not\equiv 0 \mod p$. The division by $f'(x_i)$ means multiplying by the modular inverse of $f'(x_i)$ modulo $p$.

The condition $f'(x_i) \not\equiv 0 \mod p$ is essential because otherwise the method would not be well-defined as division by zero is not allowed, even in modular arithmetic. When this condition is satisfied, the algorithm can be used to refine an approximate solution modulo $p$ to a solution modulo higher powers of $p$, essentially lifting the solution to a higher precision in the $p$-adic numbers.

# Extended Hensel's Lemma
If the situation arises where $f'(x_i) \equiv 0 \mod p$, it signifies that the derivative of the function $f(x)$ evaluates to zero at the point $x_i$ modulo $p$. This particular scenario presents a challenge when applying Newton's method since the method relies on the derivative not being zero to compute the subsequent iteration.

When $f'(x_i) \equiv 0 \mod p$, it indicates that the function $f(x)$ possesses what is referred to as a "multiple root" modulo $p$. In such instances, the direct application of Hensel's Lemma is not feasible because the conventional version of the lemma necessitates the derivative to be non-zero modulo $p$ for the lifting process to be effective.

Nevertheless, there exists an extended version of Hensel's Lemma that accommodates specific cases where $f'(x) \equiv 0 \mod p$. This extended lemma asserts that if $f(x_0) \equiv 0 \mod p^m$ and $f'(x_0) \equiv 0 \mod p^k$, with $2k < m$, then a unique $x$ exists such that $f(x) \equiv 0 \mod p^{m-k}$ and $x \equiv x_0 \mod p^{m-k}$.

In situations where $f'(x) \equiv 0 \mod p$ and the objective is to determine a root of $f(x) \equiv 0 \mod p^n$, alternative methods or modified versions of Newton's method are necessary to address such cases effectively. One potential approach is to factor out the greatest common divisor (GCD) of $f(x)$ and $f'(x)$ modulo $p^n$. Alternatively, one may need to employ an alternative root-finding algorithm specifically designed to handle roots with multiplicity in cases like these.

# How does the extended Hensel's Lemma help us?
The extended version of Hensel's Lemma is a valuable tool in "lifting" solutions from lower modulo powers to higher ones in the context of modular arithmetic. Let's elaborate on how this lemma assists us in solving congruences and how the lifting process works.

Suppose we have a polynomial equation of the form $f(x) \equiv 0 \mod p^n$, where $p$ is a prime number and $n$ is a positive integer. Initially, we might encounter a situation where $f'(x_0) \equiv 0 \mod p$ at some point $x_0$ when applying Newton's method or any other root-finding technique. This means that the derivative of the polynomial $f(x)$ is zero modulo $p$ at $x_0$, which implies that $f(x)$ has a multiple root modulo $p$ at $x_0$.

Here's how the extended Hensel's Lemma helps us:

1. **Initialization**: We start with a solution $x_0$ that satisfies $f(x_0) \equiv 0 \mod p^m$ and $f'(x_0) \equiv 0 \mod p^k$, where $2k < m$. This is the initial "lift."

2. **Lifting**: The lemma tells us that there exists a unique solution $x$ such that $f(x) \equiv 0 \mod p^{m-k}$ and $x \equiv x_0 \mod p^{m-k}$. This process effectively "lifts" the solution from modulo $p^k$ to modulo $p^m$. 

3. **Reiteration**: We can repeat this process iteratively, increasing $m$ each time, until we have "lifted" the solution to modulo $p^n$, where we originally wanted to find a solution.

The key idea here is that we can find solutions to the congruence $f(x) \equiv 0 \mod p^n$ by first finding a solution modulo $p^m$ where $m$ is greater than or equal to $n$. The lemma ensures that the solution can be systematically lifted from lower modulo powers to higher ones until we reach the desired modulo $p^n$. Each lifting step guarantees a unique solution within the specified modulo.

The extended Hensel's Lemma essentially provides a systematic way to handle cases where the derivative of the polynomial is zero modulo $p$, allowing us to find solutions to congruences that would otherwise pose challenges for standard root-finding methods.

# Proof of Extended Hensel's Lemma
**Extended Hensel's Lemma**: Suppose $p$ is a prime number, and $f(x)$ is a polynomial with integer coefficients. Let $x_0$ be an integer such that $f(x_0) \equiv 0 \mod p^m$ and $f'(x_0) \equiv 0 \mod p^k$, where $2k < m$. Then, there exists a unique integer $x$ such that $f(x) \equiv 0 \mod p^{m-k}$ and $x \equiv x_0 \mod p^{m-k}$.

**Proof**:

**Step 1: Existence of a Solution**:
Let $g(x)$ be a polynomial defined as follows:
$$
g(x) = \frac{f(x)}{p^k}.
$$
Notice that $f(x_0) \equiv 0 \mod p^m$ implies that $g(x_0) \equiv 0 \mod p^{m-k}$.

Now, consider the Taylor series expansion of $g(x)$ centered at $x_0$:
$$
g(x) = g(x_0) + (x - x_0)g'(x_0) + \frac{(x - x_0)^2}{2!}g''(x_0) + \ldots.
$$
Since $f'(x_0) \equiv 0 \mod p^k$, we have $g'(x_0) \equiv 0 \mod p$. Thus, the expansion can be written as:
$$
g(x) = g(x_0) + \frac{(x - x_0)^2}{2!}g''(x_0) + \ldots.
$$

Now, we aim to find an integer $x$ such that $g(x) \equiv 0 \mod p^{m-k}$. To do this, we need to choose $x$ such that:
$$
(x - x_0)^2 \equiv -g(x_0) \cdot 2! \cdot [g''(x_0)]^{-1} \mod p^{m-k}.
$$
This congruence is solvable because $-g(x_0) \cdot 2! \cdot [g''(x_0)]^{-1}$ is an integer not divisible by $p$ (since $p \nmid g(x_0)$, and $p$ does not divide any of the coefficients of $g''(x_0)$). Therefore, there exists a solution $x$ modulo $p^{m-k}$.

**Step 2: Uniqueness of the Solution**:
Suppose there are two solutions, $x$ and $y$, modulo $p^{m-k}$, both satisfying $f(x) \equiv 0 \mod p^{m-k}$ and $f(y) \equiv 0 \mod p^{m-k}$.

Then, we have:
$$
g(x) \equiv 0 \mod p^{m-k} \quad \text{and} \quad g(y) \equiv 0 \mod p^{m-k}.
$$

Since $g(x) \equiv g(y) \equiv g(x_0) \mod p^{m-k}$, we can subtract these congruences:
$$
g(x) - g(y) \equiv 0 \mod p^{m-k}.
$$

Now, using the fact that $g(x)$ has a factor of $p^k$:
$$
p^k(x - y) \equiv 0 \mod p^{m-k}.
$$

Since $p^k$ is not divisible by $p^{m-k}$ (because $k < m-k$), we conclude that $x - y \equiv 0 \mod p^{m-k}$, which implies that $x \equiv y \mod p^{m-k}$.

Thus, there is only one solution $x$ modulo $p^{m-k}$, satisfying both $f(x) \equiv 0 \mod p^{m-k}$ and $x \equiv x_0 \mod p^{m-k}$.

This completes the proof of the extended Hensel's Lemma.

# p-adic numbers

$p$-adic numbers are a fundamental concept in number theory, offering a different perspective on the structure of numbers. They are an extension of our familiar real numbers and play a crucial role in various areas of mathematics, including algebraic number theory and arithmetic geometry.

**Definition**:

Let $p$ be a prime number. A $p$-adic number is a way to represent numbers in a base-$p$ expansion, but unlike our standard decimal representation, $p$-adic numbers allow infinitely many digits to the left of the decimal point. Formally, a $p$-adic number is a sequence of integers $\{a_n\}_{n=0}^\infty$ where each $a_n$ is an integer between $0$ and $p-1$. This sequence represents the number:

$$
a_0 + a_1p + a_2p^2 + a_3p^3 + \ldots
$$

**Example**:

Let's consider the $5$-adic number system. A $5$-adic number can be represented as an infinite sequence of digits, where each digit can be $0$, $1$, $2$, $3$, or $4$. For instance, the sequence $\{1, 3, 2, 4, 0, 0, 0, \ldots\}$ represents the $5$-adic number:

$$
1 + 3\cdot 5 + 2\cdot 5^2 + 4\cdot 5^3 + 0\cdot 5^4 + \ldots = -4
$$

In the $5$-adic system, $-4$ is a legitimate number, even though it looks negative in our standard notation.

**Fundamental Theorems**:

1. **Hensel's Lemma**: Hensel's Lemma is a fundamental result in the theory of $p$-adic numbers. It provides a method for lifting solutions of polynomial equations from lower powers of $p$ to higher powers. 

   **Statement of Hensel's Lemma**:
   Let $p$ be a prime number, and let $f(x)$ be a polynomial with integer coefficients. Suppose there exists an integer solution $a$ such that $f(a) \equiv 0 \mod p^k$ and $f'(a) \not\equiv 0 \mod p$. Then, there exists a unique integer solution $b$ such that $f(b) \equiv 0 \mod p^{k+1}$.

2. **Ultrametric Inequality**: In the $p$-adic metric, distances between numbers are measured differently compared to the real numbers. 

   **Statement of Ultrametric Inequality**:
   For any integers $a$ and $b$, in the $p$-adic metric, $|ab|_p \leq \max(|a|_p, |b|_p)$.

3. **p-adic Expansion**: Every rational number can be represented uniquely as a $p$-adic number, and the $p$-adic expansion provides insight into the divisibility properties of integers and the behavior of rational numbers in the $p$-adic world.

4. **p-adic Valuation**: The $p$-adic valuation of a non-zero rational number $a$, denoted as $v_p(a)$, measures the highest power of $p$ that divides $a$. 

   **Statement of p-adic Valuation**:
   For any non-zero rational number $a$, $v_p(a)$ is the highest power of $p$ such that $p^{v_p(a)}$ divides $a$.

# **Notion of Convergence in p-adic Numbers**:

In the study of $p$-adic numbers, a critical concept is the notion of convergence, which determines when a sequence of $p$-adic numbers approaches a limit. Unlike the standard real numbers, where convergence is based on the absolute value metric, $p$-adic convergence is established using the $p$-adic metric. 

**Definition of p-adic Metric**:
For a prime number $p$, the $p$-adic metric on the rational numbers $\mathbb{Q}$ is defined as follows: For any two rational numbers $a$ and $b$, the $p$-adic distance between them, denoted as $d_p(a, b)$, is given by:

$$
d_p(a, b) = \begin{cases} 
0 & \text{if } a = b \\
p^{-n} & \text{if } a \neq b, \text{ where } n \text{ is the largest integer such that } p^n \text{ divides } a - b.
\end{cases}
$$

This definition leads to a metric space known as the $p$-adic numbers $\mathbb{Q}_p$, where the distance between two numbers is measured in a different way compared to the Euclidean metric on real numbers.

**Convergence in p-adic Numbers**:

In the context of $p$-adic numbers, a sequence $\{a_n\}$ is said to converge to a limit $L$ if, for any positive integer $k$, there exists an integer $N$ such that for all $n \geq N$, the terms $a_n$ and $L$ are "close" in the $p$-adic metric. Formally, this can be expressed as:

$$
\lim_{n \to \infty} a_n = L \quad \text{if and only if} \quad d_p(a_n, L) \leq p^{-k} \text{ for all } n \geq N.
$$

In other words, as $n$ becomes sufficiently large, the terms of the sequence get arbitrarily close to the limit $L$ in the $p$-adic metric.

**Questions to Consider**:

1. How does the notion of $p$-adic convergence compare to the convergence of sequences in the real numbers?
2. Are there any unique properties or behaviors of sequences in $\mathbb{Q}_p$ that differ from those in the real numbers?
3. Can you provide an example of a sequence in $\mathbb{Q}_p$ and demonstrate its convergence to a $p$-adic limit?
4. How is the concept of a Cauchy sequence related to convergence in $p$-adic numbers?


# $p$-adic convergence compared to the convergence of sequences in the real numbers
**Comparison of $p$-adic Convergence with Real Number Convergence**:

The notion of $p$-adic convergence exhibits several key differences when compared to the convergence of sequences in the real numbers. These distinctions arise from the unique properties of the $p$-adic metric and the underlying $p$-adic number system.

1. **Metric Structure**:
   - In the real numbers, convergence is typically measured using the Euclidean metric based on the absolute value. Sequences converge when the terms become arbitrarily close to the limit in terms of their absolute differences.
   - In contrast, $p$-adic convergence employs the $p$-adic metric. Here, sequences converge when the terms become arbitrarily close to the limit in a way that considers the highest power of the prime number $p$ dividing their differences. This results in a different distance metric with unique properties.

2. **Closeness in the Metric**:
   - Real numbers require convergence to be defined by closeness in the standard Euclidean metric, where terms approach the limit in a way that minimizes their absolute differences.
   - In $p$-adic numbers, closeness is defined by the $p$-adic metric, where terms approach the limit in a way that minimizes their $p$-adic differences, focusing on the highest power of $p$ that divides their differences. This can lead to counterintuitive behavior, where terms can appear to get "farther apart" as the sequence converges.

3. **Divergence Behavior**:
   - In real numbers, if a sequence does not converge, it typically diverges either to positive or negative infinity or oscillates indefinitely.
   - $p$-adic numbers exhibit different divergence behaviors. A sequence in $p$-adic numbers can fail to converge to a real number but may still converge to a $p$-adic limit. Additionally, $p$-adic numbers have the property that if a sequence does not converge in $\mathbb{Q}_p$, it may still have a $p$-adic limit in the extended $p$-adic field.

4. **Cauchy Sequences**:
   - In real numbers, a Cauchy sequence is one in which the terms become arbitrarily close to each other. Every Cauchy sequence in real numbers converges to a real limit.
   - In $p$-adic numbers, Cauchy sequences have a stronger convergence property. Every Cauchy sequence in $\mathbb{Q}_p$ converges to a $p$-adic limit within $\mathbb{Q}_p$ itself.

5. **Archimedean vs. Non-Archimedean**:
   - The real numbers follow the Archimedean property, meaning that there is no upper bound on how far apart terms in a sequence can be.
   - $p$-adic numbers are non-Archimedean, implying that the terms in a sequence can get arbitrarily close to each other as the sequence progresses. This property allows for different convergence behavior.

In summary, $p$-adic convergence is fundamentally different from convergence in the real numbers due to the unique properties of the $p$-adic metric and the $p$-adic number system. While real numbers focus on minimizing absolute differences, $p$-adic numbers prioritize the highest power of the prime $p$ dividing differences, leading to distinctive convergence patterns and behaviors. Understanding these differences is essential when working with $p$-adic analysis and its applications in number theory and beyond.

# **Concrete Example of Convergence in p-adic Numbers**:

Let's explore a concrete example of convergence in the $p$-adic numbers to gain a better understanding of how it works. We will consider the $2$-adic numbers, $\mathbb{Q}_2$, and a specific sequence that converges within this number system.

**Example**:

Consider the sequence $\{a_n\}$ defined as follows in $\mathbb{Q}_2$:

$$
a_n = 1 + 2 + 2^2 + 2^3 + \ldots + 2^n
$$

This sequence represents the partial sums of the geometric series $1 + 2 + 2^2 + 2^3 + \ldots$, and each term $a_n$ is a $2$-adic number. We want to investigate the convergence of this sequence in the $2$-adic metric.

**Analysis**:

1. **Calculation of Terms**:
   - To calculate $a_n$, we sum the geometric series up to the $n$-th term. The formula for the sum of a geometric series is given by:
     $$
     S_n = \frac{a(1 - r^n)}{1 - r}
     $$
     where $a$ is the first term, $r$ is the common ratio, and $n$ is the number of terms. In our case, $a = 1$ and $r = 2$.
   - Substituting these values into the formula:
     $$
     a_n = \frac{1(1 - 2^n)}{1 - 2} = 2^n - 1
     $$

2. **Checking Convergence**:
   - We want to find the $2$-adic limit of this sequence as $n$ approaches infinity. In other words, we want to determine if there exists a $2$-adic number $L$ such that:
     $$
     \lim_{n \to \infty} a_n = L
     $$
   - We need to show that for any positive integer $k$, there exists an integer $N$ such that for all $n \geq N$, the $2$-adic difference $|a_n - L|_2 \leq 2^{-k}$.

3. **Calculating the Limit**:
   - We take the limit of $a_n$ as $n$ goes to infinity:
     $$
     \lim_{n \to \infty} a_n = \lim_{n \to \infty} (2^n - 1)
     $$
   - This limit does not approach a real number, but it does have a $2$-adic limit within $\mathbb{Q}_2$.
   - In the $2$-adic metric, as $n$ grows larger, the difference between $2^n$ and $1$ in $|2^n - 1|_2$ becomes smaller and smaller because $2^n$ gets "closer" to $1$ in the $2$-adic sense.

4. **Convergence**:
   - We have shown that for any positive integer $k$, there exists an integer $N$ such that for all $n \geq N$, the $2$-adic difference $|a_n - 1|_2 \leq 2^{-k}$.
   - Therefore, the sequence $\{a_n\}$ converges to the $2$-adic number $1$ in the $2$-adic metric, denoted as:
     $$
     \lim_{n \to \infty} a_n = 1
     $$

This example illustrates how a sequence of $2$-adic numbers can converge to a $2$-adic limit, which may not be a real number but still has significance within the $2$-adic number system. Convergence in $p$-adic numbers follows a different set of rules compared to real numbers, taking into account the $p$-adic metric and its unique properties. 

# **Addition and Multiplication of p-adic Numbers**:

In the realm of $p$-adic numbers, addition and multiplication follow unique rules due to the non-Archimedean nature of the $p$-adic metric. Understanding these operations is crucial when working with $p$-adic numbers.

**Addition**:

Let's consider the addition of two $p$-adic numbers, $a$ and $b$, in $\mathbb{Q}_p$. The key principle to remember is that when adding $p$-adic numbers, we carry out the addition digit by digit, considering the $p$-adic valuation.

- Given $a = \sum_{i=0}^\infty a_ip^i$ and $b = \sum_{i=0}^\infty b_ip^i$, where $a_i$ and $b_i$ are the $p$-adic digits.
- To add $a$ and $b$, we add their corresponding digits, taking care of carrying over any excess to the next digit.
- Formally, the sum $a + b$ is computed as follows:
  $$
  a + b = \sum_{i=0}^\infty (a_i + b_i)p^i
  $$

**Example of Addition in 2-adic Numbers**:

Let's add two $2$-adic numbers, $a$ and $b$, where $a = \ldots2101_2$ and $b = \ldots1200_2$. The ellipses indicate that there are more $p$-adic digits to the left.

- Adding digit by digit:
  $$
  \begin{align*}
  a_0 + b_0 &= 1 + 0 = 1 \text{ (no carry)} \\
  a_1 + b_1 &= 0 + 0 = 0 \text{ (no carry)} \\
  a_2 + b_2 &= 1 + 0 = 1 \text{ (no carry)} \\
  a_3 + b_3 &= 2 + 1 = 0 \text{ (carry 1)} \\
  &\vdots
  \end{align*}
  $$
- Taking care of the carry:
  $$
  \ldots1000_2
  $$

So, $a + b = \ldots1000_2$, which represents a $2$-adic number.

**Multiplication**:

Multiplying two $p$-adic numbers, $a$ and $b$, is also performed digit by digit. The key difference here is that we need to consider the $p$-adic valuation when multiplying the digits.

- Given $a = \sum_{i=0}^\infty a_ip^i$ and $b = \sum_{i=0}^\infty b_ip^i$, where $a_i$ and $b_i$ are the $p$-adic digits.
- To multiply $a$ and $b$, we multiply their corresponding digits and take into account the $p$-adic valuation of the result.
- Formally, the product $ab$ is computed as follows:
  $$
  ab = \sum_{i=0}^\infty (a_i b_i)p^i
  $$

**Example of Multiplication in 3-adic Numbers**:

Let's multiply two $3$-adic numbers, $a$ and $b$, where $a = \ldots2101_3$ and $b = \ldots1200_3$.

- Multiplying digit by digit:
  $$
  \begin{align*}
  a_0b_0 &= 1 \cdot 0 = 0 \cdot 3^0 = 0 \\
  a_1b_1 &= 0 \cdot 0 = 0 \cdot 3^1 = 0 \\
  a_2b_2 &= 1 \cdot 0 = 0 \cdot 3^2 = 0 \\
  a_3b_3 &= 2 \cdot 1 = 2 \cdot 3^3 = 18 = 6 \cdot 3^2 \\
  &\vdots
  \end{align*}
  $$

So, $ab = \ldots0006_3$, representing a $3$-adic number.

In summary, addition and multiplication of $p$-adic numbers are carried out digit by digit, considering the $p$-adic valuation. These operations are fundamental when performing arithmetic within the $p$-adic number system and exhibit distinct behavior compared to arithmetic in the real numbers.

# Subtraction of p-adic numbers

Subtracting two $p$-adic numbers, $a$ and $b$, in the $p$-adic number system follows a similar process to addition. Just like in addition, subtraction in the $p$-adic system is performed digit by digit while considering the $p$-adic valuation.

Let's denote $a = \sum_{i=0}^\infty a_ip^i$ and $b = \sum_{i=0}^\infty b_ip^i$, where $a_i$ and $b_i$ are the $p$-adic digits.

To subtract $b$ from $a$, we subtract their corresponding digits while taking care of borrowing when necessary:

- The difference $a - b$ is computed as follows:
  $$
  a - b = \sum_{i=0}^\infty (a_i - b_i)p^i
  $$

**Example of Subtraction in 5-adic Numbers**:

Let's subtract two $5$-adic numbers, $a$ and $b$, where $a = \ldots4321_5$ and $b = \ldots3141_5$. The ellipses indicate that there are more $p$-adic digits to the left.

- Subtracting digit by digit while considering borrowing:
  $$
  \begin{align*}
  a_0 - b_0 &= 1 - 1 = 0 \text{ (no borrowing)} \\
  a_1 - b_1 &= 2 - 4 = -2 \text{ (borrow 1)} \\
  a_2 - b_2 &= 3 - 1 = 2 \text{ (no borrowing)} \\
  a_3 - b_3 &= 4 - 3 = 1 \text{ (no borrowing)} \\
  a_4 - b_4 &= 4 - 1 = 3 \text{ (no borrowing)} \\
  &\vdots
  \end{align*}
  $$

So, $a - b = \ldots3210_5$, which represents a $5$-adic number.

In summary, subtraction of $p$-adic numbers is carried out digit by digit, much like addition, with consideration of borrowing when necessary. These operations are fundamental when performing arithmetic within the $p$-adic number system and exhibit distinct behavior compared to arithmetic in the real numbers.

# Negativity in p-adic numbers

The concept of negativity in $p$-adic numbers is intriguing and differs from that in the real numbers. Here, we'll explore some theorems related to negativity in $p$-adic numbers, particularly in the context of the $p$-adic valuation.

**Theorem 1: Negativity of Infinite p-adic Expansions**:

In the $p$-adic number system, a $p$-adic number can have an infinite number of digits to the left of the radix point. However, when the expansion goes infinitely to the left, it implies that the number is negative.

*Proof*:

Let $a = \ldots a_2a_1a_0.a_{-1}a_{-2}a_{-3}\ldots$ be a $p$-adic number where the ellipses indicate an infinite number of digits to the left of the radix point. To show that this number is negative, we can consider its $p$-adic valuation, $|a|_p$.

Recall that $|a|_p$ is defined as the largest power of $p$ that divides $a$, considering all its digits. In this case, since we have an infinite number of digits to the left, $|a|_p$ will be infinite, implying that $a$ is negative in the $p$-adic system.

**Theorem 2: Negativity in the p-adic Norm**:

The $p$-adic norm of a nonzero $p$-adic number is always less than $1$. Therefore, in the $p$-adic metric, a nonzero number is considered "smaller" than any positive $p$-adic number, making it effectively negative.

*Proof*:

Let $a \in \mathbb{Q}_p$ be a nonzero $p$-adic number. The $p$-adic norm, denoted as $|a|_p$, is defined as the multiplicative inverse of the largest power of $p$ that divides $a$. Mathematically:
$$
|a|_p = p^{-v_p(a)}
$$
where $v_p(a)$ is the $p$-adic valuation of $a$. Since $v_p(a) > 0$ for any nonzero $p$-adic number, we have $|a|_p < 1$. Therefore, in the $p$-adic metric, a nonzero $p$-adic number is effectively "smaller" than any positive $p$-adic number, indicating its negativity.

**Theorem 3: Non-Positivity in the p-adic Metric**:

In the $p$-adic metric, the notion of non-positivity is more general than just negativity. A $p$-adic number is considered non-positive if its $p$-adic norm is less than or equal to $1$.

*Proof*:

Let $a \in \mathbb{Q}_p$ be a $p$-adic number. We know that $|a|_p$ is defined as $p^{-v_p(a)}$. Therefore, a $p$-adic number $a$ is non-positive if and only if $|a|_p \leq 1$. This includes both negative $p$-adic numbers (where $|a|_p > 1$) and numbers that are exactly $0$.

These theorems highlight the unique nature of negativity and non-positivity in $p$-adic numbers, which is quite distinct from the real number system. Understanding these concepts is essential for working with $p$-adic analysis and solving problems in number theory and related fields.

# Inverses in p-adic numbers

In the $p$-adic number system, finding the inverse of a $p$-adic number is a crucial operation, akin to finding reciprocals in the real number system. However, it's important to note that not all $p$-adic numbers have multiplicative inverses. The existence of inverses in $p$-adic numbers is closely related to the $p$-adic valuation and norms.

Let's explore the concept of inverses in the $p$-adic number system:

**Theorem 1: Existence of Inverses**:

In the $p$-adic number system, a $p$-adic number $a$ has a multiplicative inverse if and only if its $p$-adic norm $|a|_p$ is not equal to zero, i.e., $|a|_p \neq 0$.

*Proof*:

- If $|a|_p \neq 0$, it means that $a$ is not a multiple of any positive power of $p$, and there exists a $p$-adic number $b$ such that $|b|_p = 1/|a|_p$. This $b$ serves as the multiplicative inverse of $a$ in the $p$-adic number system, and we denote it as $a^{-1}$.

- Conversely, if $a$ has a multiplicative inverse $a^{-1}$ in the $p$-adic system, then $|a|_p \neq 0$, as the $p$-adic norm of a nonzero number is always a positive power of $p$. Therefore, the existence of inverses in the $p$-adic numbers is equivalent to the nonzero $p$-adic norm.

**Example of Finding Inverses in 3-adic Numbers**:

Let's find the inverse of a $3$-adic number, say $a = \ldots2101_3$. To check if an inverse exists, we need to compute the $3$-adic norm of $a$:
$$
|a|_3 = 3^{-\text{val}_3(a)} = 3^{-1} = \frac{1}{3}
$$

Since $|a|_3 \neq 0$, an inverse exists. To find it, we can compute $a^{-1}$ as follows:
$$
a^{-1} = \frac{1}{a} = \frac{1}{\ldots2101_3} = \ldots1222_3
$$

So, in this case, $a^{-1}$ is $\ldots1222_3$, which represents the multiplicative inverse of $a$ in the $3$-adic number system.

In summary, the existence of inverses in the $p$-adic number system is tied to the nonzero $p$-adic norm of a number. If the $p$-adic norm is nonzero, an inverse exists, and it can be found by computing the reciprocal. Understanding the existence and properties of inverses is essential for performing arithmetic operations and solving equations in the $p$-adic number system.

# **Squares in p-adic Numbers**:

In the $p$-adic number system, understanding the properties of squares, i.e., numbers of the form $a^2$, is essential for various mathematical operations and analysis. Squares in $p$-adic numbers exhibit unique characteristics compared to the real number system.

**Theorem 1: Existence of Square Roots**:

In the $p$-adic number system, a $p$-adic number $a$ has a square root if and only if $a$ is a square modulo $p$, i.e., there exists another $p$-adic number $b$ such that $b^2 \equiv a \pmod{p}$.

*Proof*:

- If $a$ is a square modulo $p$, then there exists an integer $k$ such that $a \equiv k^2 \pmod{p}$. We can find a $p$-adic number $b$ such that $b \equiv k \pmod{p}$, and it follows that $b^2 \equiv k^2 \equiv a \pmod{p}$.

- Conversely, if there exists a $p$-adic number $b$ such that $b^2 \equiv a \pmod{p}$, then we can write $a \equiv b^2 \pmod{p}$, indicating that $a$ is a square modulo $p$.

**Theorem 2: Solving Equations Involving Squares**:

Suppose we have an equation of the form $x^2 \equiv a \pmod{p}$, where $a$ is a $p$-adic number. If $a$ is a square modulo $p$, then this equation has exactly two solutions in the $p$-adic numbers.

*Proof*:

- If $a$ is a square modulo $p$, then by Theorem 1, there exists a $p$-adic number $b$ such that $b^2 \equiv a \pmod{p}$. The two solutions to the equation are $x \equiv \pm b \pmod{p}$.

**Example of Squares in 5-adic Numbers**:

Consider the $5$-adic number system. Let's find the square roots of $a = \ldots341_5$. To determine if square roots exist, we need to check whether $a$ is a square modulo $5$. We can do this by finding an integer $k$ such that $k^2 \equiv a \pmod{5}$:

- We observe that $k = 4$ satisfies $k^2 \equiv 4^2 \equiv 16 \equiv 1 \pmod{5}$.
- Therefore, $a$ is a square modulo $5$, and square roots exist.

To find the square roots, we have two solutions:
1. $x_1 \equiv 4 \pmod{5}$.
2. $x_2 \equiv -4 \equiv 1 \pmod{5}$.

So, in this case, $a$ has two square roots in the $5$-adic number system.

In summary, squares in $p$-adic numbers are numbers that have square roots in the $p$-adic number system. The existence and properties of square roots play a significant role in solving equations and understanding the structure of $p$-adic numbers.

# Squares in the 2-adic system
**Detecting if a 2-adic Number is a Square Depending on the Number of Digits**:

In the 2-adic number system, determining whether a 2-adic number is a square depends on the number of digits in its representation. Unlike the real number system, the properties of squares in the 2-adic system exhibit interesting patterns related to the number of trailing zeros in the binary representation of the number.

**Theorem 1: Square Detection Based on Trailing Zeros**:

Given a 2-adic number $a$ with binary representation $\ldots a_na_{n-1}\ldots a_2a_1a_0$, where $a_i$ are binary digits (0 or 1), we can detect if $a$ is a square in the 2-adic numbers based on the following rules:

1. If $a$ has an odd number of trailing zeros (i.e., $a_0, a_1, a_2, \ldots$ are all zeros, and $a_{2k}$ for some positive integer $k$ is the first nonzero digit), then $a$ is not a square in the 2-adic numbers.

2. If $a$ has an even number of trailing zeros (i.e., $a_0, a_1, a_2, \ldots$ are all zeros, and $a_{2k+1}$ for some positive integer $k$ is the first nonzero digit), then $a$ is a square in the 2-adic numbers.

*Proof*:

- In the 2-adic number system, the square of an integer $k$ has an even number of trailing zeros in its binary representation because $(2k)^2 = 4k^2$. Therefore, if a 2-adic number has an even number of trailing zeros, it is the square of an integer.

- Conversely, if a 2-adic number has an odd number of trailing zeros, it cannot be the square of an integer because the square of any integer in the 2-adic system has an even number of trailing zeros.

**Example**:

Let's consider a 2-adic number with the binary representation $\ldots1000_2$. This number has an odd number of trailing zeros, specifically one trailing zero. According to Theorem 1, such a number is not a square in the 2-adic numbers.

Now, consider another 2-adic number with the binary representation $\ldots1100_2$. This number has an even number of trailing zeros, specifically two trailing zeros. By Theorem 1, this number is a square in the 2-adic numbers.

In summary, detecting whether a 2-adic number is a square depends on the number of trailing zeros in its binary representation. An even number of trailing zeros indicates that the number is a square, while an odd number of trailing zeros indicates that it is not a square in the 2-adic number system. This unique property of squares in the 2-adic system adds an intriguing aspect to the study of 2-adic numbers.

# Square Detection in p-adics
**Hensel's Lemma and Detection of Square $p$-adic Numbers**:

Hensel's Lemma provides a powerful tool for lifting solutions from modulo $p^n$ to modulo $p^{n+1}$ when dealing with polynomial equations. In the context of $p$-adic numbers, it plays a crucial role in verifying whether a given integer is a square in the $p$-adic number system.

**Hensel's Lemma Overview**:

Hensel's Lemma states that if we have a solution to a polynomial congruence $f(x) \equiv 0 \mod{p^n}$ for some polynomial $f$, and if the derivative of $f$, denoted as $f'(x)$, is not congruent to $0$ modulo $p$, then we can lift this solution to modulo $p^{n+1}$. This means that we can find a unique solution modulo $p^{n+1}$.

**Detection of Square $p$-adic Numbers**:

To determine if a number is a square in the $p$-adic numbers, we need to check whether it is a square modulo $p^n$ for all $n$, starting with $n=1$. We can utilize Hensel's Lemma to formulate a theorem for detecting square $p$-adic numbers:

**Theorem (Detection of Square $p$-adic Numbers):**
Let $p$ be an odd prime, and let $a$ be an integer such that $a \not\equiv 0 \mod{p}$. Then, $a$ is a square in the $p$-adic numbers if and only if the following conditions hold:

1. $a$ is a square modulo $p$, i.e., there exists an integer $x_0$ such that $x_0^2 \equiv a \mod{p}$.
2. The polynomial $f(x) = x^2 - a$ satisfies Hensel's Lemma, meaning there exists an integer $x_0$ such that:
   - $x_0^2 \equiv a \mod{p}$.
   - $2x_0 \not\equiv 0 \mod{p}$.

If these conditions are met, then for each $n \geq 1$, there exists a unique $p$-adic integer $x_n$ such that:
1. $x_n^2 \equiv a \mod{p^n}$.
2. $x_{n+1} \equiv x_n \mod{p^n}$.

Furthermore, the sequence $\{x_n\}$ converges to a $p$-adic integer $x$ such that $x^2 = a$ in the $p$-adic integers.

**Proof**:
The proof of this theorem involves an induction argument on $n$, using Hensel's Lemma to lift solutions from $p^n$ to $p^{n+1}$ while ensuring convergence to the desired square root of $a$ in the $p$-adic integers.

This theorem provides a reliable method for detecting square $p$-adic numbers by leveraging the properties of squares modulo $p$ and the lifting capabilities of Hensel's Lemma.