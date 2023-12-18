# **Primitive Roots of Odd Prime Powers**

To discuss primitive roots of odd prime powers, we first need to establish some foundational concepts and results related to modular arithmetic. Let's begin with a few definitions and lemmas.

**Definition 1 (Primitive Root)**: Let $p$ be a prime number, and $a$ be an integer not divisible by $p$. We say that $a$ is a primitive root modulo $p$ if the set $\{a^0, a^1, a^2, \ldots, a^{p-2}\}$ contains all the integers from $1$ to $p-1$ in some order modulo $p$. In other words, $a$ is a primitive root if the powers of $a$ generate all non-zero residues modulo $p$.

**Lemma 1**: If $a$ is a primitive root modulo $p$, then for any positive integer $k$, $a$ is also a primitive root modulo $p^k$.

**Proof**: To prove this, let's consider the order of $a$ modulo $p^k$, denoted as $ord_{p^k}(a)$. By the definition of a primitive root modulo $p$, we know that $a$ generates all non-zero residues modulo $p$. Therefore, $a$ has order $\varphi(p) = p-1$ modulo $p$. 

Now, we need to show that $a$ is a primitive root modulo $p^k$. To do this, we'll use the concept of the Euler's totient function $\varphi(n)$. By Euler's Totient Theorem, if $a$ and $n$ are coprime, then $a^{\varphi(n)} \equiv 1 \pmod{n}$. Since $a$ is coprime to $p^k$, we can use Euler's Totient Theorem for $n = p^k$:

$$
a^{\varphi(p^k)} \equiv 1 \pmod{p^k}.
$$

Now, $\varphi(p^k) = p^{k-1}(p-1)$, and since $a^{p-1} \equiv 1 \pmod{p}$ (as $a$ is a primitive root modulo $p$), we have:

$$
a^{p^{k-1}(p-1)} \equiv 1 \pmod{p}.
$$

Since $a^{p^{k-1}(p-1)} \equiv 1 \pmod{p}$, it follows that $a^{p^{k-1}(p-1)}$ is also congruent to $1$ modulo $p^k$. Therefore, the order of $a$ modulo $p^k$ is at least $p^{k-1}(p-1)$.

Now, let's consider any integer $x$ coprime to $p^k$. By Euler's Totient Theorem, we have:

$$
x^{\varphi(p^k)} \equiv 1 \pmod{p^k}.
$$

Since $a$ has order at least $p^{k-1}(p-1)$ modulo $p^k$, we can express $p^{k-1}(p-1)$ as $j \cdot \varphi(p^k)$ for some positive integer $j$. Therefore:

$$
a^{p^{k-1}(p-1)} \equiv a^{j\varphi(p^k)} \equiv (a^{\varphi(p^k)})^j \equiv 1^j \equiv 1 \pmod{p^k}.
$$

This shows that $a$ raised to the power $p^{k-1}(p-1)$ is congruent to $1$ modulo $p^k$. Since the order of $a$ modulo $p^k$ must be the smallest positive integer $r$ such that $a^r \equiv 1 \pmod{p^k}$, we have shown that the order of $a$ modulo $p^k$ is $p^{k-1}(p-1)$, which is the same as $\varphi(p^k)$. Therefore, $a$ is a primitive root modulo $p^k$. 

**Corollary 1**: If $p$ is an odd prime and $g$ is a primitive root modulo $p$, then $g$ is also a primitive root modulo $p^k$ for any positive integer $k$.

Now that we have established the properties of primitive roots modulo prime powers, we can use this knowledge to explore further questions and applications in number theory and modular arithmetic. The concept of primitive roots plays a fundamental role in various cryptographic and mathematical algorithms.

# Proof of the Existence of Primitive Roots for  $p^2$

To prove the existence of primitive roots for $p^2$, where $p$ is a prime number, we will rely on some key concepts and theorems related to primitive roots.

$$
\textbf{Theorem 1 (Existence of Primitive Roots)}: \text{For any prime number } p, \text{ there exists at least one primitive root modulo } p.
$$

Proof: Let $p$ be a prime number, and $g$ be a primitive root modulo $p$. This means that $g$ satisfies the congruence:

$$
g^{p-1} \equiv 1 \pmod{p}.
$$

Now, we aim to extend this concept to $p^2$, seeking the existence of primitive roots modulo $p^2$. To accomplish this, we explore two cases:

Case 1: $g^{p-1} \not\equiv 1 \pmod{p^2}$

In this case, $g$ already fulfills the criteria of being a primitive root modulo $p^2$, as it does not possess an order of $1$ modulo $p^2$ (due to $g^{p-1} \not\equiv 1 \pmod{p^2}$).

