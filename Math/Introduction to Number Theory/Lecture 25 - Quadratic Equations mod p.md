## Quadratic Equations modulo p

In this mathematical explanation, we will explore quadratic equations modulo a prime number $p$. Specifically, we will discuss the solutions to quadratic equations of the form $ax^2 + bx + c \equiv 0 \pmod{p}$, where $p$ is a prime number.

### Background:

Before delving into the solutions, let's establish some essential concepts:

1. **Modulo Operation**: When we express an equation as $ax^2 + bx + c \equiv 0 \pmod{p}$, we are working within the framework of modular arithmetic. This means that we are considering remainders when dividing by $p$. In modular arithmetic, two numbers are considered equivalent if they have the same remainder when divided by $p$.

2. **Quadratic Residues**: In the context of modular arithmetic, a quadratic residue modulo $p$ is an integer $a$ such that there exists an integer $x$ satisfying $x^2 \equiv a \pmod{p}$. Quadratic residues are essential for solving quadratic equations modulo $p$.

### Solutions to Quadratic Equations modulo p:

Now, let's discuss the solutions to quadratic equations of the form $ax^2 + bx + c \equiv 0 \pmod{p}$, where $a$, $b$, and $c$ are integers, and $p$ is a prime number.

1. **Discriminant**: The discriminant of the quadratic equation $ax^2 + bx + c \equiv 0 \pmod{p}$ is given by $\Delta = b^2 - 4ac$. The nature of the solutions depends on the value of $\Delta$ modulo $p$.

2. **Case 1: Quadratic Residue**: If $\Delta$ is a quadratic residue modulo $p$ (i.e., there exists an integer $x$ such that $x^2 \equiv \Delta \pmod{p}$), then the equation has two distinct solutions modulo $p$. These solutions are given by the quadratic formula:

   $$
   x \equiv \frac{-b \pm \sqrt{\Delta}}{2a} \pmod{p}
   $$

   Here, $\sqrt{\Delta}$ represents any integer whose square is congruent to $\Delta$ modulo $p$.

3. **Case 2: Quadratic Non-Residue**: If $\Delta$ is not a quadratic residue modulo $p$, then the equation has no solutions modulo $p$. In this case, the solutions lie outside the field of integers modulo $p$.

# Existence of a solution to quadratic congruences using Euler's Criterion

In this mathematical explanation, we will explore the existence of solutions to certain quadratic congruences using Euler's Criterion, a result from number theory. Specifically, we will examine whether the congruence $x^2 \equiv a \pmod{p}$ has solutions based on the value of $a$ and the prime modulus $p$.

### Euler's Criterion:

Euler's Criterion provides a condition for the existence of solutions to the congruence $x^2 \equiv a \pmod{p}$, where $a$ is an integer and $p$ is an odd prime. The criterion states:

**Euler's Criterion**: If $a$ is an integer and $p$ is an odd prime such that $a$ is not divisible by $p$, then the congruence $x^2 \equiv a \pmod{p}$ has a solution if and only if $a^{(p-1)/2} \equiv 1 \pmod{p}$.

Let's break down the implications of Euler's Criterion:

1. If $a$ is not divisible by $p$ and $a^{(p-1)/2} \equiv 1 \pmod{p}$, then there exists at least one solution $x$ to the congruence $x^2 \equiv a \pmod{p}$.

2. If $a$ is not divisible by $p$ and $a^{(p-1)/2} \not\equiv 1 \pmod{p}$, then the congruence $x^2 \equiv a \pmod{p}$ has no solutions.

# Proof of Euler's Criterion for Quadratic Congruences

In this mathematical proof, we will establish Euler's Criterion for quadratic congruences modulo an odd prime $p$. Euler's Criterion is a fundamental result in number theory and provides a condition for the existence of solutions to the congruence $x^2 \equiv a \pmod{p}$, where $a$ is an integer and $p$ is an odd prime.

### Euler's Criterion:

Euler's Criterion states that if $a$ is an integer and $p$ is an odd prime such that $a$ is not divisible by $p$, then the congruence $x^2 \equiv a \pmod{p}$ has a solution if and only if $a^{(p-1)/2} \equiv 1 \pmod{p}$.

### Proof:

#### Part 1: If $x^2 \equiv a \pmod{p}$ has a solution, then $a^{(p-1)/2} \equiv 1 \pmod{p}$.

Let's assume that there exists an integer $x$ such that $x^2 \equiv a \pmod{p}$. We want to show that $a^{(p-1)/2} \equiv 1 \pmod{p}$.

By Euler's Totient Theorem (a well-known result in number theory), for any integer $a$ that is not divisible by $p$, we have:

$$
a^{\phi(p)} \equiv 1 \pmod{p}
$$

