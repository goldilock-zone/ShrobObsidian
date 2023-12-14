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

# **Wolstenholme's Theorem**

Wolstenholme's theorem relates to the congruence properties of certain binomial coefficients. Specifically, it deals with the congruence of the numerator of the harmonic number:

$$
H_n = 1 + \frac{1}{2} + \frac{1}{3} + \ldots + \frac{1}{n}
$$

where $n$ is a positive integer.

**Theorem:** For any prime number $p > 3$, the following congruence relation holds:

$$
\binom{2p}{p} \equiv 2 \pmod{p^3}
$$

Here, $\binom{2p}{p}$ represents the binomial coefficient.

**Proof:**

1. **Lucas's Theorem:** To prove Wolstenholme's theorem, we first utilize Lucas's theorem, which states that for any prime $p$ and integers $a$ and $b$, the binomial coefficient $\binom{a}{b}$ is congruent to the product of binomial coefficients modulo $p$:

   $$
   \binom{a}{b} \equiv \binom{a_p}{b_p} \binom{a_q}{b_q} \pmod{p}
   $$

   where $a_p$ and $b_p$ are the base-$p$ representations of $a$ and $b$, respectively, and $a_q$ and $b_q$ are the base-$p$ representations of $a$ and $b$ with the base-$p$ digits removed.

2. **Applying Lucas's Theorem:** Let's apply Lucas's theorem to $\binom{2p}{p}$. The base-$p$ representations of $2p$ and $p$ are $2p = 2 \cdot p^1$ and $p = p^1$, respectively. Therefore:

   $$
   \binom{2p}{p} \equiv \binom{2}{1} \binom{2}{1} \pmod{p}
   $$

3. **Simplify Binomial Coefficients:** The binomial coefficients on the right can be simplified to $\binom{2}{1} = 2$.

4. **Applying the Congruence Relation:** We have established that $\binom{2p}{p} \equiv 2 \pmod{p}$.

5. **Finding the Second Congruence:** To proceed, we need to find the congruence modulo $p^3$. We can use the following expansion for $\binom{2p}{p}$:

   $$
   \binom{2p}{p} = \frac{(2p)(2p-1)(2p-2)\ldots(p+2)(p+1)}{p!}
   $$

6. **Dividing by $p^2$:** Observe that the numerator contains the product of consecutive integers from $2p$ down to $(p+1)$. Since $p$ is prime, none of these integers are divisible by $p^2$. Therefore, we can safely divide the numerator by $p^2$:

   $$
   \binom{2p}{p} \equiv \frac{(2p)(2p-1)(2p-2)\ldots(p+2)(p+1)}{p!} \equiv \frac{2p-1}{1} \cdot \frac{2p-2}{2} \cdot \frac{2p-3}{3} \ldots \frac{p+2}{p-1} \cdot \frac{p+1}{p} \pmod{p^3}
   $$

7. **Canceling Factors:** We notice that the fractions $\frac{2p-1}{1}, \frac{2p-2}{2}, \frac{2p-3}{3}, \ldots, \frac{p+2}{p-1}, \frac{p+1}{p}$ are all congruent to $-1 \pmod{p^2}$ because each numerator is one less than the denominator, and $p$ does not divide any of the denominators. Therefore:

   $$
   \binom{2p}{p} \equiv (-1)(-1)(-1)\ldots(-1) \equiv (-1)^{p-1} \pmod{p^2}
   $$

8. **Final Step:** Now, we have two congruence relations for $\binom{2p}{p}$:

   - $\binom{2p}{p} \equiv 2 \pmod{p}$ (from step 4)
   - $\binom{2p}{p} \equiv (-1)^{p-1} \pmod{p^2}$ (from step 7)

9. **Combining the Congruences:** To find the congruence modulo $p^3$, we can apply the Chinese Remainder Theorem (CRT) to combine the above congruences:

   - $x \equiv 2 \pmod{p}$
   - $x \equiv (-1)^{p-1} \pmod{p^2}$

   CRT yields:

   $$
   x \equiv 2p \cdot (-1)^{p-1} + (-1)^{p-1} \cdot 2 \pmod{p^3}
   $$

10. **Simplify and Conclude:** Simplifying this expression, we get:

    $$
    x \equiv 2p(-1)^{p-1} + 2(-1)^{p-1} \equiv 2((-1)^{p-1}(p+1)) \pmod{p^3}
    $$

    Since $p > 3$ is prime, $p$ is odd, and therefore $(-1)^{p-1} = 1$. Thus, we have:

    $$
    x \equiv 2(p+1) \pmod{p^3}
    $$

    This completes the proof of Wolstenholme's theorem.

