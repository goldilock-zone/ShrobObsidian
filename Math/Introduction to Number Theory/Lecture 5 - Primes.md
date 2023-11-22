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

