<iframe width="941" height="480" src="https://www.youtube.com/embed/VRrP4US7idg?list=PL8yHsr3EFj53L8sMbzIhhXSAOpuZ1Fov8" title="Introduction to number theory lecture 5. Primes." frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
# Definition of Primes
A prime number is defined within the realm of integers. Formally, an integer $$ p > 1 $$ is said to be a prime number if its only positive divisors are 1 and itself. In other words, if the only solutions to the equation $$ p = ab $$, where $$ a $$ and $$ b $$ are integers, are when either $$ a = p $$ and $$ b = 1 $$, or $$ a = 1 $$ and $$ b = p $$.

This definition excludes 1 from being a prime number, as its only divisor is itself, and it doesn't satisfy the condition of having two distinct positive divisors. Additionally, negative integers and non-integer numbers are not considered when discussing prime numbers, as the concept is inherently tied to the set of positive integers greater than 1.

In a more abstract sense, prime numbers can be seen as the fundamental building blocks of the integers, since any integer greater than 1 can be uniquely factored into a product of prime numbers, a principle known as the Fundamental Theorem of Arithmetic.

Sometimes: [[1 was counted as a prime number]]

# Extension of the definitions of primes to negative numbers

Extending the concept of prime numbers to include negative integers requires a bit of nuance, primarily because the original definition of a prime number is intrinsically linked to the set of positive integers. However, in a broader algebraic context, particularly within the domain of ring theory, this extension is indeed possible and meaningful.

In ring theory, an element \( p \) in a ring \( R \) is called a prime element if it satisfies the following two conditions:

1. **Non-Unit and Non-Zero**: \( p \) is neither a unit (an element with a multiplicative inverse) nor zero.
2. **Prime Property**: Whenever \( p \) divides a product \( ab \), with \( a, b \in R \), then \( p \) must divide at least one of \( a \) or \( b \).

Applying this to the ring of integers \( \mathbb{Z} \), we can consider negative numbers. For instance, in this context, \(-3\) is a prime because:

- It is neither a unit nor zero.
- If \(-3\) divides a product \( ab \), then it must divide either \( a \) or \( b \).

In essence, the negative counterpart of a positive prime number (like \(-2\), \(-3\), \(-5\), etc.) also behaves as a prime in this extended sense. This broadens our perspective on divisibility and factors within the integers.

However, it's important to recognize that this extension is more abstract and is usually discussed within the realms of higher algebra and number theory. In elementary arithmetic and basic number theory, when we talk about prime numbers, we are typically referring to the positive primes as per the traditional definition.

# Checking for Primes

Certainly! Let's reformulate the prime-checking algorithms using rigorous mathematical notation and the requested format.

### Algorithm 1: Trial Division

1. **Input and Initial Check**:
   - Given an integer \( n \).
   - If \( n \leq 1 \), then 
     $$ \text{Output: "Not Prime"} $$

2. **Division Test**:
   - For each integer \( i \) from 2 to \( n-1 \):
     - If \( n \) is divisible by \( i \), i.e.,
       $$ n \mod i = 0 $$
     - Then,
       $$ \text{Output: "Not Prime"} $$

3. **Prime Confirmation**:
   - If no divisors are found, then 
     $$ \text{Output: "Prime"} $$

#### Complexity Analysis:
- Time Complexity: \( O(n) \), as it checks all integers from 2 to \( n-1 \).

### Algorithm 2: Optimized Trial Division

1. **Input and Preliminary Verification**:
   - Given an integer \( n \).
   - If \( n \leq 1 \), then 
     $$ \text{Output: "Not Prime"} $$

2. **Handling Even Numbers**:
   - If \( n > 2 \) and \( n \) is even, i.e.,
     $$ n \mod 2 = 0 $$
   - Then,
     $$ \text{Output: "Not Prime"} $$

3. **Optimized Division Test**:
   - Iterate \( i \) from 3 to \( \sqrt{n} \) with a step of 2, i.e., check only odd numbers.
   - If \( n \) is divisible by \( i \), i.e.,
     $$ n \mod i = 0 $$
   - Then,
     $$ \text{Output: "Not Prime"} $$