**Remark:** Wolstenholme's theorem has important applications in number theory and the study of congruences involving binomial coefficients. It provides a deeper understanding of the properties of harmonic numbers and their relationships with prime numbers.

# Proof of a Weaker form of Wolstenholme's Theorem
 The proof is leveraging the properties of modular arithmetic in the context of prime numbers and appears to be aiming to show that the sum of reciprocals from $1$ to $p-1$ is divisible by $p$ when $p$ is a prime number greater than $2$.

Here is a structured proof of the statement based on the usual approach taken in number theory:

### Proof:

Consider the sum of reciprocals modulo a prime number $p$:

$$
S = 1 + \frac{1}{2} + \frac{1}{3} + \ldots + \frac{1}{p-1} \mod p.
$$

We want to show that the numerator of $S$ when expressed with a common denominator is divisible by $p$.

1. **Multiplicative Inverses Modulo p**:
   
   For each integer $a$ such that $1 \leq a \leq p-1$, there exists a unique integer $b$ such that $1 \leq b \leq p-1$ and $ab \equiv 1 \mod p$ because every non-zero element in a field has a multiplicative inverse, and the integers modulo a prime form a field.

2. **Pairing Inverses**:
   
   Each term $\frac{1}{k}$ for $k \in \{1, \ldots, p-1\}$ can be paired with its multiplicative inverse modulo $p$. If $k$ is its own inverse (which can only happen when $k \equiv -1 \mod p$ or $k \equiv 1 \mod p$), then it counts as being paired with itself.

3. **Expression of S**:
   
   When we sum these terms, we can group them into pairs whose product is $1$ modulo $p$. The only terms that cannot be paired with a distinct element are $1$ and $p-1$ since $1 \cdot 1 \equiv 1 \mod p$ and $(p-1)(p-1) \equiv 1 \mod p$. Hence, we can rewrite the sum as:
   $$
   S \equiv 1 + (p-1) + \text{sum of other pairs} \equiv 0 \mod p.
   $$

4. **Using the Property of S**:
   
   The sum of all pairs excluding $1$ and $p-1$ will also be congruent to $0$ modulo $p$ because they are sums of products of inverses which are congruent to $1$ modulo $p$.

5. **Conclusion**:
   
   Since $S$ is a sum of integers each of which is congruent to $1$ modulo $p$, and there are $p-1$ such integers, $S$ is congruent to $p-1$ modulo $p$, which is congruent to $-1$ modulo $p$. Hence, $S$ is divisible by $p$ in the sense that when all terms of $S$ are brought to a common denominator, the numerator will be a multiple of $p$.

This proof strategy relies on the fact that in the ring of integers modulo $p$, every element except $0$ has a multiplicative inverse. It also uses the concept that the sum of all elements in this field is $0$ except for the special cases where the elements are their own inverses. The notation and structure used in this proof are standard for a rigorous mathematical argument.

# $f(x) \equiv 0 \mod p$ and its solutions

To address the problem given $f(x) \equiv 0 \mod p$, we must apply concepts from number theory, particularly those dealing with congruences and modular arithmetic. The prime number $p$ is the modulus for our congruences.

1. **Existence of Solutions:**
    - The existence of solutions to the congruence $f(x) \equiv 0 \mod p$ is guaranteed if $f(x)$ is a polynomial with integer coefficients. This is because the polynomial can be evaluated at all elements of $\mathbb{Z}/p\mathbb{Z}$, the set of integers modulo $p$, and for each such evaluation, the result will be an element of $\mathbb{Z}/p\mathbb{Z}$. If $f(x)$ has a degree $n$, then by the Factor Theorem for polynomials over a field, there are at most $n$ distinct solutions modulo $p$.

2. **Number of Solutions:**
    - The number of solutions can be determined using the structure of $\mathbb{Z}/p\mathbb{Z}$ as a finite field when $p$ is prime. A non-zero polynomial $f(x)$ of degree $n$ over a field cannot have more than $n$ roots unless it is the zero polynomial (which is congruent to $0$ for all $x$). Therefore, there are at most $n$ solutions modulo $p$.

3. **Finding the Solutions:**
    - To find the actual solutions, one would typically factor $f(x)$ over the field $\mathbb{Z}/p\mathbb{Z}$. If $f(x)$ can be factored into linear factors, then the solutions are the roots of those linear factors. However, factoring polynomials over finite fields can be non-trivial and may require algorithms such as the Berlekamp algorithm or the Cantor–Zassenhaus algorithm.

