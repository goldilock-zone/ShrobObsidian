# Order
Fermat's Little Theorem is a beautiful intersection of number theory and abstract algebra, involving the concept of order in a group. To delve into this theorem, let's first establish the fundamental concepts.

### Order in Abstract Algebra

In abstract algebra, the order of an element $a$ in a group refers to the smallest positive integer $n$ such that $a^n$ is the identity element of the group. In the context of integers modulo $p$ (where $p$ is a prime), the order of an integer $a$ is the smallest positive integer $n$ such that $a^n \equiv 1 \pmod{p}$.

### Fermat's Little Theorem

Fermat's Little Theorem states that if $p$ is a prime number, then for any integer $a$, the number $a^p - a$ is an integer multiple of $p$. In the language of congruences, it is often written as:
$$ a^p \equiv a \pmod{p} $$

For any integer $a$ that is not divisible by $p$, Fermat's Little Theorem simplifies to:
$$ a^{p-1} \equiv 1 \pmod{p} $$

### Connection to Order

The connection to order here is subtle but profound. If $a$ is not divisible by $p$ (i.e., $a$ and $p$ are coprime), the theorem implies that the order of $a$ in the multiplicative group of integers modulo $p$ divides $p-1$. This is because $a^{p-1} \equiv 1 \pmod{p}$, and the order of $a$ **is the smallest such exponent.**

# Proof: Order of a mod p, divides p-1

To rigorously prove that the order of an integer $a$ modulo $p$ divides $p-1$, where $p$ is a prime and $a$ is an integer not divisible by $p$, we will utilize Fermat's Little Theorem and some properties of groups. Here's the step-by-step proof:

### Given:

1. $p$ is a prime number.
2. $a$ is an integer such that $gcd(a, p) = 1$ (i.e., $a$ is not divisible by $p$).
3. Fermat's Little Theorem states that $a^{p-1} \equiv 1 \pmod{p}$.

### Objective:

Prove that the order of $a \bmod p$ divides $p-1$.

### Proof:

Let's denote the order of $a \bmod p$ as $d$. By definition, $d$ is the smallest positive integer such that $a^d \equiv 1 \pmod{p}$.

1. **Fermat's Little Theorem**: It tells us that $a^{p-1} \equiv 1 \pmod{p}$.

2. **Existence of Order**: Since $a^d \equiv 1 \pmod{p}$, and $d$ is the smallest such positive integer, we know that $d$ exists and is a positive integer.

3. **Division of Powers**: We know that $a^{p-1} \equiv 1 \pmod{p}$. If we divide the exponent $p-1$ by $d$, we can express $p-1$ as $qd + r$, where $q$ and $r$ are integers with $0 \leq r < d$ (by the division algorithm).

   Therefore, we can rewrite $a^{p-1}$ as $a^{qd + r}$.

4. **Modular Exponentiation**: Using the property of exponentiation, we have $a^{qd + r} = (a^d)^q \cdot a^r$. Given that $a^d \equiv 1 \pmod{p}$, this reduces to $a^r$.

5. **Substituting Back**: Since $a^{p-1} \equiv 1 \pmod{p}$ and $a^{p-1} = a^r$, we have $a^r \equiv 1 \pmod{p}$.

6. **Minimality of Order**: Recall that $d$ is the smallest positive integer for which $a^d \equiv 1 \pmod{p}$. Since $r < d$ and $a^r \equiv 1 \pmod{p}$, the only way this can hold true is if $r = 0$.

7. **Conclusion**: As $r = 0$, $p-1 = qd$ or $p-1 = q \cdot \text{order of } a \bmod p$. This means that the order of $a \bmod p$ (which is $d$) divides $p-1$.

### Summary

This proof leverages the foundational principles of modular arithmetic and the properties of groups in number theory. It elegantly shows that the order of an element in a multiplicative group modulo a prime number is a divisor of $p-1$, highlighting the intricate structure and symmetries inherent in modular systems.


# Note: 
- Modular numbers are closed under addition and multiplication and form an [[ideal]]

# Proof:  that if p and q are primes and p divides 2^q - 1, then p must be congruent to 1 mod q 

---

