# Properties of Congruences
Congruences in number theory are a fundamental concept, with several important properties that provide a foundation for various branches of mathematics, including cryptography, modular arithmetic, and algebraic number theory. Here are key properties of congruences:

1. **Reflexivity:** For any integer $a$ and a positive integer $n$, $a \equiv a \pmod{n}$. This means any number is congruent to itself modulo $n$.

2. **Symmetry:** If $a \equiv b \pmod{n}$, then $b \equiv a \pmod{n}$. Congruence is a symmetric relation; if $a$ is congruent to $b$, then $b$ is congruent to $a$.

3. **Transitivity:** If $a \equiv b \pmod{n}$ and $b \equiv c \pmod{n}$, then $a \equiv c \pmod{n}$. This property allows us to infer the congruence of two numbers through a third.

4. **Compatibility with Addition:** If $a \equiv b \pmod{n}$ and $c \equiv d \pmod{n}$, then $a + c \equiv b + d \pmod{n}$. Congruences respect addition, meaning the sum of congruent numbers is also congruent.

5. **Compatibility with Multiplication:** If $a \equiv b \pmod{n}$ and $c \equiv d \pmod{n}$, then $a \cdot c \equiv b \cdot d \pmod{n}$. Similar to addition, congruence is preserved under multiplication.

6. **Compatibility with Powers:** If $a \equiv b \pmod{n}$, then $a^k \equiv b^k \pmod{n}$ for any non-negative integer $k$. This extends the congruence property to powers of congruent numbers.

7. **Cancellation Law:** If $a \cdot c \equiv b \cdot c \pmod{n}$ and $c$ is coprime to $n$, then $a \equiv b \pmod{n}$. This property allows 'cancelling out' a factor if it is coprime to the modulus.

These properties make congruences a powerful tool in number theory, enabling elegant solutions to complex problems and forming the backbone of many advanced mathematical concepts.

## Power laws
The power laws of congruences in number theory are particularly important for understanding how exponents interact with modular arithmetic. These laws extend the basic properties of congruences to powers of integers. Here are the key power laws:

1. **Basic Power Law:** If $a \equiv b \pmod{n}$, then $a^k \equiv b^k \pmod{n}$ for any positive integer $k$. This means that if two numbers are congruent modulo $n$, their powers (raised to the same exponent) are also congruent modulo $n$. 

2. **Power of a Sum:** For any integers $a$ and $b$, and a positive integer $n$, $(a + b)^n \equiv a^n + b^n \pmod{n}$, if $n$ is a prime number. This is a consequence of the Binomial Theorem and Fermat's Little Theorem. 

3. **Fermat's Little Theorem:** If $p$ is a prime number and $a$ is an integer not divisible by $p$, then $a^{p-1} \equiv 1 \pmod{p}$. This theorem is very useful in number theory and cryptography.

4. **Euler's Theorem:** If $a$ and $n$ are coprime positive integers, then $a^{\phi(n)} \equiv 1 \pmod{n}$, where $\phi(n)$ is Euler's totient function. This theorem generalizes Fermat's Little Theorem and is pivotal in RSA encryption.

5. **Modular Exponentiation:** For any integers $a$, $b$, and $n$ with $n > 0$, if $b$ can be expressed as $b = b_1 + b_2 + \ldots + b_k$ in base $2$, then $a^b \equiv (a^{b_1} \cdot a^{b_2} \cdot \ldots \cdot a^{b_k}) \pmod{n}$. This method is efficient for computing large powers modulo $n$.

6. **Carmichael's Function:** Similar to Euler's theorem, if $a$ and $n$ are coprime, then $a^{\lambda(n)} \equiv 1 \pmod{n}$, where $\lambda(n)$ is the Carmichael function. This function provides the smallest such exponent in many cases.

These power laws are extensively used in algorithmic number theory, particularly in cryptographic algorithms, where operations on large powers modulo a number are common.

# Residue (Equivalence) Classes as Rings
The concept of residue classes forming a ring is rooted in modular arithmetic. To prove that residue classes form a ring, we need to demonstrate that they satisfy the ring axioms under addition and multiplication modulo $n$.