**Proof and Theorems:**

- **Factor Theorem**: If $f(x)$ is a polynomial over a field and $a$ is a root of $f(x)$, then $(x-a)$ is a factor of $f(x)$.

- **Fermat's Little Theorem**: For a prime $p$ and an integer $a$ not divisible by $p$, $a^{p-1} \equiv 1 \mod p$. This theorem is often used to reduce the powers of integers modulo $p$ and is helpful in polynomial factorization.

- **Fundamental Theorem of Algebra**: Every non-zero, single-variable, degree $n$ polynomial with complex coefficients has, counted with multiplicity, exactly $n$ complex roots. This theorem extends to finite fields for the number of distinct roots.

For an explicit example, consider the polynomial $f(x) = x^2 - 1$. We want to solve $f(x) \equiv 0 \mod p$. We can factor $f(x)$ as $(x-1)(x+1)$, so the solutions to $f(x) \equiv 0 \mod p$ are $x \equiv 1 \mod p$ and $x \equiv -1 \mod p$ or equivalently $x \equiv p-1 \mod p$.

This is a simple case, and generally, for higher degree polynomials or those that do not factor easily, more sophisticated techniques would be necessary.

To proceed with a specific $f(x)$, please provide the explicit form of the polynomial.

#  $x^p - x$ is sparse

To determine how the polynomial $x^p - x$ is sparse, we need to consider its structure and properties.

**Definition**: A polynomial is considered sparse if it has a relatively small number of non-zero coefficients compared to its degree.

In the given polynomial $x^p - x$, the highest power of $x$ is $p$, which makes it a polynomial of degree $p$. To analyze its sparsity, we must examine its coefficients.

**Coefficient Analysis**:
1. The coefficient of $x^p$ is 1.
2. The coefficient of $x$ is -1.
3. All other coefficients are 0.

Now, let's consider the degree and the number of non-zero coefficients:
- The degree of the polynomial is $p$.
- There are only two non-zero coefficients, which are 1 and -1.

Given that the polynomial has a degree of $p$ but only two non-zero coefficients, it can be observed that as $p$ increases, the ratio of non-zero coefficients to the degree decreases significantly. This behavior is indicative of a sparse polynomial.

To summarize, the polynomial $x^p - x$ is sparse because it has a relatively small number of non-zero coefficients (two) compared to its degree $p$. Further exploration may reveal additional insights into its sparsity based on different values of $p$.

# GCD of a sparse polynomial
To factorize and find the greatest common divisor (GCD) of a sparse polynomial, we can employ techniques based on polynomial factorization and GCD computation. Let's consider these processes separately:

**Factorization of a Sparse Polynomial**:

Factorization of a sparse polynomial involves expressing it as a product of irreducible factors. We can utilize the following theorem:

**Theorem**: Every polynomial of degree greater than zero can be factored into a product of irreducible polynomials over a field.

The process of factorization typically involves finding the roots of the polynomial and expressing it as a product of linear factors and irreducible factors corresponding to higher-degree roots.

1. **Roots and Linear Factors**:
   - Find the roots of the sparse polynomial by solving the equation $P(x) = 0$, where $P(x)$ represents the polynomial.
   - Express the polynomial as a product of linear factors corresponding to its roots.

2. **Irreducible Factors**:
   - If there are any remaining factors after expressing the polynomial as a product of linear factors, these are the irreducible factors.

**Finding the GCD of Sparse Polynomials**:

To find the GCD of two sparse polynomials, we can use the Euclidean algorithm for polynomial GCD computation. This algorithm is based on polynomial division and utilizes the following theorem:

**Theorem**: If $A(x)$ and $B(x)$ are two polynomials over a field, then their GCD $D(x)$ is the unique monic polynomial of highest degree that divides both $A(x)$ and $B(x)$.

The Euclidean algorithm involves repeated polynomial divisions until the remainder becomes zero. The GCD is the polynomial obtained at this point.

1. **Polynomial Division**:
   - Use polynomial division to find the quotient $Q(x)$ and remainder $R(x)$ when dividing the first polynomial by the second: $A(x) = B(x)Q(x) + R(x)$.

2. **Update Polynomials**:
   - Set $A(x)$ to be the divisor, and $B(x)$ to be the remainder from the previous division.
   - Repeat the polynomial division until the remainder is zero.

3. **GCD Determination**:
   - The GCD is the non-zero polynomial obtained in the final step.

