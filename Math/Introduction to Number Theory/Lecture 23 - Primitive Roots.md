# Primitive Roots in Modular Arithmetic

In modular arithmetic, primitive roots play a fundamental role. Let's explore what primitive roots are and their significance in this context.

## Definition of Primitive Roots

**Definition:** In modular arithmetic, for a positive integer $m$, an integer $a$ is called a primitive root modulo $m$ if the set of powers of $a$ modulo $m$ generates all the positive integers relatively prime to $m$. In other words, $a$ is a primitive root modulo $m$ if the order of $a$ modulo $m$ is $\phi(m)$, where $\phi(m)$ is Euler's totient function.

## Euler's Totient Function

Before delving deeper into primitive roots, let's briefly recall Euler's totient function, denoted as $\phi(m)$. Euler's totient function calculates the number of positive integers less than or equal to $m$ that are coprime (relatively prime) to $m$.

$$
\phi(m) = \text{number of positive integers coprime to } m
$$

Euler's Totient Theorem establishes a crucial relationship between Euler's totient function and powers modulo $m$:

**Euler's Totient Theorem:** If $a$ is coprime to $m$, then $a^{\phi(m)} \equiv 1 \pmod{m}$.

## Significance of Primitive Roots

Now, let's discuss why primitive roots are significant in modular arithmetic:

### 1. Existence of Primitive Roots

**Theorem:** For any prime number $p$, there exists at least one primitive root modulo $p$.

This theorem implies that primitive roots always exist for prime moduli, making them essential in many applications, including cryptography and number theory.

### 2. Generating Residue Classes

Primitive roots help generate all the residue classes modulo $m$ for any positive integer $m$. This means that by raising a primitive root to different powers, we can obtain all possible residues modulo $m$. In essence, primitive roots allow us to explore the entire set of residues modulo $m$.

## Finding Primitive Roots

Finding primitive roots modulo a given integer $m$ can be a challenging task. While there are methods to identify primitive roots for specific values of $m$, there is no general formula to find primitive roots for all integers $m$. However, if we know the prime factorization of $m$, we can use this information to find primitive roots.

## Conclusion

Primitive roots are crucial elements in modular arithmetic, with applications in number theory, cryptography, and various mathematical problems. Their ability to generate all residue classes modulo an integer makes them a valuable tool for exploring the properties of modular arithmetic and designing secure cryptographic systems. While finding primitive roots for any modulus can be complex, their existence for prime moduli is guaranteed, simplifying their use in many mathematical contexts.

# Necessary and Sufficient Condition for a Number to Have a Primitive Root

The concept of primitive roots is related to modular arithmetic, specifically within the context of group theory. A primitive root modulo $n$ is an integer $g$ such that every number coprime to $n$ is congruent to a power of $g$ modulo $n$.

The necessary and sufficient conditions for an integer $n$ to have a primitive root are:

1. $n$ is 1,
2. $n$ is 2,
3. $n$ is 4,
4. $n$ is a power of an odd prime number ($p^k$, where $p$ is an odd prime),
5. $n$ is twice a power of an odd prime ($2p^k$).

No other integers have primitive roots. This is a result of the structure of the multiplicative group of integers modulo $n$, denoted by $(\mathbb{Z}/n\mathbb{Z})^*$. For the cases where $n$ is a prime power or twice a prime power, the group $(\mathbb{Z}/n\mathbb{Z})^*$ is cyclic, meaning that there is an element (a primitive root) whose powers generate all the elements of the group. For other values of $n$, the group is not cyclic, and thus there are no primitive roots.

# Homomorphism between a number $n \mod m$, and the number $kn \mod m$, where m, n and k are integers

In number theory, two groups are considered isomorphic if there is a bijection between them that preserves the group operation. When discussing residue classes modulo $kn$ and $n$, we are referring to the additive groups $(\mathbb{Z}/kn\mathbb{Z}, +)$ and $(\mathbb{Z}/n\mathbb{Z}, +)$, respectively.

The residue classes modulo $n$ are denoted by $[0], [1], [2], \ldots, [n-1]$, and for modulo $kn$ by $[0], [1], [2], \ldots, [kn-1]$. These are not groups under multiplication, but they form groups under addition modulo $n$ and $kn$.