Let's consider the set of residue classes modulo $n$, denoted as $\mathbb{Z}_n$. This set is $\{0, 1, 2, \ldots, n-1\}$.

**1. Closure under Addition and Multiplication:**  
For any two elements $a, b \in \mathbb{Z}_n$, the sum $a + b$ and the product $a \cdot b$ are also in $\mathbb{Z}_n$. This is because if you add or multiply two numbers and then take the remainder when dividing by $n$, the result is still a number between $0$ and $n-1$.

**2. Associativity of Addition and Multiplication:**  
For all $a, b, c \in \mathbb{Z}_n$, the following holds:
$$ (a + b) + c = a + (b + c) \quad \text{and} \quad (a \cdot b) \cdot c = a \cdot (b \cdot c) $$
This is true because addition and multiplication of integers are associative, and this property is preserved modulo $n$.

**3. Additive and Multiplicative Identity:**  
The additive identity in $\mathbb{Z}_n$ is $0$ since for any $a \in \mathbb{Z}_n$, $a + 0 = a$. The multiplicative identity is $1$ because for any $a \in \mathbb{Z}_n$, $a \cdot 1 = a$.

**4. Additive Inverses:**  
For every $a \in \mathbb{Z}_n$, there exists an element $b \in \mathbb{Z}_n$ such that $a + b = 0$. The element $b$ is $n - a$.

**5. Commutativity of Addition and Multiplication:**  
For all $a, b \in \mathbb{Z}_n$, we have $a + b = b + a$ and $a \cdot b = b \cdot a$. This follows from the commutativity of addition and multiplication in $\mathbb{Z}$.

**6. Distributive Property:**  
For all $a, b, c \in \mathbb{Z}_n$, $a \cdot (b + c) = a \cdot b + a \cdot c$. This is a property inherited from the integers.

Since the set of residue classes modulo $n$, $\mathbb{Z}_n$, satisfies these axioms, it forms a ring. This ring is known as the ring of integers modulo $n$.

# Test for divisibility by 9 
To test whether a number is divisible by 9, you can use the divisibility rule for 9, which states that a number is divisible by 9 if the sum of its digits is also divisible by 9. Here's how you can do it step by step:

1. Take the number you want to test for divisibility by 9.

2. Find the sum of its digits.

3. If the sum of the digits is divisible by 9, then the original number is also divisible by 9.

For example, let's say you want to test if 729 is divisible by 9:

1. The number is 729.

2. Sum of its digits: 7 + 2 + 9 = 18.

3. Since 18 is divisible by 9, the original number 729 is also divisible by 9.

So, 729 is divisible by 9. You can use this method to test the divisibility of other numbers by 9 as well.

# Test for divisiblity of 11
To test whether a number is divisible by 11, you can use the divisibility rule for 11. The rule states that a number is divisible by 11 if the difference between the sum of its alternating digits (starting from the right) is either 0 or a multiple of 11.

Here's how you can use modulo in this context to test divisibility by 11:

1. Take the number you want to test for divisibility by 11.

2. Starting from the rightmost digit (the units digit), subtract the sum of the alternating digits.

3. If the result is either 0 or a multiple of 11, then the original number is divisible by 11.

Let's use an example to illustrate this:

Suppose you want to test if 352 is divisible by 11:

1. The number is 352.

2. Starting from the right, sum the alternating digits: 2 - 5 + 3 = 0.

3. Since the result is 0, which is a multiple of 11, the original number 352 is divisible by 11.

You can also use the modulo operator (%) to test divisibility by 11. If a number is divisible by 11, then it will have a remainder of 0 when divided by 11. So, you can check if the number modulo 11 is equal to 0. In code, it would look like this:

```python
number = 352
if number % 11 == 0:
    print("352 is divisible by 11")
else:
    print("352 is not divisible by 11")
```

This code will output: "352 is divisible by 11" because the remainder when dividing 352 by 11 is 0.

# Lagrange's Theorem about the sum of four squares
Lagrange's Four-Square Theorem is a beautiful blend of number theory and algebra. The theorem states that every natural number can be represented as the sum of four integer squares. In formal terms, for every natural number $n$, there exist integers $a$, $b$, $c$, and $d$ such that:

$$ n = a^2 + b^2 + c^2 + d^2 $$