In summary, factorizing and finding the GCD of sparse polynomials involves techniques such as polynomial factorization based on roots and irreducible factors, as well as the Euclidean algorithm for GCD computation. The specific characteristics of sparse polynomials may impact the efficiency of these processes, and further exploration can reveal their computational properties.

# Discussion on the factorization and gcd of $x^p - x$ 
The degree of the polynomial $x^p - x$ over the field $\mathbb{Z}/p\mathbb{Z}$, where $p$ is a prime, is $p$. By Fermat's Little Theorem, for any integer $a$ that is not divisible by $p$, $a^p \equiv a \mod p$. Hence, for every element $a$ in $\mathbb{Z}/p\mathbb{Z}$, $a^p - a \equiv 0 \mod p$. Consequently, $x^p - x$ vanishes for all $x$ in $\mathbb{Z}/p\mathbb{Z}$, and since there are $p$ elements in $\mathbb{Z}/p\mathbb{Z}$, $x^p - x$ can be expressed as the product of all linear factors $x - a$, where $a$ ranges over all elements of $\mathbb{Z}/p\mathbb{Z}$. This demonstrates that $x^p - x$ is a multiple of every linear polynomial $x - a$ in $\mathbb{Z}/p\mathbb{Z}$.

For the computation of the greatest common divisor (gcd) of $x^p - x$ and another polynomial $f(x)$ in $\mathbb{Z}/p\mathbb{Z}$, one may employ the Euclidean Algorithm. The gcd of $x^p - x$ and $f(x)$ reveals the roots of $f(x)$ in the field $\mathbb{Z}/p\mathbb{Z}$, corresponding to the shared factors. The gcd computation can be expedited if $f(x)$ is sparse, meaning most of its coefficients are zero, allowing for an optimized algorithmic approach.

Considering sparse polynomials, they are characterized by having a few non-zero terms. Their sparsity can be leveraged to improve the efficiency of polynomial operations, such as multiplication or finding gcd, especially within the structure of a finite field.

The Russian Peasant Method, historically used for multiplication, is an algorithm predicated on the binary representation of numbers and can be adapted for efficient exponentiation in modular arithmetic, an operation necessary for computations in finite fields. This method can be particularly useful when applied to polynomials in the context of $\mathbb{Z}/p\mathbb{Z}$, where exponentiation modulo $p$ is a common task.

Applying these principles and methods in finite field arithmetic requires an understanding of the underlying algebraic structures. For instance, the Euclidean Algorithm's application to polynomials in $\mathbb{Z}/p\mathbb{Z}$ is grounded in the Division Algorithm, which guarantees the existence of a quotient and remainder for any two polynomials, where the degree of the remainder is less than that of the divisor.

The Euclidean Algorithm proceeds by iterative application of the Division Algorithm to the pair of polynomials, reducing the degree at each step, until a zero remainder is obtained. The last non-zero remainder in this process is the gcd of the original pair of polynomials.

If specific polynomials are given, these methods can be illustrated concretely to find the gcd, demonstrating the roots of the polynomial in the finite field $\mathbb{Z}/p\mathbb{Z}$ and thereby the factors of the polynomial that are linear polynomials $x - a$.

# Euler's Method to check if a number if a quadratic residue

Euler's criterion states that for a prime $p$ and an integer $a$ not divisible by $p$, $a$ is a square modulo $p$ (a quadratic residue) if and only if:

$$
a^{\frac{p-1}{2}} \equiv \pm 1 \mod p
$$

Here's a brief proof of Euler's criterion:

### Proof:

1. **Fermat's Little Theorem**: For any integer $a$ and a prime $p$ not dividing $a$, it is known that $a^{p-1} \equiv 1 \mod p$.

2. **Group Theory**: The multiplicative group of non-zero elements modulo $p$, denoted by $(\mathbb{Z}/p\mathbb{Z})^*$, is a group with $p-1$ elements. If $a$ is a square, then it is an element of the subgroup of squares (quadratic residues), which has $\frac{p-1}{2}$ elements. If $a$ is not a square, it is not in this subgroup.

3. **Lagrange's Theorem**: This theorem in group theory states that the order of a subgroup divides the order of the group. Thus, the order of any element (in this case, $a$) divides the order of the group, which is $p-1$.

4. **Squares and Non-Squares**: If $a$ is a square, then $a$ is in the subgroup of quadratic residues, and its order must divide the subgroup's order, which is $\frac{p-1}{2}$. Thus, $a^{\frac{p-1}{2}} \equiv 1 \mod p$. If $a$ is not a square, then its order must be the same as the entire group, which is $p-1$, because if it were less, it would divide $\frac{p-1}{2}$, implying that $a$ is a square, which is a contradiction.