An isomorphism between $(\mathbb{Z}/kn\mathbb{Z}, +)$ and $(\mathbb{Z}/n\mathbb{Z}, +)$ does not always exist because the groups are not always of the same order: $(\mathbb{Z}/kn\mathbb{Z}, +)$ has $kn$ elements, whereas $(\mathbb{Z}/n\mathbb{Z}, +)$ has $n$ elements. They can only be isomorphic if $k=1$, in which case they are actually the same group.

However, there is a related concept where a homomorphism can be established between these two groups, which is a function that respects the group operation. For example, the natural projection map from $(\mathbb{Z}/kn\mathbb{Z}, +)$ to $(\mathbb{Z}/n\mathbb{Z}, +)$ defined by sending the residue class $[a]_{kn}$ to the residue class $[a]_n$ is a group homomorphism.

It's important to note that while this map is surjective, it is not injective unless $k=1$, which means it's not an isomorphism unless $k=1$. This homomorphism demonstrates that $(\mathbb{Z}/n\mathbb{Z}, +)$ is a **quotient group of $(\mathbb{Z}/kn\mathbb{Z}, +)$ when you factor out the subgroup of multiples of $n$** that are also multiples of $kn$, which is the kernel of the homomorphism.

# Extrapolating the primitive roots of 11, using Lagrange's Theorem
In modular arithmetic, the order of an element $g$ in the multiplicative group $(\mathbb{Z}/n\mathbb{Z})^*$ is the smallest positive integer $d$ such that $g^d \equiv 1 \pmod{n}$.

Here's an explanation of the example, followed by relevant theorems and lemmas:

**Explanation:**
1. The Euler totient function $\phi(11) = 10$ since $11$ is prime. This means there are $10$ elements in $(\mathbb{Z}/11\mathbb{Z})^*$.
2. The possible orders of elements in this group divide $\phi(11)$, so the orders can be $1, 2, 5,$ or $10$.
3. If an element has order $d$, then it must satisfy $g^d \equiv 1 \pmod{11}$. There can be at most $d$ solutions to this congruence by Lagrange's theorem.
4. Counting the elements of each possible order, there are at most $1 + 2 + 5 = 8$ elements of orders $1, 2,$ and $5$.
5. Since there are $10$ elements in total, at least $10 - 8 = 2$ must have order $10$. These elements are the primitive roots of $11$.

**Theorems and Lemmas:**
1. **Lagrange's Theorem:** In a finite group, the order of any element divides the order of the group.
2. **Euler's Criterion:** An integer $a$ is a quadratic residue modulo $p$ (a prime) if and only if $a^{\frac{p-1}{2}} \equiv 1 \pmod{p}$.
3. **Fermat's Little Theorem:** For any integer $a$ and prime $p$, if $p \nmid a$ then $a^{p-1} \equiv 1 \pmod{p}$.
4. **Primitive Root Existence:** A primitive root exists for any modulus $n$ if and only if $n$ is of the form $2, 4, p^k,$ or $2p^k$ where $p$ is an odd prime and $k \geq 1$.
5. **Structure of $(\mathbb{Z}/p\mathbb{Z})^*$:** If $p$ is prime, then the group of units modulo $p$, $(\mathbb{Z}/p\mathbb{Z})^*$, is cyclic. This means that it is generated by a single element, a primitive root.

To find the primitive roots of $11$, we would test elements within $(\mathbb{Z}/11\mathbb{Z})^*$ and look for those whose powers generate all non-zero elements modulo $11$. For example, we would check if $g^1, g^2, ..., g^9$ are distinct and non-zero modulo $11$ for some candidate $g$. If so, then $g$ is a primitive root modulo $11$.

# Order of Elements in the multiplicative group of integers modulo $n$

1. **$\phi(d)$ Elements of Order $d$:**
   - In a multiplicative group modulo $n$, there are at most $\phi(d)$ elements of order $d$, where $\phi$ is Euler's totient function. This is because the order of an element must divide the order of the group (Lagrange's theorem), and $\phi(d)$ counts the number of integers up to $d$ that are relatively prime to $d$; these correspond to the generators of the cyclic group of order $d$.

2. **Solutions to $g^d \equiv 1$:**
   - If $g$ has order $d$ in $(\mathbb{Z}/n\mathbb{Z})^*$, then the equation $g^d \equiv 1 \pmod{n}$ will have at most $d$ solutions. This is derived from the definition of the order of an element and the fact that a polynomial of degree $d$ has at most $d$ distinct roots in a field (which extends to the ring of integers modulo $n$ under certain conditions).
