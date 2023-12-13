# Advantages of having a congruence modulo p, where p is a prime

1. **No Zero Divisors**: In a field, which $\mathbb{Z}_p$ (integers modulo $p$) is when $p$ is prime, the statement $ab \equiv 0 \mod p$ implies that either $a \equiv 0 \mod p$ or $b \equiv 0 \mod p$. This is a direct consequence of the definition of a prime number, which states that a prime number has no divisors other than 1 and itself. This property is fundamental because it ensures that the cancellation law holds, which is not the case in rings with zero divisors.

2. **Inverses Exist**: For any non-zero element $a$ in $\mathbb{Z}_p$, there exists an inverse $b$ such that $ab \equiv 1 \mod p$. This is a result of Bézout's Lemma, which asserts that if $a$ and $p$ are coprime, there exist integers $x$ and $y$ such that $ax + py = 1$. Taking this equation modulo $p$ gives us the existence of a multiplicative inverse for $a$ modulo $p$.

3. **Polynomials of Degree $n$ Have $n$ Roots**: This statement is a simplified version of the Fundamental Theorem of Algebra, which applies to polynomials over the complex numbers. However, in $\mathbb{Z}_p$, it is not always true that a polynomial of degree $n$ will have $n$ roots. The correct statement is that a polynomial of degree $n$ cannot have more than $n$ roots in $\mathbb{Z}_p$. For example, the polynomial $x^2 - 1$ has $2$ roots modulo $8$, which is not a prime, but modulo a prime like $7$, it will have exactly $2$ roots.

4. **Fermat's Little Theorem**: For any integer $a$ not divisible by $p$, Fermat's Little Theorem states that $a^{p-1} \equiv 1 \mod p$. This is a fundamental result in number theory and is often used to demonstrate that a number is not prime if it fails to satisfy this congruence.

5. **Primitive Roots Exist**: A primitive root modulo $p$ is an integer $g$ such that the powers of $g$ generate all non-zero elements of $\mathbb{Z}_p$. The existence of primitive roots is guaranteed for prime moduli, and this is a result of the group structure of the multiplicative group of $\mathbb{Z}_p$, which is cyclic when $p$ is prime.

In summary, when $p$ is prime, $\mathbb{Z}_p$ forms a field, which ensures no zero divisors, the existence of inverses for every non-zero element, and a cyclic multiplicative group structure. These properties are central to the algebraic structure of $\mathbb{Z}_p$ and have far-reaching implications in number theory, cryptography, and algebraic geometry. 

# Polynomial Roots Modulo Prime

When dealing with polynomials in modular arithmetic, specifically modulo a prime number $p$, it's important to understand why $p$ must be a prime number to make certain statements about the number of roots of a polynomial of degree $n$ modulo $p$. Let's explore this concept.

## Polynomial Roots Modulo Prime

Given a polynomial $f(x)$ of degree $n$ with coefficients in the integers, we can consider its roots modulo a prime number $p$. This means we are looking for solutions to the equation $f(x) \equiv 0 \pmod{p}$, where $x$ and $p$ are integers.

## Why Does $p$ Need to Be Prime?

The statement that a polynomial of degree $n$ (mod $p$) has at most $n$ roots relies on the fundamental property of prime numbers. Let's break down the key reasons:

### 1. Euclidean Division

For integers, division is not always straightforward. However, when we work with a prime number $p$, Euclidean division is well-defined. This means that for any integer $a$, there exist unique integers $q$ and $r$ such that $a = qp + r$ and $0 \leq r < p$. This unique division property plays a crucial role when working with modular arithmetic.

### 2. Modular Arithmetic Properties

When we take congruences modulo a prime $p$, several properties emerge:

   a. **Unique Inverses**: Every non-zero integer has a unique multiplicative inverse modulo $p$ if $p$ is prime. This allows us to solve linear congruences with unique solutions.

   b. **Cancellation Property**: If $ab \equiv ac \pmod{p}$, then $b \equiv c \pmod{p}$ as long as $a$ is not congruent to $0$ (mod $p$). This follows from the fact that we can cancel $a$ from both sides of the congruence.

### 3. Polynomial Factorization

In the ring of integers modulo $p$ (denoted as $\mathbb{Z}_p$), polynomial factorization behaves differently compared to the ring of integers. Over $\mathbb{Z}_p$, polynomials can factor uniquely into irreducible factors. Irreducible polynomials in $\mathbb{Z}_p[x]$ correspond to linear factors in $\mathbb{Z}_p$.

### 4. The Fundamental Theorem of Algebra

The statement that a polynomial of degree $n$ has at most $n$ roots is a consequence of the Fundamental Theorem of Algebra. Over the complex numbers, this theorem guarantees that a polynomial of degree $n$ has exactly $n$ complex roots (counting multiplicity). However, in modular arithmetic, we are dealing with a different algebraic structure.