This theorem, proved by Joseph-Louis Lagrange in 1770, expanded upon earlier work by Diophantus and Fermat. It's a significant result because it provides a universal rule applicable to all natural numbers, emphasizing the elegance and depth of number theory.

### The Essence of the Proof

Lagrange's proof is complex, involving several steps:

1. **Reduction to Prime Numbers:** First, it's shown that it suffices to prove the theorem for prime numbers. This is because if every prime can be expressed as the sum of four squares, then by multiplying out these sums (using the distributive property of multiplication), we can express any product of primes — and thus any integer — as a sum of four squares.

2. **Properties of Squares Mod 4:** A key observation is that any square number is congruent to either 0 or 1 modulo 4. This property is essential in handling the cases of different prime numbers.

3. **Case Analysis for Primes:** The proof then involves a case-by-case analysis for different types of prime numbers, particularly those of the form $4n + 1$ and $4n + 3$. The most challenging part is proving that primes of the form $4n + 1$ can be expressed as the sum of two squares, which involves sophisticated number theoretic arguments.

4. **Constructive Approach:** For primes of the form $4n + 3$, it's shown that they can be expressed as a sum of four squares, often involving more intricate constructions.

### Visualizing the Theorem

To better understand the theorem, let's visualize it for a specific number. For instance, the number 30 can be expressed as a sum of four squares in multiple ways. One such representation is:

$$ 30 = 1^2 + 1^2 + 3^2 + 5^2 $$

# Sum of three cubes
The question of representing any given number as the sum of three cubes is a fascinating and complex topic in number theory. Formally, the question asks if for every integer $n$, there exist integers $x$, $y$, and $z$ such that:

$$ n = x^3 + y^3 + z^3 $$

This problem, unlike Lagrange's Four-Square Theorem, does not have a universal solution applicable to all integers. In fact, it's an open problem in mathematics, and extensive computational efforts have been undertaken to find solutions for specific numbers.

### Known Results

- **Trivial Solutions:** For certain numbers, like those of the form $9k \pm 4$, $9k \pm 1$ (where $k$ is an integer), it's known that they can't be expressed as the sum of three cubes. This is due to congruence properties of cubic residues modulo 9.

- **Specific Cases:** For many integers, specific solutions have been found, often through computational methods. For example, the number 33 was famously solved in 2019: $33 = 8866128975287528^3 + (-8778405442862239)^3 + (-2736111468807040)^3$.

- **No General Formula:** Unlike the Four-Square Theorem, there is no general formula or method to determine whether a given number can be expressed as a sum of three cubes, or to find such a representation if it exists.

### Computational Efforts

The quest to find representations of numbers as sums of three cubes has seen significant computational efforts, particularly with the advent of powerful computers. These efforts often involve searching through large sets of integers to find potential solutions, a process that can be computationally intensive.

### Current Status

As of my last update, the problem remains unsolved for many integers, and it is an active area of research in number theory. It's a captivating example of how simple-looking problems can lead to deep mathematical inquiries and challenges.

If you have a specific number in mind, I can attempt to find its representation as a sum of three cubes, if it's known. Keep in mind that for many numbers, this representation might not yet be discovered.

# Fermat's Little Theorem
Fermat's Little Theorem is a fundamental result in number theory, particularly in the field of modular arithmetic. It states that if $p$ is a prime number, then for any integer $a$ not divisible by $p$, the number $a^{p-1}$ is congruent to 1 modulo $p$. In mathematical terms:

$$ a^{p-1} \equiv 1 \ (\text{mod} \ p) $$

This theorem is incredibly useful in various areas of mathematics, including cryptography and primality testing.

### Proof of Fermat's Little Theorem

There are several ways to prove Fermat's Little Theorem. One elegant proof uses the concept of combinatorics:

1. **Consider the Set of Products:** Take the set $S = \{a, 2a, 3a, \ldots, (p-1)a\}$ where $a$ is an integer and $p$ is a prime not dividing $a$.

2. **Modulo $p$ Uniqueness:** None of these products are congruent modulo $p$. Suppose $ia \equiv ja \ (\text{mod} \ p)$ for some $i, j \in \{1, 2, \ldots, p-1\}$ and $i \neq j$. Then $p$ would divide $(i-j)a$, which is impossible since $p$ doesn't divide $a$ and $|i-j| < p$.