Case 2: $g^{p-1} \equiv 1 \pmod{p^2}$

Here, we must identify an integer $h$ such that:

$$
h^{p-1} \not\equiv 1 \pmod{p^2}.
$$

Lemma 1: Given that $a$ is a primitive root modulo $p$, $a$ retains this property modulo $p^2$ unless $a^{p-1} \equiv 1 \pmod{p^2}$.
 
Proof of Lemma 1: Let $a$ be a primitive root modulo $p$, and suppose $a^{p-1} \equiv 1 \pmod{p^2}$. This implies that $a$ holds an order of $p-1$ modulo $p^2$. Since $p-1$ is not divisible by $p$, we invoke Euler's Totient Theorem to deduce that $a^{p-1} \equiv 1 \pmod{p}$ cannot lead to $a^{p-1} \equiv 1 \pmod{p^2}$. This conclusion contradicts our assumption, thus establishing that $a$ remains a primitive root modulo $p^2$ unless $a^{p-1} \equiv 1 \pmod{p^2}$.

Returning to Case 2, since $g$ is a primitive root modulo $p$, as per Lemma 1, $g$ serves as a primitive root modulo $p^2$ unless $g^{p-1} \equiv 1 \pmod{p^2}$. However, in Case 2, we presumed that $g^{p-1} \equiv 1 \pmod{p^2}$, implying the necessity to locate an alternative integer $h$ satisfying $h^{p-1} \not\equiv 1 \pmod{p^2}$.

To identify such an $h$, we examine the set of integers distinct from $1$ modulo $p^2$. Euler's Totient Function asserts that the count of integers less than $p^2$ coprime to $p^2$ is $\phi(p^2) = p(p-1)$. Hence, $p(p-1)$ integers exist that are not congruent to $1$ modulo $p^2$. From this set, we can confidently select one $h$ such that $h^{p-1} \not\equiv 1 \pmod{p^2}$.

In either Case 1 or Case 2, we identify an integer (either $g$ or $h$) serving as a primitive root modulo $p^2$. This concludes the proof, affirming the existence of primitive roots for $p^2$.

This proof establishes the existence of at least one primitive root modulo $p^2$ for any prime number $p$, a significant result in the realm of number theory.

# Theorem Regarding Primitive Roots of $p^2$ extending to the $p^n$ case

To prove that if $g$ is a primitive root of $p^2$ for an odd prime $p$, then $g$ is also a primitive root of $p^n$ for $n > 1$, we use the fact that for any prime $p$, if $g$ is a primitive root modulo $p^k$, then $g$ is a primitive root modulo $p^{k+1}$ if and only if $g^{p^k} \not\equiv 1 \pmod{p^{k+1}}$.

Since $g$ is a primitive root of $p^2$, $g$ is also a primitive root of $p$, which means that:

1. $g^{p-1} \equiv 1 \pmod{p}$ by Fermat's Little Theorem.
2. $g^k \not\equiv 1 \pmod{p}$ for any $k < p-1$, since $g$ is a primitive root modulo $p$.

To be a primitive root of $p^2$, $g$ must also satisfy:

3. $g^{p(p-1)} \equiv 1 \pmod{p^2}$ since $\phi(p^2) = p(p-1)$ where $\phi$ is Euler's totient function.
4. $g^k \not\equiv 1 \pmod{p^2}$ for any $k < p(p-1)$.

Now, we want to show $g$ is a primitive root for $p^n$. For $g$ to be a primitive root of $p^n$, it must satisfy $g^{\phi(p^n)} \equiv 1 \pmod{p^n}$ and $g^k \not\equiv 1 \pmod{p^n}$ for $0 < k < \phi(p^n)$.

We have $\phi(p^n) = p^{n-1}(p-1)$. Since $g$ is a primitive root of $p^2$, we only need to show that $g^{p^{n-1}(p-1)} \not\equiv 1 \pmod{p^n}$ for any $n > 2$. 

Since $g$ is already a primitive root of $p^2$, we have $g^{p(p-1)} \not\equiv 1 \pmod{p^2}$. Now, suppose for some $k$, $g^{p^k} \equiv 1 \pmod{p^{k+1}}$. Then, $g^{p^k} = 1 + lp^{k+1}$ for some integer $l$. Raising both sides to the $p$-th power gives:

$$
g^{p^{k+1}} = (1 + lp^{k+1})^p = 1 + lp^{k+2} + \frac{p(p-1)}{2}l^2p^{2k+2} + \ldots
$$

The second term and the following terms are all divisible by $p^{k+2}$, so:

$$
g^{p^{k+1}} \equiv 1 \pmod{p^{k+2}}
$$

This contradicts the assumption that $g$ is a primitive root of $p^2$ since it would imply $g^{p^2} \equiv 1 \pmod{p^3}$, which cannot be true.

Therefore, $g^{p^k} \not\equiv 1 \pmod{p^{k+1}}$ for any $k \geq 1$, and by induction, $g$ is a primitive root for all $p^n$ where $n > 1$.

This proof relies on the properties of primitive roots and exponents in modular arithmetic and uses an inductive argument to extend the property from $p^2$ to $p^n$.

# Equivalent statements in the context of primitive roots modulo n

1. $m$ has $\phi(m)$ primitive roots.
2. $m$ has $\phi(\phi(m))$ primitive roots.
3. $m$ is of the form $1, 2, 4, p^k, 2p^k$ where $p$ is an odd prime.
4. If $x^2 \equiv 1 \mod m$, then $x \equiv \pm 1 \mod m$.

It also mentions Wilson's Theorem, which states:
$$ \prod_{\substack{a \mod m \\ \gcd(a, m) = 1}} a \equiv -1 \mod m. $$

To prove the equivalence, we go through the conditions:

Condition 3 is a theorem which states that an integer $m$ has a primitive root if and only if $m$ is of the form $2$, $4$, $p^k$, or $2p^k$ where $p$ is an odd prime and $k$ is a positive integer. This is a well-established result in number theory.

From condition 3, we can derive condition 1. If $m$ has a primitive root, then it has exactly $\phi(m)$ elements that are relatively prime to $m$, each of which can be generated by the primitive root to the power of integers from $1$ to $\phi(m)$. Thus, there are $\phi(m)$ different primitive roots modulo $m$.

Condition 2 follows from condition 1 since the number of primitive roots mod $m$ is $\phi(m)$, and each primitive root mod $m$ corresponds to a unique primitive root mod $\phi(m)$.

For condition 4, we note that if $x^2 \equiv 1 \mod m$ and $m$ has a primitive root, $m$ must be of the form given in condition 3. For such $m$, the equation $x^2 \equiv 1 \mod m$ implies that $x$ must be congruent to $\pm 1$ modulo $m$. This is because the order of any element dividing $\phi(m)$ must be a factor of $\phi(m)$, and since $\pm 1$ are the only elements of order $2$, $x$ must be congruent to either $1$ or $-1$ modulo $m$.

Lastly, Wilson's Theorem provides a property of the integers less than $m$ and relatively prime to $m$. While not directly related to the existence of primitive roots, Wilson's Theorem is often discussed in the context of number theory and congruences involving factorial expressions.

Each of these conditions or statements is interrelated and part of the broader discussion on the criteria for the existence of primitive roots modulo $m$. The equivalences are part of the foundational theorems in elementary number theory.

# "Any number mod $2^n$, coprime to $2^n$ is of the form $\pm 5^k$."

To understand the statement "Any number mod $2^n$, coprime to $2^n$ is of the form $\pm 5^k$," we need to delve into number theory and modular arithmetic. This statement is closely related to Euler's totient function and the properties of numbers that are coprime to powers of 2.

## Proof of the Statement:

We want to prove that any number, when taken modulo $2^n$ and is coprime to $2^n$, can be expressed in the form $\pm 5^k$. 

### Step 1: Coprime Numbers to $2^n$:

First, let's consider numbers that are coprime to $2^n$. These numbers do not have any factors of 2. We can express them as $2^0$ times some other integer, which means they are odd numbers. Therefore, any number coprime to $2^n$ is odd.

### Step 2: Euler's Totient Function:

Now, let's use Euler's totient function $\phi(2^n)$ to count the number of positive integers less than or equal to $2^n$ that are coprime to $2^n$. Since $2^n$ is a power of 2, it only has one prime factor, which is 2. 

Euler's totient function for a power of a prime is given by: $\phi(p^n) = p^n - p^{n-1}$, where $p$ is a prime.

In our case, $\phi(2^n) = 2^n - 2^{n-1} = 2^{n-1}$. So, there are $2^{n-1}$ positive integers less than or equal to $2^n$ that are coprime to $2^n$.

### Step 3: Expressing Coprime Numbers:

Now, we have established that any number coprime to $2^n$ is odd, and there are $2^{n-1}$ such numbers. We want to show that these numbers can be expressed in the form $\pm 5^k$.

Let's consider the odd positive integers less than $2^n$. We can express any odd number as $2k + 1$, where $k$ is a non-negative integer.