Here, $\phi(p)$ is Euler's Totient Function, which gives the count of positive integers less than $p$ that are coprime to $p$. Since $p$ is prime, $\phi(p) = p - 1$. Substituting this into the theorem:

$$
a^{p-1} \equiv 1 \pmod{p}
$$

Now, we can express $(p-1)$ as twice some integer $k$ plus $1$ (since $p$ is odd):

$$
p-1 = 2k + 1
$$

Rearranging:

$$
2k = p-2
$$

Dividing both sides by $2$:

$$
k = \frac{p-2}{2}
$$

Now, we can rewrite $a^{p-1}$ as:

$$
a^{p-1} = a^{2k + 1}
$$

Using the properties of exponents:

$$
a^{2k + 1} = a^{2k} \cdot a^1
$$

Since $a^{2k} \equiv 1 \pmod{p}$ (by the Totient Theorem), we have:

$$
a^{p-1} \equiv a \pmod{p}
$$

Now, we can substitute this into our original assumption that $x^2 \equiv a \pmod{p}$:

$$
x^2 \equiv a^{p-1} \equiv a \pmod{p}
$$

We have shown that if $x^2 \equiv a \pmod{p}$ has a solution, then $a^{(p-1)/2} \equiv 1 \pmod{p}$.

#### Part 2: If $a^{(p-1)/2} \equiv 1 \pmod{p}$, then $x^2 \equiv a \pmod{p}$ has a solution.

Now, let's prove the other direction. If $a^{(p-1)/2} \equiv 1 \pmod{p}$, we want to show that $x^2 \equiv a \pmod{p}$ has a solution.

We start with the assumption that $a^{(p-1)/2} \equiv 1 \pmod{p}$. This means that there exists an integer $k$ such that:

$$
a^{(p-1)/2} = 1 + kp
$$

Now, we can express this in terms of $a$:

$$
a^{(p-1)/2} = 1 + kp
$$

Raise both sides to the power of $2$:

$$
(a^{(p-1)/2})^2 = (1 + kp)^2
$$

Expand the right side:

$$
a^{p-1} = 1 + 2kp + k^2p^2
$$

Since we are working modulo $p$, all multiples of $p$ vanish:

$$
a^{p-1} \equiv 1 \pmod{p}
$$

Now, we can apply Euler's Totient Theorem in the reverse direction:

$$
a^{(p-1)/2} \equiv \pm 1 \pmod{p}
$$

Since we are given that $a^{(p-1)/2} \equiv 1 \pmod{p}$, we have:

$$
a^{(p-1)/2} \equiv 1 \pmod{p}
$$

Now, let $k$ be the integer such that:

$$
a^{(p-1)/2} = 1 + kp
$$

This implies:

$$
a^{(p-1)/2} - 1 = kp
$$

So, we can write:

$$
a^{(p-1)/2} - 1 \equiv 0 \pmod{p}
$$

Now, let

's square both sides:

$$
(a^{(p-1)/2} - 1)^2 \equiv 0^2 \pmod{p}
$$

Expand the left side:

$$
(a^{(p-1)/2})^2 - 2a^{(p-1)/2} + 1 \equiv 0 \pmod{p}
$$

Now, use the fact that $a^{(p-1)/2} \equiv 1 \pmod{p}$:

$$
1 - 2 \cdot 1 + 1 \equiv 0 \pmod{p}
$$

Simplify:

$$
0 \equiv 0 \pmod{p}
$$

This shows that $x^2 \equiv a \pmod{p}$ has a solution.

### Conclusion:

We have successfully proven Euler's Criterion for quadratic congruences modulo an odd prime $p$. Euler's Criterion provides a powerful tool for determining the existence of solutions to quadratic congruences and plays a significant role in number theory and modular arithmetic.

# Berlekamp Polynomial Solver

In this mathematical explanation, we will explore the Berlekamp Polynomial Solver, a technique used in algebraic coding theory to find the minimal polynomial of a linear recurring sequence. The minimal polynomial is a fundamental concept in error-correcting codes, and the Berlekamp algorithm is a powerful tool to determine it.

### Background:

Before delving into the Berlekamp Polynomial Solver, let's establish some foundational concepts:

1. **Linear Recurring Sequence**: In coding theory, a linear recurring sequence is a sequence in which each term is a linear combination of the preceding terms. It is often used to represent the encoded message in error-correcting codes.

2. **Minimal Polynomial**: The minimal polynomial of a linear recurring sequence is the monic polynomial of lowest degree that has the sequence as a root. It is crucial in decoding the original message from the received, possibly corrupted, message.

### The Berlekamp Polynomial Solver:

The Berlekamp Polynomial Solver is an algorithm developed by Elwyn R. Berlekamp for finding the minimal polynomial of a linear recurring sequence. Here's how it works:

1. **Step 1 - Initialization**: Start with an empty list of polynomials and initialize a list of coefficients for the sequence.