4. **Prime Determination**:
   - If no divisors are found, then 
     $$ \text{Output: "Prime"} $$

#### Complexity Analysis:
- Time Complexity: \( O(\sqrt{n}) \).
- This method is more efficient, particularly for large \( n \), reducing the number of checks drastically.

These formulations provide a clear and precise representation of the prime-checking algorithms, adhering to the conventions of mathematical rigor and notation.

# Fundamental Theorem of Arithmetic
The Fundamental Theorem of Arithmetic is a foundational principle in number theory, elegantly capturing the essence of prime numbers and their unique role in the composition of integers. Let us articulate this theorem with the clarity and precision it deserves:

### Statement of the Theorem:

The Fundamental Theorem of Arithmetic asserts that:

1. **Unique Prime Factorization**:
   - Every integer greater than 1 either is a prime number itself or can be uniquely represented as a product of prime numbers.
   - This representation is unique up to the order of the factors.

Mathematically, for any integer \( n > 1 \), there exists a unique set of prime numbers \( p_1, p_2, \ldots, p_k \) (not necessarily distinct) such that:
$$ n = p_1^{e_1} \cdot p_2^{e_2} \cdot \ldots \cdot p_k^{e_k} $$
where \( e_1, e_2, \ldots, e_k \) are positive integers, and the primes are ordered such that:
$$ p_1 < p_2 < \ldots < p_k $$

2. **Uniqueness**:
   - No two distinct integers greater than 1 have the same set of prime factors with the same exponents.
   - This means that the prime factorization of an integer is unique, apart from the order of the factors.

### Implications and Significance:

- **Foundation of Number Theory**: This theorem forms the cornerstone of number theory, influencing various areas such as cryptography, algebra, and prime number theory.
- **Divisibility and GCD**: The theorem provides a method to find the greatest common divisor (GCD) and the least common multiple (LCM) of two integers.
- **Proofs and Applications**: It is pivotal in proving other important theorems in mathematics and has practical applications in computer algorithms and cryptography.

### Proof Outline:

The proof of the Fundamental Theorem of Arithmetic generally involves two main parts:

1. **Existence**: Showing that every integer greater than 1 can be expressed as a product of prime numbers. This is often achieved by induction or by a direct construction of such a factorization.

2. **Uniqueness**: Demonstrating that this prime factorization is unique. This typically involves assuming two different prime factorizations for the same number and showing that they must be the same, often employing the properties of prime numbers and divisibility.

The Fundamental Theorem of Arithmetic elegantly encapsulates the intricate tapestry woven by prime numbers in the realm of integers, highlighting their indivisible and foundational nature in the structure of number theory.

The assertion that the product of an empty set of numbers is equal to 1 is a concept rooted in the fundamental principles of mathematics, particularly in the context of multiplication and its identity element. This concept is not about the product of "empty sets" in the set-theoretic sense, but rather the product of a set of numbers that contains no elements. Let's delve into the reasoning:

# The Concept of an Empty Product:

1. **Definition**:
   - An empty product refers to the product of zero numbers. It's like asking, "What do we get when we multiply together no numbers at all?"

2. **Multiplicative Identity**:
   - In mathematics, the multiplicative identity is the number 1, since multiplying any number by 1 leaves it unchanged. Symbolically,
     $$ a \times 1 = a \quad \text{for any number } a $$

3. **Consistency with Multiplication**:
   - To maintain consistency in the properties of multiplication, particularly the identity property, we define the product of no numbers (an empty product) as the multiplicative identity, which is 1.

4. **Analogy with Summation**:
   - This is analogous to the concept in addition where the sum of an empty set of numbers is defined as 0, the additive identity. Just as adding zero numbers leaves us with 0, multiplying zero numbers leaves us with 1.

5. **Convenience in Mathematical Expressions**:
   - Defining the empty product as 1 simplifies many mathematical expressions and formulas, especially in algebra, calculus, and number theory. It allows for consistent and elegant handling of expressions that may involve variable numbers of terms.