3. **Multiply the Elements of $S$:** Consider the product of all elements in $S$: $P = a \cdot 2a \cdot 3a \cdot \ldots \cdot (p-1)a = a^{p-1} \cdot (p-1)!$.

4. **Modulo $p$ Comparison:** Each element of $S$ is congruent modulo $p$ to a unique element of the set $\{1, 2, 3, \ldots, p-1\}$. Therefore, $P \equiv (p-1)! \ (\text{mod} \ p)$.

5. **Conclusion:** Since $P = a^{p-1} \cdot (p-1)!$, we have $a^{p-1} \cdot (p-1)! \equiv (p-1)! \ (\text{mod} \ p)$. After dividing both sides by $(p-1)!$, we obtain $a^{p-1} \equiv 1 \ (\text{mod} \ p)$.

This proof elegantly combines elements of combinatorics and modular arithmetic, reflecting the profound interconnectedness of mathematical concepts. Fermat's Little Theorem is a cornerstone in the study of numbers and has significant implications in fields such as cryptography, where it underpins the RSA algorithm and other cryptographic systems. 

# Example of a divisibility problem

Consider the sum:
$$ S = \frac{1}{5}n^5 + \frac{1}{3}n^3 + \frac{7}{15}n $$

In our quest to probe the divisibility of $15S$ by 3 and 5, we first magnify $S$ by 15, thereby liberating it from the clutches of fractional coefficients:
$$ 15S = 3n^5 + 5n^3 + 7n $$

**Divisibility by 3:**
- Here, the term $3n^5$ gracefully carries the divisor 3 in its fabric.
- The term $5n^3$, though not overtly divisible by 3, subtly upholds the divisibility rule; for when $n$ is an integer, its cube $n^3$ maintains the divisibility characteristics of $n$. Thus, if $n$ is divisible by 3, so is $n^3$, and if not, the factor of 5 in $5n^3$ does not disturb this property.
- Similarly, the term $7n$ is divisible by 3, as 3 is inherently woven into its structure.

**Divisibility by 5:**
- The narrative for divisibility by 5 unfolds similarly. The terms $3n^5$ and $5n^3$ are naturally divisible by 5, for they bear the number 5 in their constitution.
- The term $7n$, like $5n^3$, adheres to the divisibility rule of $n$, ensuring that the entire expression $15S$ is divisible by 5, given $n$ is an integer.

Thus, with $15S$ being divisible by both 3 and 5, it stands as a testament to the power of integers and their unique prime factorizations, a cornerstone of arithmetic.


# Divisibility of Binomial Expansion

The divisibility of a binomial expansion in the context of a prime number $p$ is a fascinating topic, elegantly intertwining number theory with combinatorics. Let's consider the binomial expansion of $(a + b)^n$, where $n$ is a natural number and $a, b$ are integers. The expansion is given by:

$$(a + b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k}b^k$$

Here, $\binom{n}{k}$ represents the binomial coefficients, computed as $\frac{n!}{k!(n-k)!}$.

Now, to explore divisibility by a prime number $p$, we delve into a theorem from number theory: **Fermat's Little Theorem**. This theorem states that for any integer $a$ not divisible by $p$, $a^{p-1} \equiv 1 \mod p$. This theorem can be extended to assert that $a^p \equiv a \mod p$.

### Conditions for Divisibility

1. **Prime Number**: The number $p$ must be prime.
2. **Binomial Coefficients**: For $0 < k < p$, where $p$ is prime, $\binom{p}{k}$ is divisible by $p$. This is because the numerator of $\binom{p}{k} = \frac{p!}{k!(p-k)!}$ contains the prime $p$, but the denominator does not, as $k$ and $(p-k)$ are both less than $p$ and hence cannot contain $p$ as a factor.

### Application in Binomial Expansion

Given $(a + b)^p$, the expansion is:

$$(a + b)^p = a^p + \binom{p}{1}a^{p-1}b + \binom{p}{2}a^{p-2}b^2 + \ldots + \binom{p}{p-1}ab^{p-1} + b^p$$