#### Example:
Let's take $p = 7$, so we're working with the group $(\mathbb{Z}/7\mathbb{Z})^*$ which consists of the integers $\{1, 2, 3, 4, 5, 6\}$ since all these numbers are relatively prime to $7$. The order of the group is $6$, which is $\phi(7)$ since $7$ is prime.

Now, let's say we want to find the number of solutions to $g^d \equiv 1 \pmod{7}$, for some order $d$. Take $d = 3$ for instance. We're looking for elements in $(\mathbb{Z}/7\mathbb{Z})^*$ that, when raised to the third power, give a result congruent to $1$ modulo $7$.

Computing $g^3$ for each $g$ in $(\mathbb{Z}/7\mathbb{Z})^*$:

- $1^3 \equiv 1 \pmod{7}$
- $2^3 \equiv 8 \equiv 1 \pmod{7}$
- $3^3 \equiv 27 \equiv 6 \pmod{7}$
- $4^3 \equiv 64 \equiv 1 \pmod{7}$
- $5^3 \equiv 125 \equiv 6 \pmod{7}$
- $6^3 \equiv 216 \equiv 6 \pmod{7}$

From this, we see that $g = 1, 2, 4$ satisfy the congruence $g^3 \equiv 1 \pmod{7}$. Thus, there are three solutions to $g^3 \equiv 1 \pmod{7}$ when $g$ is an element of $(\mathbb{Z}/7\mathbb{Z})^*$, which are the $g$ values that have an order dividing $3$. The order of $2$ and $4$ in this group is actually $6$, but $6$ is a multiple of $3$, hence $2^3$ and $4^3$ giving a result of $1$ modulo $7$ still fits within the general statement that a congruence $g^d \equiv 1 \pmod{n}$ has at most $d$ solutions. Here, we have $3$ solutions, which is not more than $d = 3$.

3. **Order $g^k$ has order $d$:**
   - The last statement says that the element $g^k$ will have order $d$ if and only if $k$ and $d$ are coprime (i.e., $\gcd(k, d) = 1$). This is a result of the property that raising $g$ to the $k$-th power effectively "skips" through the order of $g$ in steps of $k$. If $k$ and the order of $g$ share a common factor, then $g^k$ will not generate all elements in the subgroup of order $d$ but rather a proper subset. If $k$ and $d$ are coprime, then the cyclic subgroup generated by $g^k$ will indeed have $d$ distinct elements, making its order $d$.

These principles are fundamental in understanding the structure of the multiplicative group modulo $n$ and are used, among other things, to determine the existence of primitive roots and to compute discrete logarithms.

# Finding Orders of the Primitive Roots of 12
# Analyzing the Conceptual Error in Identifying Orders of Elements

1. **Identifying the Orders:**
   In the handwritten note, the writer lists possible orders of elements: $1, 2, 3, 4, 6$, which are divisors of $\phi(12)$. Since $12$ is not prime, we use $\phi(12)$ instead of $12-1$. The value of $\phi(12)$, which is Euler's totient function of $12$, equals $4$ because there are $4$ numbers less than $12$ and coprime to it: $1, 5, 7, 11$.

2. **Counting the Number of Elements for Each Order:**
   The writer notes that there can be at most $\phi(1)$ elements of order $1$, $\phi(2)$ elements of order $2$, and so on, using the inequality:
  $$ \[
   \#\text{elements of order } d \leq \phi(d)
   \]$$
   The $\phi$ function values are filled in as $1$ for $\phi(1)$, $\phi(2)$; $2$ for $\phi(3)$, $\phi(4)$; and $2$ for $\phi(6)$. Here, $\phi(3) = 2$ and $\phi(4) = 2$ because there are $2$ integers less than $3$ and $4$, respectively, that are coprime to them.

3. **Summation and Inference:**
   The writer sums these up to find that there are at most $8$ elements of orders other than $12$.
   $$
   \[ 1+1+2+2+2 = 8 \]
$$
   Since there are $\phi(12) = 4$ elements in total, and at most $8$ of them have orders other than $12$, this seems to be an error because the sum of potential elements of orders $1, 2, 3, 4,$ and $6$ exceeds the total number of elements in the group.