$$
\textbf{Step 1: Fermat's Little Theorem}
$$
The theorem of Fermat, subtle yet powerful, asserts that for a prime number $p$ and any integer $a$ not divisible by $p$, the following truth holds:
$$
a^{p-1} \equiv 1 \pmod{p}
$$

$$
\textbf{Step 2: \( p \) divides \( 2^q - 1 \)}
$$
Given the premise that $p$ divides $2^q - 1$, we express this in the language of congruences as:
$$
2^q \equiv 1 \pmod{p}
$$

$$
\textbf{Step 3: Applying Fermat's Little Theorem to 2 mod \( p \)}
$$
As $p$, a prime, does not share a factor with 2, we apply Fermat's theorem to 2, revealing that:
$$
2^{p-1} \equiv 1 \pmod{p}
$$

$$
\textbf{Step 4: Order of 2 mod \( p \)}
$$
We define the order of 2 modulo $p$, denoted $\text{ord}_p(2)$, as the smallest positive integer $k$ such that $2^k \equiv 1 \pmod{p}$. From our premises and Fermat's insight, it follows that:
1. $2^q \equiv 1 \pmod{p}$ implies $\text{ord}_p(2)$ divides $q$.
2. $2^{p-1} \equiv 1 \pmod{p}$ implies $\text{ord}_p(2)$ divides $p-1$.

$$
\textbf{Step 5: Conclusion}
$$
Should $\text{ord}_p(2)$ be 1, it would lead us to $2 \equiv 1 \pmod{p}$, an impossibility for a prime $p$ greater than 2. Thus, $\text{ord}_p(2)$ must equal $q$. Consequently, $q$ divides $p-1$, or in the formal tongue of mathematics:
$$
p \equiv 1 \pmod{q}
$$

---

Thus, we have elegantly and rigorously demonstrated that if $p$ and $q$ are primes and $p$ divides $2^q - 1$, then indeed $p$ must be congruent to 1 modulo $q$.

# Conditions of Fermat Primes where they are not prime
Fermat primes are a special class of prime numbers, named after the French mathematician Pierre de Fermat. They are of the form $F_n = 2^{2^n} + 1$, where $n$ is a non-negative integer. A Fermat number $F_n$ is prime if and only if it cannot be factored into smaller integers greater than 1. 

To understand the conditions under which Fermat numbers are not prime, we need to consider the factors that could potentially divide $F_n$. A Fermat number $F_n$ is not prime if there exists a positive integer $a$ such that $1 < a < F_n$ and $a$ divides $F_n$.

One approach to proving the non-primality of certain Fermat numbers is to find specific factors. For instance, Euler showed that $F_5 = 2^{2^5} + 1 = 4294967297$ is not prime by finding that it is divisible by 641. 

Let's dive into Euler's proof:

1. **Euler's Insight**: Euler noted that $641 = 5 \times 2^7 + 1$.

2. **Modular Arithmetic**:
   - Consider $2^{2^5} = 2^{32}$. By modular arithmetic, we can show that $2^{32} \equiv -1 \pmod{641}$.
   - Similarly, we can show that $5 \times 2^7 \equiv -1 \pmod{641}$.

3. **Combining Results**: Since both $2^{32}$ and $5 \times 2^7$ are congruent to $-1$ modulo 641, we can combine them to find that $2^{32} + 1$ is divisible by $641$. Thus, $641$ divides $F_5$, proving that $F_5$ is not a prime number.

This proof is a classic example of using modular arithmetic and clever insight to establish the non-primality of a Fermat number. It should be noted that not all Fermat numbers have known factors, and determining the primality of Fermat numbers for large $n$ remains a challenging problem in number theory.

# if $n$ has an odd factor, then a Fermat number $F_n = 2^{2^n} + 1$ is not prime

The observation that if $n$ has an odd factor, then a Fermat number $F_n = 2^{2^n} + 1$ is not prime is indeed a critical insight in number theory. To understand and prove this, we first need to establish some preliminary facts and use the concept of modular arithmetic.

### Preliminary Fact
For any integer $a$ and odd integer $b$, the following holds true:
$$ a^{2b} \equiv 1 \pmod{a^2 + 1} $$
as long as $a^2 + 1$ is not divisible by 2 (which is true when $a$ is even).

### Proof
Let's now apply this to Fermat numbers and show that if $n$ has an odd factor, $F_n$ is not prime.

1. **Assumption**: Suppose $n = km$ where $k > 1$ is the smallest odd factor of $n$.

2. **Fermat Number Representation**:
   We express $F_n$ as:
   $$ F_n = 2^{2^n} + 1 = 2^{2^{km}} + 1 $$

3. **Use of Preliminary Fact**:
   Taking $a = 2^{2^m}$, we have $a^2 = 2^{2^{m+1}}$, and thus:
   $$ a^{2k} = 2^{2^{m+1}k} = 2^{2^n} $$
   Since $k$ is odd, from our preliminary fact, we know:
   $$ a^{2k} \equiv 1 \pmod{a^2 + 1} $$
   or,
   $$ 2^{2^n} \equiv 1 \pmod{2^{2^{m+1}} + 1} $$

4. **Conclusion**:
   From the congruence, $2^{2^{m+1}} + 1$ divides $2^{2^n} - 1$, which is $F_n - 2$. Hence, if $2^{2^{m+1}} + 1 < F_n$, it is a non-trivial factor of $F_n$, proving that $F_n$ is not prime.

### Key Insight
The crucial part of this proof is realizing that the presence of an odd factor in $n$ allows us to construct a non-trivial factor of $F_n$, thus proving that $F_n$ is composite. This method elegantly combines the properties of powers of two and the characteristics of Fermat numbers to reach a profound conclusion in number theory.

# Squares, mods and primes

## Proof 1: 
Suppose $a^2 \equiv b^2 \mod m$.

Question: whether this implies $a \equiv b \mod m$, and it provides a counterexample when $m = 8$ and a validation when $m$ is prime.

However, when $m$ is prime, the situation changes. The property of a prime modulus ensures that if $a^2 \equiv b^2 \mod m$, then it must be the case that $a \equiv b \mod m$ or $a \equiv -b \mod m$. This is because the difference of squares factorization $a^2 - b^2 = (a + b)(a - b)$ reveals that $m$ must divide at least one of the factors if it divides their product. Since $m$ is prime, it cannot divide a product unless it divides one of the factors. If $m$ divides $a + b$, then $a \equiv -b \mod m$, and if $m$ divides $a - b$, then $a \equiv b \mod m$. This is a consequence of the fact that in a field (which is what the integers modulo a prime number form), every non-zero element has a unique inverse.

Let's formalize the proof of the statement when $m$ is prime:

1. Start with the assumption $a^2 \equiv b^2 \mod m$, which implies that $m | (a^2 - b^2)$.
2. Since $a^2 - b^2 = (a + b)(a - b)$, it follows that $m | (a + b)(a - b)$.
3. In a field, if the product of two numbers is zero, then at least one of the numbers must be zero. Therefore, $m | (a + b)$ or $m | (a - b)$.
4. If $m | (a + b)$, then $a \equiv -b \mod m$. If $m | (a - b)$, then $a \equiv b \mod m$.
5. Therefore, $a^2 \equiv b^2 \mod m$ implies that $a \equiv \pm b \mod m$, when $m$ is prime.

This conclusion elegantly encapsulates the essence of congruences when interfaced with the prime characteristic of modulus. It is an illustration of the rich structure that primes impart to the number system, and the reason why they are fundamental in many areas of mathematics, including number theory and cryptography.

## Proof 2:
To address the heart of the matter, we must indeed examine the claim with mathematical scrutiny. The statement:

Given: $$a^2 \equiv b^2 \mod m^2$$

To verify: Does this imply $$a \equiv \pm b \mod m$$?

To disprove the implication, it is sufficient to find a counterexample where $$a^2 \equiv b^2 \mod m^2$$ holds, but $$a \not\equiv \pm b \mod m$$.

Let us construct such an example. Consider the case where $a = m + 1$ and $b = m - 1$, with $m > 2$. Now, let's compute $a^2$ and $b^2$ modulo $m^2$.

For $a^2$:
$$
a^2 = (m + 1)^2 = m^2 + 2m + 1
$$
And modulo $m^2$, we get:
$$
a^2 \mod m^2 = (m^2 + 2m + 1) \mod m^2 = 2m + 1
$$

For $b^2$:
$$
b^2 = (m - 1)^2 = m^2 - 2m + 1
$$
And modulo $m^2$, we have:
$$
b^2 \mod m^2 = (m^2 - 2m + 1) \mod m^2 = -2m + 1
$$

Since $m^2$ divides both $m^2 + 2m + 1 - 2m - 1$ and $m^2 - 2m + 1 + 2m - 1$, it follows that:
$$
a^2 \equiv b^2 \mod m^2
$$

However, when we consider $a$ and $b$ modulo $m$:
$$
a \mod m = (m + 1) \mod m = 1
$$
$$
b \mod m = (m - 1) \mod m = -1 \text{ or } m - 1 \text{ (since } -1 \equiv m - 1 \mod m\text{)}
$$

Clearly, $a \not\equiv b \mod m$ since $1 \not\equiv -1 \mod m$ for $m > 2$. Similarly, $a \not\equiv -b \mod m$ since $1 \not\equiv m - 1 \mod m$ unless $m = 2$.

Our counterexample demonstrates that even though $a^2 \equiv b^2 \mod m^2$, it does not necessarily follow that $a \equiv \pm b \mod m$. This counterexample refutes the implication, thereby preserving the integrity of our mathematical universe, where claims must stand the rigorous test of logic and proof.