Now, let's examine the expression $2k + 1$ modulo 5:
- When $k$ is even, $2k + 1 \equiv 1 \pmod{5}$. So, it can be expressed as $1 \cdot 5^0 = 5^0$.
- When $k$ is odd, $2k + 1 \equiv 3 \pmod{5}$. So, it can be expressed as $-1 \cdot 5^0 = -5^0$.

Therefore, any odd number less than $2^n$ can be expressed as $\pm 5^0$ modulo 5.

### Step 4: Conclusion:

We have shown that any odd number coprime to $2^n$ can be expressed as $\pm 5^0$ modulo 5. Since there are $2^{n-1}$ such numbers, they can collectively be expressed as $\pm 5^0, \pm 5^0, \ldots, \pm 5^0$ ($2^{n-1}$ times).

Hence, we have established that any number taken modulo $2^n$ and coprime to $2^n$ can indeed be expressed in the form $\pm 5^k$, where $k$ can take values from $0$ to $n-1$.

# Logarithms of p-adic numbers
In the realm of number theory, p-adic logarithms hold a significant place. These logarithms are a fundamental concept, particularly in the context of p-adic numbers, and they find applications in various branches of mathematics, including algebraic number theory and algebraic geometry. To delve into p-adic logarithms, we will first establish some necessary definitions and background information.

## Definitions and Background:

1. **p-adic Numbers ($\mathbb{Q}_p$)**: The p-adic numbers, denoted as $\mathbb{Q}_p$, are an extension of the rational numbers ($\mathbb{Q}$). They are a collection of numbers obtained by allowing the expansion of a rational number in powers of a prime number $p$. The norm on $\mathbb{Q}_p$ measures how divisible a number is by $p$, and it plays a central role in p-adic analysis.

2. **p-adic Valuation ($v_p$)**: For any nonzero rational number $q$, the p-adic valuation $v_p(q)$ is defined as the largest power of $p$ that divides $q$. In other words, it measures how many times $p$ can be factored out of $q$.

3. **p-adic Absolute Value ($| \cdot |_p$)**: The p-adic absolute value $| \cdot |_p$ is a way to quantify the size of a rational number in the context of p-adic numbers. It is defined as $|q|_p = p^{-v_p(q)}$, where $q$ is a nonzero rational number. This absolute value satisfies the strong triangle inequality.

## The p-adic Logarithm:

Now, let's explore the concept of the p-adic logarithm. Given a nonzero rational number $q$ in $\mathbb{Q}_p$, the p-adic logarithm $\log_p(q)$ is a function that aims to find an exponent to which we must raise $p$ to obtain $q$. In other words, it seeks to solve the equation:

$$
p^{\log_p(q)} = q
$$

The p-adic logarithm is a powerful tool for understanding the structure of p-adic numbers and their properties. It allows us to study exponential and logarithmic functions within the p-adic number system, similar to how we do with real and complex numbers.

## Properties and Applications:

1. **p-adic Exponential Function**: The p-adic logarithm is intimately related to the p-adic exponential function, which is the inverse operation. The exponential function, denoted as $\exp_p(x)$, is defined as the solution to the equation $p^x = q$. These functions are essential in studying p-adic analysis and have applications in algebraic number theory.

2. **p-adic L-functions**: The study of p-adic logarithms and exponentials plays a crucial role in the theory of L-functions, particularly in the context of Elliptic Curves and Modular Forms. These L-functions encode deep arithmetic information and have connections to Fermat's Last Theorem and other famous conjectures.

3. **Algebraic Geometry**: In algebraic geometry, the p-adic logarithm is used to define the p-adic height pairing, which is a fundamental tool for studying the arithmetic of algebraic varieties.

In conclusion, p-adic logarithms are a fundamental concept in number theory and p-adic analysis. They provide a means to understand the structure of p-adic numbers and have far-reaching applications in various areas of mathematics, including algebraic number theory and algebraic geometry. The concept of p-adic logarithms is intricately connected to the theory of p-adic numbers, and its study opens doors to exploring deeper mathematical landscapes.

# Finding p-adic Logarithm with an Example

In this explanation, we will explore the concept of the p-adic logarithm and illustrate how to find it using an example. The p-adic logarithm is a fundamental concept in number theory, particularly in the context of p-adic numbers.

### Definition of p-adic Logarithm:

Given a nonzero rational number $q$ in the field of p-adic numbers, denoted as $\mathbb{Q}_p$, the p-adic logarithm, denoted as $\log_p(q)$, is defined as the exponent to which we must raise the prime number $p$ to obtain $q$. In other words, it solves the equation:

$$
p^{\log_p(q)} = q
$$

### Example: Finding the 2-adic Logarithm of 8