By Fermat's Little Theorem, $a^p \equiv a \mod p$ and $b^p \equiv b \mod p$. Also, for $1 \leq k \leq p-1$, each $\binom{p}{k}a^{p-k}b^k$ is divisible by $p$ since $\binom{p}{k}$ is divisible by $p$. Hence, each term in the expansion, except for the first and last, is divisible by $p$. Therefore, we can write:

$$(a + b)^p \equiv a^p + b^p \equiv a + b \mod p$$

This result elegantly shows that under the realm of modular arithmetic with a prime modulus, the binomial expansion retains a symmetrical and simplified form, demonstrating the profound interplay between combinatorial structures and number theory.

# Testing for primality using Fermat's Little Theorem

Using Fermat's Little Theorem for primality testing involves a basic but effective approach. The theorem states that if $p$ is a prime number and $a$ is an integer that is not divisible by $p$, then $a^{p-1} \equiv 1 \mod p$. This property can be used as a test for primality, though it's important to note that it can produce false positives (numbers that pass the test but are not prime), known as Carmichael numbers.

### Fermat Primality Test Procedure

1. **Choose a Random Integer \( a \)**: Pick a random integer $a$ such that $1 < a < p$, where $p$ is the number being tested for primality.

2. **Compute \( a^{p-1} \mod p \)**: Calculate $a^{p-1} \mod p$. 

3. **Check the Result**: 
    - If $a^{p-1} \mod p \neq 1$, then $p$ is not prime.
    - If $a^{p-1} \mod p = 1$, then $p$ might be prime. 

4. **Repeat the Test (Optional)**: For increased accuracy, repeat the test with different values of $a$. The more tests passed, the higher the likelihood that $p$ is prime.

### Limitations

- **False Positives**: Some composite numbers (notably [[Carmichael numbers]]) can still satisfy the condition $a^{p-1} \equiv 1 \mod p$ for several values of $a$. Hence, passing the Fermat test does not guarantee that the number is prime, only that it is likely to be prime.

- **Deterministic Tests**: For a conclusive test, other methods like the Miller-Rabin test [[Lecture 2 - Survey of the Course#^b62d2d]] or AKS primality test are preferred as they provide more reliable results, especially for larger numbers.

### Example

Let's conduct a Fermat primality test on a small number, say 7. Choose a random integer $a$, such as 2, and compute:

$$ 2^{7-1} \mod 7 $$

If the result is 1, then according to Fermat's test, 7 might be prime. We can perform this calculation to verify the result.

The calculation yields $2^{6} \mod 7 = 1$. According to  Fermat's primality test, since $1$ is the result, the number $7$ might be prime. Given that $7$ is indeed a prime number, this example aligns with Fermat's theorem. However, remember that for larger numbers, especially for Carmichael numbers, this test might give misleading results, and more robust primality tests should be employed.

## Note:
The Fermat's Little Theorem test for the primality of a number is actually a probabilistic test for primality, instead of it being a deterministic test like the miller rabin test

# Proof that there are infinitely many primes of the form (4n + 1)

**Proof:**

Assume, for contradiction, that there are only a finite number of primes of the form $4n + 1$, and let these primes be $p_1, p_2, \ldots, p_k$.

Consider the number $N = 4p_1p_2\ldots p_k - 1$. This number is clearly odd, and it is not divisible by any of the primes $p_1, p_2, \ldots, p_k$, since dividing $N$ by any of these primes gives a remainder of -1.

However, every integer greater than 1 has a prime divisor. So, $N$ must have a prime divisor, say $q$. This prime $q$ cannot be of the form $4n + 3$ because the product of numbers of the form $4n + 3$ is again of the form $4n + 3$, and subtracting 1 would result in a number of the form $4n + 2$ or $4n$, but $N$ is of the form $4n - 1$.

Therefore, the prime divisor $q$ of $N$ must be of the form $4n + 1$. However, this leads to a contradiction since $q$ cannot be among $p_1, p_2, \ldots, p_k$ (as it does not divide $N$ evenly), and we assumed that all primes of the form $4n + 1$ are among these.

Thus, our initial assumption that there are only finitely many primes of the form $4n + 1$ must be false. Therefore, there are infinitely many primes of the form $4n + 1$.