6. **Example in Factorials**:
   - Consider the factorial of 0, denoted \( 0! \). Factorials are defined as the product of all positive integers up to that number. Since there are no positive integers up to 0, \( 0! \) is an empty product, and thus it is defined to be 1. This definition is crucial for the consistency of many mathematical formulas involving factorials.

### Conclusion:

The product of an empty set of numbers being equal to 1 is not an empirical observation but a definitional necessity. It ensures consistency and elegance in mathematical operations and expressions, aligning with the fundamental properties of multiplication and its identity element. This definition is universally accepted in mathematics for its utility and coherence with established mathematical principles.

# The Proof
**Theorem**: Every integer $n > 1$ is either prime or can be written as a product of primes. Furthermore, this representation is unique, up to the order of the factors.

**Proof**:

1. **Existence of Prime Factorization**:
   - If $n$ is prime, there is nothing to prove.
   - If $n$ is not prime, it can be written as a product $n = ab$, where $a, b < n$. By the principle of mathematical induction, both $a$ and $b$ are either prime or can be factored into primes. Thus, $n$ can be factored into primes.

2. **Uniqueness of Prime Factorization**:
   - Assume for contradiction that $n$ has two distinct prime factorizations: $n = p_1p_2...p_r = q_1q_2...q_s$, where $p_i$ and $q_j$ are prime numbers.
   - Without loss of generality, assume $p_1 \leq p_2 \leq ... \leq p_r$ and $q_1 \leq q_2 \leq ... \leq q_s$.
   - By the fundamental property of prime numbers, $p_1$ must divide one of the $q_j$'s. Since all $q_j$'s are prime, this implies $p_1 = q_j$ for some $j$.
   - We can cancel this common factor from both sides of the equation.
   - Repeating this process, we conclude that $r = s$ and, after reordering, $p_i = q_i$ for all $i$. This contradicts the assumption of two distinct factorizations.

Therefore, every integer greater than 1 can be uniquely factored into primes, up to the order of the factors. This completes the proof of the Fundamental Theorem of Arithmetic.

Euclid's Result Existed, he wasn't able to write it well because of [[Greek Mathematical Notation]]

# Fundamental Theorem Of Arithmetic in  the context of Polynomials
The Fundamental Theorem of Arithmetic, a cornerstone in number theory, states that every integer greater than 1 can be uniquely factorized into prime numbers, up to the order of the factors. This profound concept finds a remarkable analogue in the realm of polynomials.

In the context of polynomials, the theorem is reimagined as follows: Every non-constant polynomial $f(x)$ with coefficients in a field (like the real or complex numbers) can be expressed as a product of irreducible polynomials, and this factorization is unique up to the order of the factors and multiplicative constants.

In formal mathematical terms, if $f(x)$ is a non-constant polynomial, then we can express $f(x)$ as:

$$
f(x) = c \cdot p_1(x)^{n_1} \cdot p_2(x)^{n_2} \cdot \ldots \cdot p_k(x)^{n_k}
$$

Here:
- $c$ is a non-zero constant.
- Each $p_i(x)$ is an irreducible polynomial, meaning it cannot be factored into polynomials of lower degree with leading coefficients of 1.
- The exponents $n_i$ are positive integers.
- This factorization is unique up to the order of the polynomials $p_i(x)$ and the constant $c$.

This theorem assures us that the factorization of polynomials into irreducible is not just possible, but also unique, mirroring the way prime factorization works for integers. The elegance of this theorem lies in its universal applicability across various fields, providing a fundamental tool in understanding the structure of polynomials.

# Note: 
The uniqueness is the nontrivial part of the proof