Let's illustrate how to find the 2-adic logarithm of the number 8, denoted as $\log_2(8)$.

We want to find $\log_2(8)$ such that $2^{\log_2(8)} = 8$. 

To do this, we need to determine how many times we can divide 8 by 2 until we reach 1. This process is essentially finding the exponent to which 2 must be raised to get 8.

Starting with 8:
- Divide by 2: $8 / 2 = 4$
- Divide by 2 again: $4 / 2 = 2$
- Divide by 2 once more: $2 / 2 = 1$

We have reached 1, which means that 2 must be raised to the power of 3 to obtain 8. Therefore, $\log_2(8) = 3$.

In mathematical notation:
$$
2^{\log_2(8)} = 2^3 = 8
$$

### Conclusion:

In this example, we found the 2-adic logarithm of 8 to be 3. This means that $2^3$ equals 8 in the 2-adic number system. The p-adic logarithm is a powerful tool for understanding p-adic numbers and their properties, and it allows us to determine the exponent to which a prime number must be raised to obtain a given p-adic number.

# 3 - Adic Logarithm of 100:
### Calculation:

Let's calculate $\log_3(100)$:

We aim to find $\log_3(100)$ such that $3^{\log_3(100)} = 100$.

Starting with 100, we need to determine how many times we can divide it by 3 until we reach 1, which will reveal the exponent to which 3 must be raised to obtain 100.

- Divide by 3: $100 / 3 = 33$.
- Divide by 3 again: $33 / 3 = 11$.
- Divide by 3 once more: $11 / 3 = 3$.
- Divide by 3 yet again: $3 / 3 = 1$.

We have reached 1, which means that $\log_3(100) = 4$. Therefore, $3^4 = 100$ in the 3-adic number system.

### Curiosity:

In the 3-adic system, it's interesting to note that, unlike the real numbers, there is no unique representation for 100. Both $3^4$ and $(-3)^4$ are equal to 100 in the 3-adic system, reflecting the non-uniqueness of representations in p-adic numbers.

# Simple Primality Test
For a given number $p$, if we want to test whether $p$ is prime:

1. Factor $p-1$ into its prime factors.
2. For each prime factor $q$ of $p-1$, find an element $g$ in the range $2$ to $p-1$ such that $g^{(p-1)/q} \not\equiv 1 \mod p$.

The element $g$ is said to have an order $p-1$ if no smaller positive exponent $e$ exists such that $g^e \equiv 1 \mod p$. If such a $g$ exists for all prime factors $q$ of $p-1$, then $p$ is likely prime.

**Proof**:

The idea behind the test is that for $p$ to be prime, $\mathbb{Z}/p\mathbb{Z}$ (the integers modulo $p$) must be a cyclic group of order $p-1$ when $p$ is prime. In a cyclic group of order $p-1$, there exists a primitive root $g$ such that $g$ raised to any power less than $p-1$ will not be congruent to $1$ modulo $p$.

If $p$ is indeed prime, then by Lagrange's theorem, the order of any element must divide the order of the group, which is $p-1$ for the multiplicative group modulo $p$. Hence, if for any prime divisor $q$ of $p-1$, we have an element $g$ such that $g^{(p-1)/q} \not\equiv 1 \mod p$, it suggests that $g$ has order $p-1$ and that the group is indeed of order $p-1$, supporting the primality of $p$.

If, on the other hand, $g^{(p-1)/q} \equiv 1 \mod p$ for some prime divisor $q$, this would mean that $g$ has an order that is a proper divisor of $p-1$, which cannot be the case if $p$ is prime and $g$ is a primitive root modulo $p$. Hence, $p$ cannot be prime.

**Example**:

Let's use the test on a known prime, $p = 101$. We have $p-1 = 100 = 2^2 \cdot 5^2$.

We need to find a $g$ such that $g^{100/2} = g^{50} \not\equiv 1 \mod 101$ and $g^{100/5} = g^{20} \not\equiv 1 \mod 101$.

Let's take $g = 2$ and check:

1. $2^{50} \mod 101$
2. $2^{20} \mod 101$

If both expressions are not congruent to $1$ mod $101$, then $101$ passes the test for these divisors of $p-1$, and it is likely prime (which we already know it is).

We can use Python to perform these calculations.

For $p = 101$ and $g = 2$:

1. $2^{50} \mod 101 = 100$
2. $2^{20} \mod 101 = 95$

Since neither of these results is congruent to $1$ modulo $101$, the number $101$ passes the test for the divisors $2$ and $5$ of $p-1$. Therefore, according to this test, $101$ is likely prime, which is consistent with the fact that $101$ is a known prime number.