2. **Step 2 - Berlekamp-Massey Algorithm**: Iterate through the coefficients of the sequence one by one. For each new coefficient, apply the Berlekamp-Massey algorithm to update the list of polynomials. The Berlekamp-Massey algorithm checks for the linear recurrence relation of the sequence.

3. **Step 3 - Minimal Polynomial**: Once all coefficients have been processed, the last polynomial in the list will be the minimal polynomial of the sequence.

### Implications and Curiosity:

- The Berlekamp Polynomial Solver is used in various error-correcting codes, including [[Reed-Solomon codes]], which are widely used in digital communication and data storage.

- Understanding the minimal polynomial is crucial for error correction because it allows for the reconstruction of the original message even in the presence of errors or noise.

- The algorithm is based on the mathematical properties of polynomials and linear algebra, making it a fundamental tool in [[coding theory]].

# **Cantor-Zassenhaus Theorem**:

The Cantor-Zassenhaus theorem is a fundamental result in algebraic number theory and polynomial factorization. It provides a method for factoring a polynomial over a finite field into irreducible factors. Let's delve into the theorem and its proof.

**Theorem** (Cantor-Zassenhaus Theorem):

Let $F_q$ be a finite field with $q$ elements, where $q$ is a prime power, and let $f(x)$ be a polynomial in $F_q[x]$ of degree $n$ with no multiple roots. Then, for any positive integer $d$ that divides $n$, the polynomial $f(x)$ can be factored uniquely into irreducible polynomials of degree $d$ in $F_q[x]$.

**Proof**:

1. We start by considering the [[field extension]] $K/F_q$, where $K$ is the [[splitting field ]]of $f(x)$ over $F_q$. Since $f(x)$ has no multiple roots, all its roots in $K$ are distinct.
  
2. Let $\alpha$ be one of the roots of $f(x)$ in $K$. By considering the minimal polynomial of $\alpha$ over $F_q$, denoted as $m_{\alpha}(x)$, we have $[F_q(\alpha):F_q] = \deg(m_{\alpha}(x)) = d$. This implies that the degree of the extension $[K:F_q(\alpha)]$ is $n/d$.

3. We can apply the following result: For any finite field extension $L/F_q$, there exists a unique monic irreducible polynomial of degree $k$ in $F_q[x]$ for each positive integer $k$ that divides $[L:F_q]$.

4. Applying this result to our situation, we conclude that there exists a unique monic irreducible polynomial of degree $d$ in $F_q[x]$ for each positive integer $d$ dividing $n$. Let's denote these irreducible polynomials as $g_1(x), g_2(x), \ldots, g_k(x)$, where $k = n/d$.

5. Now, we need to find the number of distinct irreducible factors of degree $d$ that appear in the factorization of $f(x)$. For this, we consider the factorization of $f(x)$ into irreducible polynomials over $K$:
   $$
   f(x) = (x - \alpha_1)(x - \alpha_2)\cdots(x - \alpha_n)
   $$

6. Each $\alpha_i$ is a root of $f(x)$, and since $f(x)$ has no multiple roots, all $\alpha_i$'s are distinct.

7. We can group these roots into sets of size $d$:
   $$
   \{(\alpha_1, \alpha_2, \ldots, \alpha_d), (\alpha_{d+1}, \alpha_{d+2}, \ldots, \alpha_{2d}), \ldots, (\alpha_{n-d+1}, \alpha_{n-d+2}, \ldots, \alpha_n)\}
   $$

8. Each of these sets corresponds to one of the irreducible factors $g_i(x)$. Since there are $k = n/d$ irreducible factors of degree $d$, we have found all the distinct irreducible factors of $f(x)$.

9. Therefore, we can conclude that the polynomial $f(x)$ factors uniquely into irreducible polynomials of degree $d$ in $F_q[x]$, where $d$ divides $n$.

This completes the proof of the Cantor-Zassenhaus theorem. It provides a systematic way to factorize a polynomial over a finite field into its irreducible components, which is a crucial step in many applications of algebraic number theory and cryptography.

# Finding Square Roots
**Finding Square Roots of Quadratic Equations mod p**:

In modular arithmetic, finding square roots of quadratic equations modulo a prime number $p$ is a common problem with applications in cryptography and number theory. Given a quadratic congruence of the form $x^2 \equiv a \pmod{p}$, where $a$ and $p$ are integers and $p$ is prime, we aim to find the solutions for $x$ modulo $p$. Let's explore the techniques to find square roots in such equations.

**Legendre Symbol**:

Before delving into finding square roots, let's introduce the Legendre symbol, denoted as $\left(\frac{a}{p}\right)$. For an integer $a$ and a prime $p$, it is defined as:

$$
\left(\frac{a}{p}\right) = 
\begin{cases}
1, & \text{if } a \text{ is a quadratic residue modulo } p \\
-1, & \text{if } a \text{ is a quadratic non-residue modulo } p \\
0, & \text{if } a \equiv 0 \pmod{p}
\end{cases}
$$

**Quadratic Residues and Non-Residues**:

1. Quadratic Residue: An integer $a$ is a quadratic residue modulo $p$ if there exists an integer $x$ such that $x^2 \equiv a \pmod{p}$. In this case, $x$ is called a square root of $a$ modulo $p$.

2. Quadratic Non-Residue: An integer $a$ is a quadratic non-residue modulo $p$ if there is no integer $x$ such that $x^2 \equiv a \pmod{p}$.

**Finding Square Roots**:

Now, let's discuss how to find square roots of $a$ modulo a prime $p$:

1. **Legendre Symbol Evaluation**: Compute $\left(\frac{a}{p}\right)$ using the Legendre symbol.

2. **Case 1: Legendre Symbol is 0**:
   - If $\left(\frac{a}{p}\right) = 0$, it means $a$ is divisible by $p$, and there is one solution: $x \equiv 0 \pmod{p}$.

3. **Case 2: Legendre Symbol is 1**:
   - If $\left(\frac{a}{p}\right) = 1$, it means $a$ is a quadratic residue modulo $p$, and there are two square roots modulo $p$.
   - Use the fact that if $x$ is a square root of $a$ modulo $p$, then $p - x$ is also a square root of $a$ modulo $p$. So, the two solutions are $x \equiv \pm \sqrt{a} \pmod{p}$.

4. **Case 3: Legendre Symbol is -1 (Quadratic Non-Residue)**:
   - If $\left(\frac{a}{p}\right) = -1$, it means $a$ is a quadratic non-residue modulo $p$, and there are no square roots modulo $p$.

**Example**:

Let's illustrate this with an example: Solve $x^2 \equiv 9 \pmod{13}$.

1. Compute $\left(\frac{9}{13}\right)$. It equals 1 since 9 is a quadratic residue modulo 13.

2. Since $\left(\frac{9}{13}\right) = 1$, there are two square roots modulo 13: $x \equiv \pm \sqrt{9} \pmod{13}$. Therefore, $x \equiv \pm 3 \pmod{13}$.

So, the solutions are $x \equiv 3 \pmod{13}$ and $x \equiv 10 \pmod{13}$.

**Inquisitive Questions**:

1. Are there efficient algorithms for finding square roots modulo a prime for large prime numbers, especially in cryptographic applications?

2. What is the significance of quadratic residues and non-residues in number theory, and how are they used in various mathematical applications?

3. How can we generalize the concept of finding square roots to higher degree polynomials modulo a prime?

4. Are there any connections between finding square roots modulo different primes, especially in the context of solving systems of modular equations?

Finding square roots modulo a prime is a foundational concept in modular arithmetic and has wide-ranging applications in number theory, cryptography, and algebraic structures. Understanding the properties of Legendre symbols and the techniques for finding square roots is essential in these domains.

# Example
To solve the congruence $x^2 \equiv 2 \pmod{41}$, follow these steps:

1. **Quadratic Residues Modulo 41**: Check if 2 is a quadratic residue modulo 41 by computing $a^{20} \pmod{41}$ for $a = 2$. Since $2^{20} \equiv 40 \pmod{41}$, 2 is not a quadratic residue modulo 41.

2. **Gaussian Integers Approach**: Since 2 is not a quadratic residue, the congruence has no solutions in the integers. Extend the search to Gaussian integers $\mathbb{Z}[i]$.

3. **Rewrite the Congruence**: Express the congruence as $x^2 - 2 \equiv 0 \pmod{41}$, which can be rewritten as $(x - \sqrt{2})(x + \sqrt{2}) \equiv 0 \pmod{41}$.

4. **Factorization in $\mathbb{Z}[i]$**: Factorize 41 in Gaussian integers as $41 = (1 + 6i)(1 - 6i)$.

5. **Solve in Two Cases**:
   - **Case 1**: If $(x - \sqrt{2})$ is divisible by $1 + 6i$ and $(x + \sqrt{2})$ is divisible by $1 - 6i$.
   - **Case 2**: If $(x - \sqrt{2})$ is divisible by $1 - 6i$ and $(x + \sqrt{2})$ is divisible by $1 + 6i$.

6. **Find Solutions in Gaussian Integers**:
   - In **Case 1**, find $x$ such that $x \equiv \sqrt{2} \pmod{1 + 6i}$.
   - In **Case 2**, find $x$ such that $x \equiv \sqrt{2} \pmod{1 - 6i}$.

The solutions in Gaussian integers are:
1. $x \equiv 12 + 5i \pmod{41}$,
2. $x \equiv 12 - 5i \pmod{41}$.