5. **Euler's Criterion**: From the above, if $a$ is a square, then raising $a$ to the power of $\frac{p-1}{2}$ gives $1$. If $a$ is not a square, it cannot give $1$, and by the properties of the multiplicative group modulo $p$, it must give the only other element of order $2$, which is $-1$.

So, Euler's criterion gives us a fast way to test if $a$ is a quadratic residue modulo $p$ without having to actually find a square root. This is particularly useful in cryptographic algorithms and primality testing.

# Example of extended case of Euler's Criterion

### Explanation of Concepts:

1. **Divisibility in Modular Arithmetic**: The statement begins by considering an integer $d$ that divides a prime number $p$ minus one, $d | (p-1)$. It then states that $x^d \equiv 1 \mod p$ has exactly $d$ roots. This is a consequence of the structure of the group of units modulo $p$, which is a cyclic group of order $p-1$. If $d$ divides $p-1$, there is a subgroup of order $d$, and by Lagrange's Theorem, elements of this subgroup raised to the power of $d$ will be congruent to $1$ mod $p$.

2. **Divisibility of Polynomials**: The image mentions that $(x^{p-1} - 1)$ is divisible by $(x^d - 1)$ if $d$ divides $p-1$. This is a result of the fact that the polynomial $x^{p-1} - 1$ has $p-1$ roots in the field of integers modulo $p$, and by the division algorithm for polynomials, if $d | (p-1)$, then $x^{d} - 1$ divides $x^{p-1} - 1$.

3. **Substitution of Variables**: The notation $(y^n - 1)$ divisible by $y$ where $y = x^d$ and $n = \frac{p-1}{d}$ suggests a change of variables. This is used to show that when you raise $y$ to the power of $n$, you get $x^{p-1}$, and since $y = x^d$, it shows that $(x^{p-1} - 1)$ is divisible by $(x^d - 1)$ by substituting $x^d$ with $y$.

4. **Greatest Common Divisor (GCD)**: The image ends with an expression suggesting that the greatest common divisor of $(x^{p-1} - 1)$ and $(x^d - 1)$ is equal to $(x^d - 1)$. This is true because, as stated earlier, $(x^d - 1)$ divides $(x^{p-1} - 1)$, which implies that $(x^d - 1)$ is the largest polynomial (in terms of degree) that divides both, hence it is their GCD.

### Connection to Euler's Criterion:

The concepts relate to Euler's criterion in the sense that they both deal with the properties of integers and polynomials in modular arithmetic. Euler's criterion gives a quick check for quadratic residues, while the concepts in the image explore the roots of unity modulo a prime $p$ and how divisibility among polynomials corresponds to the structure of the cyclic group modulo $p$. The relationship between $d$ and $p-1$ in the image is akin to the relationship between $a$ and $p$ in Euler's criterion, where powers of $a$ modulo $p$ reveal information about the residue class of $a$.

### In-Depth Analysis:

In group theory and number theory, understanding the order of elements and subgroups allows us to make predictions about the behavior of powers of elements in those groups. For instance, the multiplicative group of integers modulo $p$ is cyclic and has order $p-1$. If we have a divisor $d$ of $p-1$, then by group theory, there exists an element (or elements) of order $d$ in this group. The polynomials $(x^{p-1} - 1)$ and $(x^d - 1)$ can be seen as expressions that relate to the cyclic nature of the group. The roots of these polynomials correspond to elements of the group that satisfy the equations $x^{p-1} \equiv 1 \mod p$ and $x^d \equiv 1 \mod p$ respectively.

When we have $d | (p-1)$, the group of units modulo $p$ has a subgroup whose order is $d$. This subgroup is generated by an element $g$ such that $g^d \equiv 1 \mod p$. In terms of polynomials, this means that $g$ is a root of both polynomials $x^{p-1} - 1$ and $x^d - 1$. The fundamental theorem of algebra applied in the context of modulo $p$ arithmetic ensures that the polynomial $x^{p-1} - 1$ can be factored into linear factors corresponding to each of these roots, and

 the polynomial $x^d - 1$ will appear as a factor in this factorization due to the divisibility relation.

Furthermore, Euler's criterion comes into play when considering the exponents $(p-1)/2$ and $(d-1)/2$ in the context of quadratic residues and non-residues. The criterion provides a way to determine whether a given number $a$ is a quadratic residue modulo $p$ without factoring or finding actual square roots, which aligns with the exploration of roots and factors.