4. **Correcting the Calculation:**
   However, the correct approach would be to note that since there are $\phi(12) = 4$ elements in $(\mathbb{Z}/12\mathbb{Z})^*$, and we have identified $8$ potential elements of orders that are divisors of $\phi(12)$, there seems to be a contradiction. The mistake likely stems from the fact that not all divisors of $\phi(n)$ necessarily correspond to actual orders of elements in $(\mathbb{Z}/n\mathbb{Z})^*$. In fact, for $n = 12$, the only orders possible are $1$ and $2$, corresponding to the elements $1$ and $11$ for order $1$, and $5$ and $7$ for order $2$.

5. **Primitive Roots:**
   The concept of primitive roots does not apply to $n = 12$ because $12$ is not of the form $2$, $4$, $p^k$, or $2p^k$ for an odd prime $p$ and integer $k \geq 1$. Therefore, there are no primitive roots modulo $12$, and the number of elements of maximal order (which would be the order $\phi(12)$ if primitive roots existed) is actually zero.

The conclusion about the elements of order $12$ is incorrect because the modulus $12$ cannot have elements of order $12$—it has no primitive roots. This appears to be a conceptual misunderstanding in the handwritten note.

# Relationship Between Orders of Elements and Primitive Roots

## Orders of Elements and Primitive Roots

1. **Identifying the Orders:**
   The enumeration of possible orders of elements: $1, 2, 3, 4, 6$, which are divisors of $\phi(12)$, is significant. Here, $\phi(12)$ represents the Euler's totient function value for the modulus $12$. These orders are noteworthy because they signify the potential orders of elements within the multiplicative group modulo $12$, denoted as $(\mathbb{Z}/12\mathbb{Z})^*$.

2. **Counting the Number of Elements for Each Order:**
   The statement highlights that there can be, at most, $\phi(1)$ elements of order $1$, $\phi(2)$ elements of order $2$, and so forth. This observation introduces a crucial mathematical principle: the quantity of elements with a specific order is constrained by the value of Euler's totient function, i.e., $\#\text{elements of order } d \leq \phi(d)$.

3. **The $\phi$ Function Values:**
   The assignment of values to the $\phi$ function is relevant. The values are $1$ for $\phi(1)$ and $\phi(2)$; $2$ for $\phi(3)$ and $\phi(4)$; and $2$ for $\phi(6)$. These values are computed based on the count of positive integers less than the given order that are coprime to that order. For instance, $\phi(3) = 2$ because there are $2$ integers less than $3$ that are coprime to it: $1$ and $2$.

## Connection to Primitive Roots

The mathematical connection between these statements and the concept of primitive roots lies in the identification and quantification of potential orders of elements in the group modulo $12$. When exploring the concept of primitive roots, our interest revolves around elements whose orders are maximal and equal to Euler's totient function value ($\phi(12)$ in this specific case).

The statements, in essence, reveal that the enumerated orders $1, 2, 3, 4,$ and $6$ are conceivable orders for elements in $(\mathbb{Z}/12\mathbb{Z})^*$. These orders are acknowledged because they are divisors of $\phi(12)$. The calculation then proceeds to determine the count of elements that could potentially possess these orders.

In the context of primitive roots, these statements are pertinent because, for an integer to be a primitive root modulo $n$, it must have an order equal to $\phi(n)$. This ensures that the integer generates all coprime residues modulo $n$. The calculation effectively identifies and quantifies the elements that could potentially serve as primitive roots by having orders equal to $\phi(12)$.

In conclusion, these mathematical statements are interrelated with the concept of primitive roots by pinpointing and quantifying potential orders of elements within a mathematical group modulo $12$. This is an initial step in determining whether any of these elements might qualify as primitive roots by possessing maximal orders, which correspond to $\phi(12)$.

# Proof: If p is Prime, p Has Primitive Roots

Let's prove the statement: If $p$ is a prime number, then $p$ has primitive roots. This proof will rely on the fundamental properties of prime numbers and group theory.

## Preliminary Definitions and Concepts

Before we proceed with the proof, let's establish some key concepts and definitions:

1. **Primitive Roots**: An integer $g$ is a primitive root modulo $p$ if the set of powers of $g$ modulo $p$ generates all positive integers coprime to $p$. In other words, the order of $g$ modulo $p$ is equal to $\phi(p)$, where $\phi$ is Euler's totient function.

2. **Euler's Totient Function ($\phi$)**: For a positive integer $n$, $\phi(n)$ is the count of positive integers less than or equal to $n$ that are coprime to $n$.

## Proof

Now, let's prove the statement:

**Statement**: If $p$ is a prime number, then $p$ has primitive roots.

**Proof**:

1. We begin by considering the group of integers modulo $p$, denoted as $(\mathbb{Z}/p\mathbb{Z})^*$.

2. Since $p$ is prime, all integers less than $p$ are coprime to $p$. Therefore, $\phi(p) = p - 1$. This is a fundamental property of Euler's totient function.

3. According to a fundamental theorem in group theory, a cyclic group of order $n$ has exactly $\phi(n)$ generators. In our case, we are interested in the group $(\mathbb{Z}/p\mathbb{Z})^*$, which is a cyclic group of order $p-1$. 

4. Since $\phi(p) = p - 1$, there are exactly $\phi(p) = p - 1$ generators in the group $(\mathbb{Z}/p\mathbb{Z})^*$.

5. By definition, a primitive root modulo $p$ is a generator of the group $(\mathbb{Z}/p\mathbb{Z})^*$. Since there are $p - 1$ generators in this group (as shown in step 4), there must be at least one primitive root modulo $p$.

6. Therefore, if $p$ is a prime number, it has at least one primitive root.

This completes the proof. We have shown that if $p$ is a prime number, then the group of integers modulo $p$ has at least one primitive root, which verifies the statement.

# Proof of : $$

\sum_{d|n} \phi(d) = n.

$$
This is a well-known identity involving the Euler's totient function $\phi$, which counts the number of positive integers up to $n$ that are coprime to $n$. The identity states that the sum of the totient function over all divisors of $n$ equals $n$ itself.

**Proof:**

The proof can be given using the principle of inclusion-exclusion or considering the fractions of the form $\frac{k}{n}$ where $1 \leq k \leq n$.

Consider the set of fractions $\left\{ \frac{1}{n}, \frac{2}{n}, \ldots, \frac{n}{n} \right\}$. We will reduce each fraction to its lowest terms. The fraction $\frac{k}{n}$ will be in lowest terms if and only if $k$ and $n$ are coprime, that is, $\gcd(k, n) = 1$. There are exactly $\phi(n)$ such fractions for a given $n$.

Now, we look at the fractions where the denominator when reduced is a divisor $d$ of $n$. There are $\phi(d)$ such fractions for each $d$ because there are $\phi(d)$ numbers less than $d$ that are coprime to $d$.

As every fraction $\frac{k}{n}$ for $1 \leq k \leq n$ can be uniquely reduced to a form where the denominator is a divisor of $n$, and there are $\phi(d)$ such fractions for each divisor $d$ of $n$, summing over all divisors of $n$ gives us exactly $n$ different fractions.

Therefore, summing $\phi(d)$ over all divisors $d$ of $n$ counts each number from $1$ to $n$ exactly once, which proves the identity.

**Related Results, Lemmas, and Theorems:**

1. **Multiplicativity of $\phi$:** Euler's totient function is multiplicative: If $m$ and $n$ are coprime, then $\phi(mn) = \phi(m)\phi(n)$.
   
2. **Euler's Product Formula:** $\phi(n)$ can be calculated using the prime factorization of $n$: If $n = p_1^{k_1} \cdots p_r^{k_r}$, then
$$
   
   \phi(n) = n \left(1 - \frac{1}{p_1}\right) \cdots \left(1 - \frac{1}{p_r}\right).
   
   $$

3. **Euler's Theorem:** For any integer $a$ and $n$ that are coprime, $a^{\phi(n)} \equiv 1 \pmod{n}$.

4. **Fermat's Little Theorem:** A special case of Euler's theorem where $n$ is a prime $p$, it states that for any integer $a$ not divisible by $p$, $a^{p-1} \equiv 1 \pmod{p}$.

5. **Structure of Units Group:** The group $(\mathbb{Z}/n\mathbb{Z})^*$ is cyclic if and only if $n$ is 1 or 2, a power of an odd prime, or twice a power of an odd prime. This gives us information about the existence of primitive roots.

6. **Mobius Inversion Formula:** If $g(n)$ and $f(n)$ are arithmetic functions related by $g(n) = \sum_{d|n} f(d)$, then $f(n)$ can be recovered by $f(n) = \sum_{d|n} g(d) \mu\left(\frac{n}{d}\right)$ where $\mu$ is the Möbius function.

The given identity is a fundamental result in number theory with far-reaching implications in the study of arithmetic functions and group theory.