# Algebraic Number Fields and unique factorization
[[Algebraic Number Fields]] are extended systems of the real numbers. and some of them can be used to study the unique factorization in primes, where we are using primes ion a more generalized definition. [[9 Daily Scribble 14-11-2023#^96d4a5]]

# Likeliness of obtaining a prime using Euclid's method of generating primes

Euclid's method for generating primes, famously known as Euclid's proof of the infinitude of primes, inherently produces a number that is either prime or has prime factors larger than any in a given finite list of primes. To rigorously examine the likelihood of obtaining a prime through this method, we delve into the method itself and its probabilistic implications.

### Euclid's Method Overview:

1. **Starting Point**:
   - Begin with a finite list of primes: $p_1, p_2, \ldots, p_n$.

2. **Construction**:
   - Form a new number $P$ by multiplying all primes in the list and adding 1: $$P = p_1 \cdot p_2 \cdot \ldots \cdot p_n + 1$$

3. **Outcome**:
   - $P$ is not divisible by any of the primes in the list ($p_1, p_2, \ldots, p_n$).
   - Therefore, $P$ is either prime itself or divisible by primes not in the initial list.

### Analyzing the Likelihood of $P$ Being Prime:

To assess the probability of $P$ being prime, consider the following:

- **Size of $P$**: 
  - $P$ grows rapidly as the list of primes increases. For a large $n$, $P$ becomes significantly large.

- **Density of Primes (Prime Number Theorem)**:
  - The Prime Number Theorem provides insight into the density of primes. It states that the number of primes less than a given number $x$ is approximately $\frac{x}{\ln(x)}$.
  - As numbers grow larger, the density of primes decreases.

- **Heuristic Analysis**:
  - For a large $n$, the number $P$ is much larger than any prime in the initial list. The probability of a random number of this magnitude being prime is roughly $\frac{1}{\ln(P)}$.
  - Given the construction of $P$, its primality is not random, but this gives a rough estimation.

### Conclusion:

While Euclid's method guarantees the production of a number with new prime factors, the likelihood of $P$ being prime decreases as the list of initial primes grows. This decrease aligns with the overall lower density of primes among larger numbers. Hence, while Euclid's method is a brilliant conceptual proof for the infinitude of primes, it becomes less efficient for generating large primes compared to other methods like probabilistic tests or sieve methods. The elegance of Euclid's approach lies in its theoretical implications rather than practical utility in prime generation.

# Probability that a randomly chosen integer is divisible by a given integer a 

employing the formalism of mathematical notation and probability theory.

### Divisibility and Distribution:

1. **Divisibility Criterion**:
   - An integer \( N \) is divisible by \( a \) if and only if there exists an integer \( k \) such that 
     $$ N = ak. $$

2. **Uniform Distribution of Multiples**:
   - The multiples of \( a \) are uniformly distributed among the integers. They appear at intervals of \( a \), i.e., 
     $$ a, 2a, 3a, \ldots. $$

### Probability Calculation:

- **Assumption of Uniformity**:
  - Assuming a uniform distribution of integers within a given range, each integer is equally likely to be selected.

- **Analysis of Intervals**:
  - In any set of \( a \) consecutive integers, there is exactly one multiple of \( a \). For example, in the set 
     $$ \{1, 2, \ldots, a\}, $$
     the number \( a \) is the only multiple of \( a \).

- **Derivation of Probability**:
  - Therefore, the probability \( P \) that a randomly chosen integer is divisible by \( a \) is 
     $$ P = \frac{1}{a}. $$

### Conclusion:

The probability of a random integer being divisible by another specified integer \( a \) is mathematically expressed as 
$$ P = \frac{1}{a}. $$
This formula is based on the premise of uniformly distributed integers and the regular occurrence of multiples of \( a \) in the integer sequence.

# Infinitely many primes ending in $1$ 
To prove that there are infinitely many primes ending in $1$ (in base $10$), we indeed turn to Dirichlet's theorem on arithmetic progressions. This theorem, a jewel of analytic number theory, states that in any arithmetic progression of the form $a, a+d, a+2d, a+3d, \ldots$, where $a$ and $d$ are coprime integers (i.e., their greatest common divisor is $1$), there are infinitely many primes.

In our case, we are interested in the arithmetic progression $1, 1+10, 1+20, 1+30, \ldots$, or more compactly, the sequence $1, 11, 21, 31, \ldots$. This is the arithmetic progression of the form $a + nd$ where $a = 1$ and $d = 10$. Since $a$ and $d$ are coprime (their greatest common divisor is $1$), Dirichlet's theorem applies.

Let us delve into the heart of Dirichlet's proof, which employs techniques from analytic number theory:

1. **L-Series and Non-Vanishing Property**: Dirichlet constructs L-series for each character $\chi$ modulo $d$. These are akin to the Riemann Zeta function but twisted by the character. He showed that these L-series do not vanish at $s = 1$.

2. **Dirichlet's Test for Convergence**: Dirichlet used what is now known as Dirichlet's test for convergence to establish the non-vanishing of the L-series at $s = 1$.

3. **Linking to Prime Numbers**: The critical leap is linking the non-vanishing of these L-series at $s = 1$ to the distribution of prime numbers in arithmetic progressions. He showed that if the L-series does not vanish, then there are infinitely many primes in the arithmetic progression corresponding to the character.

4. **Analytic Techniques**: The proof involves a deep dive into complex analysis, particularly the study of analytic functions, and a profound understanding of Euler products, which relate the distribution of prime numbers to the properties of certain meromorphic functions.

In essence, Dirichlet's proof is a masterpiece that connects the distribution of prime numbers with the properties of certain complex functions. For the specific case of primes ending in $1$, it asserts that within the sequence $1, 11, 21, 31, \ldots$, there are infinitely many prime numbers. This is because the underlying L-series for the character associated with this progression does not vanish at $s = 1$, implying the infinite presence of primes in this sequence.

# Essence of Dirichlet's Proof
To provide a full and rigorous proof of Dirichlet's theorem, specifically for the case of primes ending in $1$, we need to delve into several sophisticated areas of mathematics, including number theory, complex analysis, and the theory of L-series. Given the complexity and length of such a proof, I'll provide a high-level overview, structured in the formal mathematical format:

### Theorem (Dirichlet on Primes in Arithmetic Progressions):
For any two coprime integers $a$ and $d$, the arithmetic progression $a, a+d, a+2d, \ldots$ contains infinitely many prime numbers.

### Specific Case:
For the arithmetic progression $1, 11, 21, 31, \ldots$ (where $a = 1$ and $d = 10$), there are infinitely many primes.

### Proof:

#### Step 1: Introduction of Dirichlet Characters
- Define Dirichlet characters $\chi$ modulo $d$. These are completely multiplicative functions from the integers to the complex numbers, periodic with period $d$, and trivial on integers coprime to $d$.
- For our case, consider characters modulo $10$.

#### Step 2: Construction of Dirichlet L-Series
- For each character $\chi$, construct the Dirichlet L-series:
  $$ L(s, \chi) = \sum_{n=1}^{\infty} \frac{\chi(n)}{n^s} $$
  where $s$ is a complex number with $\Re(s) > 1$.

#### Step 3: Analytic Continuation and Non-Vanishing of L-Series
- Extend the definition of $L(s, \chi)$ to all $s$ in the complex plane, except possibly a simple pole at $s=1$ when $\chi$ is the principal character.
- Prove that $L(1, \chi) \neq 0$ for non-principal characters $\chi$.
- [[Non Vanishing in the context of L-Series]]

#### Step 4: Establishing the Link with Prime Numbers
- Show that the non-vanishing of $L(1, \chi)$ implies the existence of infinitely many primes $p$ such that $p \equiv a \pmod{d}$.
- This involves understanding the Euler product representation of $L(s, \chi)$ and its relation to primes:
  $$ L(s, \chi) = \prod_{p \text{ prime}} \left(1 - \frac{\chi(p)}{p^s}\right)^{-1} $$

#### Step 5: Application to the Case $a=1, d=10$
- Apply the above theory specifically to characters modulo $10$.
- Demonstrate that the non-vanishing of the appropriate L-series at $s = 1$ ensures the existence of infinitely many primes in the sequence $1, 11, 21, 31, \ldots$.

### Conclusion:
By Dirichlet's theorem, and specifically through the analysis of L-series and their properties, we conclude that there are infinitely many primes in the arithmetic progression starting at $1$ and increasing in steps of $10$. This includes primes that end in $1$ in base $10$.

---

This overview touches only the surface of a deeply complex proof that integrates multiple areas of advanced mathematics. Each step contains significant mathematical theory and requires a detailed understanding of concepts like multiplicative functions, complex analysis, and the properties of prime numbers.

# Gaps between Primes
The question of prime gaps, or the intervals between successive prime numbers, treads into a fascinating area of number theory. The predictability and bounding of these gaps have been subjects of intense research and have led to several important results.

### Prime Gaps: Definitions and Basic Observations

- **Prime Gap:** Given two successive prime numbers $p$ and $q$ where $q > p$, the prime gap is $g = q - p$. For example, the gap between the primes 2 and 3 is 1, and between 3 and 5 is 2.

### Unpredictability of Prime Gaps

Prime gaps are not predictable in a straightforward manner. The distribution of primes, governed by the Prime Number Theorem, suggests that primes become less frequent as numbers grow larger. However, the exact location of primes and thus the specific gaps between them cannot be predicted with a simple formula.

### Bounding Prime Gaps

#### Bertrand's Postulate

A classical result relevant here is Bertrand's Postulate (proved by Chebyshev in 1852), which states that for every $n > 1$, there exists at least one prime $p$ such that $n < p < 2n$. This effectively places a bound on prime gaps for sufficiently large numbers, asserting that a prime gap is at most $n$ for primes greater than $n$.

#### General Bounds

In a general sense, the gap between successive primes grows, but it's irregular. Notably, the Prime Number Theorem implies that the average gap between primes around a large number $N$ is roughly $\log(N)$, where $\log$ denotes the natural logarithm.

### Proving Bounds on Prime Gaps

While proving specific bounds like Bertrand's Postulate involves intricate mathematical arguments, demonstrating that prime gaps increase on average with $\log(N)$ can be derived from the Prime Number Theorem.

#### Prime Number Theorem

The Prime Number Theorem states that the number of primes less than a given number $N$ approximates to $\frac{N}{\log(N)}$. This suggests that the density of primes near $N$ is about $\frac{1}{\log(N)}$, leading to the average gap of $\log(N)$.

### More Recent Advances

In recent years, there have been significant advancements in understanding prime gaps. For instance, Yitang Zhang made a breakthrough in 2013 by proving that there are infinitely many pairs of primes with gaps less than 70 million. This was a monumental step in the study of prime gaps, although it doesn't directly answer the question of predictability or provide a tight bound for all prime gaps.

In summary, while prime gaps are not predictable in a straightforward way, there are bounds on how large these gaps can be. These bounds become more nuanced and challenging to establish for larger primes, and the field continues to evolve with ongoing research.

# Unboundedness of Prime Gaps
Indeed, you're correct in stating that there are no upper bounds on the gaps between consecutive primes. This assertion is grounded in two fundamental constructions in number theory: the factorial-based construction and Euler's product formula for the Riemann Zeta function.

### 1. Factorial-Based Construction

The simplest proof to demonstrate that there is no upper bound on prime gaps involves factorials. Consider the sequence of numbers $n! + 2, n! + 3, \ldots, n! + n$, where $n!$ denotes the factorial of $n$ (the product of all positive integers up to $n$). 

Each number in this sequence is not prime:

- $n! + 2$ is divisible by 2,
- $n! + 3$ is divisible by 3,
- ...
- $n! + n$ is divisible by $n$.

This sequence demonstrates that for any natural number $n$, there exists a run of $n - 1$ consecutive composite (non-prime) numbers. Thus, for any arbitrarily large $n$, we can find a gap between successive primes that is at least as large as $n$. This establishes that there is no universal upper bound on the gaps between primes.

### 2. Euler's Product Formula and the Riemann Zeta Function

Euler's product formula for the Riemann Zeta function also hints at the unbounded nature of prime gaps. The formula states:

$$
\zeta(s) = \prod_{p \text{ prime}} \left(1 - \frac{1}{p^s}\right)^{-1}
$$

where $\zeta(s)$ is the Riemann Zeta function.

While this formula doesn't directly prove the unbounded nature of prime gaps, it shows the deep interconnection between primes and non-trivial mathematical constructs. The distribution of zeros of the Riemann Zeta function is believed to be closely related to the distribution of primes. However, this relationship is highly complex and not linear, suggesting that the appearance of primes (and thus the gaps between them) cannot be bounded in a straightforward manner.

### Conclusion

The factorial argument provides a direct and intuitive proof that there are no upper bounds on the gaps between consecutive primes. This understanding is crucial in the study of prime numbers and leads to fascinating questions in number theory, many of which remain active areas of research.

# Zhang's Proof of Prime Gaps
Zhang Yitang's breakthrough in prime number theory, specifically regarding the prime gap, represents a significant advancement in our understanding of the distribution of prime numbers. Before delving into the proof, let's establish some context and key concepts.

### Background

Prime numbers are integers greater than 1 that have no positive divisors other than 1 and themselves. The distribution of prime numbers has been a central topic in number theory for centuries. A prime gap is the difference between two successive prime numbers. For a long time, it was conjectured that there are infinitely many pairs of primes that differ by a fixed number $n$, but proving this remained elusive.

### Zhang's Breakthrough

In 2013, Zhang announced a major result: he proved that there exist infinitely many pairs of primes that differ by less than 70,000,000. This was the first time a finite bound had been established for the gap between consecutive primes, under the assumption that they are infinitely many.

### Outline of the Proof

Zhang's proof is complex and involves deep methods from analytic number theory. Here's a simplified overview:

1. **Sieve Theory**: Zhang utilized a branch of number theory known as sieve theory, which is used to count or estimate the number of primes within a certain range. He used a modified version of the Goldston-Pintz-Yıldırım (GPY) sieve to find bounds on prime gaps.

2. **Bounded Gaps Between Primes**: He showed that there exists some integer $k$, such that for infinitely many primes $p$, there's another prime between $p$ and $p + k$. The original value of $k$ he proved was 70,000,000.

3. **Careful Analysis and Optimization**: Zhang's proof involved careful and delicate analysis of the distribution of primes. He optimized parameters in the GPY method to get the bound down to 70,000,000, a task that required intricate calculations and estimations.

4. **Use of the Bombieri-Vinogradov Theorem**: This theorem is a central result in analytic number theory. It states that the primes, on average, are evenly distributed amongst the different residue classes, modulo any integer. Zhang used this to effectively control the distribution of primes in arithmetic progressions.

# More info on prime gaps
In 1938, Robert Alexander Rankin, a distinguished Scottish mathematician, made significant contributions to the study of prime gaps, which are relevant to your reference about the conjecture involving $ \log(n)^2 $.

### Rankin's Work on Prime Gaps

1. **Rankin's Theorem**: Rankin's most notable work in this area is what is now known as Rankin's Theorem. This theorem provides an upper bound on the size of gaps between consecutive prime numbers. Specifically, Rankin established a formula that gave an upper bound for the prime gap following a prime number $p$.

2. **Use of $\log$ Functions**: Rankin's formula involved iterated logarithm functions. To be more precise, he showed that there exist prime gaps larger than
   $$
   c \log p \log\log p \log\log\log\log p / (\log\log\log p)^2
   $$
   for any constant $c$ and infinitely many primes $p$.

3. **Significance**: This result was significant because it was the first time that an upper bound of this nature had been proven. It improved upon earlier results and opened the door to more detailed investigations into the distribution of primes.

4. **Relation to Prime Gap Conjectures**: Rankin's work is often discussed in the context of Cramér's conjecture and the general study of prime gaps. While it does not directly relate to the specific conjecture that the gap between primes is sometimes equal to $\log(n)^2$, it contributes to the broader understanding of how large prime gaps can be.

### Contemporary Perspective

- **Continuing Research**: Rankin's theorem is still a topic of interest in modern number theory. Mathematicians continue to explore its implications and seek to refine the bounds on prime gaps.
- **Contextualizing with Other Conjectures**: In the landscape of prime number theory, Rankin's theorem complements other conjectures and results, offering a piece of the larger puzzle of understanding the distribution and gaps of prime numbers.

Rankin's work exemplifies the depth and intricacy of mathematical research into prime numbers, illustrating how mathematicians build upon each other's work to gradually uncover the mysteries of number theory.