### 5. Field Properties

To make statements about the number of roots of a polynomial, we need a field structure. **The ring of integers modulo a prime $p$, denoted as $\mathbb{Z}_p$, is a field when $p$ is prime. A field has well-defined addition, subtraction, multiplication, and division (excluding division by zero)**. This field structure allows us to apply properties such as the cancellation property, which is crucial when working with polynomial equations.

# Roots of the polynomial $x^p - x$ mod p
The polynomial $x^p - x$ over the finite field $\mathbb{F}_p$, where $p$ is a prime number, is interesting because it relates to Fermat's Little Theorem. According to the theorem, for any integer $a$, $a^p \equiv a \ (\text{mod} \ p)$. This implies that every element $a$ in $\mathbb{F}_p$ is a root of the polynomial $x^p - x$, as substituting $a$ for $x$ yields $a^p - a \equiv 0 \ (\text{mod} \ p)$.

To see why these are all the roots, consider the factorization of $x^p - x$ over $\mathbb{F}_p$:

$$
x^p - x = x(x-1)(x-2)\ldots(x-(p-1)).
$$

This factorization is possible because the polynomial is separable, which means its derivative $px^{p-1} - 1$ is relatively prime to $x^p - x$ for $p > 2$, ensuring distinct roots. For $p = 2$, the polynomial is $x^2 - x = x(x - 1)$, which also has distinct roots.

Moreover, by the fundamental theorem of algebra, a polynomial of degree $n$ has at most $n$ roots in a field. Here, since $p$ is the degree of our polynomial, there cannot be more than $p$ roots in $\mathbb{F}_p$. As we have already found $p$ roots corresponding to the elements of $\mathbb{F}_p$, these must be all the roots.

It is also worth exploring whether $x^p - x$ has any roots outside $\mathbb{F}_p$. Could there exist an element $b \notin \mathbb{F}_p$ such that $b^p - b \equiv 0 \ (\text{mod} \ p)$? The extension of Fermat's Little Theorem to non-prime moduli and the behavior of polynomials in ring extensions of $\mathbb{F}_p$ might provide further insight.

# Expansion of $x^p - x$ in a finite field of order $p$
$x^p - x$ in a finite field of order $p$, where $p$ is a prime number, and its factorization. The polynomial is expressed as a product of its linear factors and then expanded using the binomial theorem. The coefficients of the expanded form are related to the sums of powers of the roots, and these are the elementary symmetric polynomials in the roots.

Given the polynomial $x^p - x$, which can be factored as

$$
x(x-1)(x-2)\ldots(x-(p-1)),
$$

the expanded form will have terms $x^p$, $-\sigma_1 x^{p-1}$, $\sigma_2 x^{p-2}$, ..., $(-1)^p \sigma_p$, where $\sigma_k$ denotes the $k$-th elementary symmetric polynomial in the roots $0, 1, 2, ..., p-1$ of $x^p - x$. Specifically, $\sigma_1$ is the sum of the roots, $\sigma_2$ is the sum of the products of the roots taken two at a time, and so on, up to $\sigma_p$ which is the product of all roots.

# Expansion of $x^p - x$ in a finite field of order $p$ leading to a proof of Wilsons' Theorem
Wilson's Theorem states that for any prime number $p$, $(p-1)!\equiv -1 \ (\text{mod} \ p)$. To see how the expansion of $x^p - x$ can lead to a proof of Wilson's Theorem, consider the factorization of $x^p - x$ in the finite field $\mathbb{F}_p$:

$$
x^p - x = x(x-1)(x-2)\ldots(x-(p-1)).
$$

Now, if we set $x=0$ in this factorization, we get $0^p - 0 = 0$, which is trivial. The interesting case is setting $x = p$, which gives us:

$$
p^p - p = p(p-1)(p-2)\ldots(1) \equiv 0 \ (\text{mod} \ p).
$$

Since $p$ is a prime, we can cancel $p$ from each term on the left-hand side, which is legitimate in a field, and we are left with:

$$
(p-1)(p-2)\ldots(1) \equiv 0 \ (\text{mod} \ p).
$$

However, this expression represents $(p-1)!$, and we know that for any prime $p$, the numbers $1, 2, ..., p-1$ are all non-zero and have multiplicative inverses modulo $p$. Therefore, each term in the product $(p-2)\ldots(1)$ has an inverse modulo $p$ except for the term $p-1$ itself, which is its own inverse since $(p-1)^2 \equiv 1 \ (\text{mod} \ p)$. This implies that the product of all these terms is congruent to $-1$ modulo $p$, hence:

$$
(p-1)! \equiv -1 \ (\text{mod} \ p),
$$

which is Wilson's Theorem. 

This is not the standard proof of Wilson's Theorem but demonstrates the deep interplay between different areas of number theory and how expanding a polynomial in a finite field can reveal interesting properties about numbers and their relationships.
