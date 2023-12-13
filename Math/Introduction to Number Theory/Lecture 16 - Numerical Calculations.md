# Using Wilson's Theorem to find the square root of minus 1 mod p, when p is congruent to 1 mod 4 

Wilson's Theorem states that for any prime $p$, the product $(p-1)! \equiv -1 \mod p$. 

From the image, it seems to suggest a calculation of $x$ using Wilson's Theorem, where $x$ is given by the factorial of half the prime minus one, or $\left(\frac{p-1}{2}\right)!$. The notation $(\frac{p-1}{2})!$ is used to denote the factorial of $\frac{p-1}{2}$, which is the product of all positive integers up to $\frac{p-1}{2}$.

Let's consider the congruence $x^2 \equiv 1 \mod p$. The solutions to this congruence are $x \equiv 1 \mod p$ and $x \equiv -1 \mod p$ because squaring either $1$ or $-1$ will result in $1$ modulo $p$.

Now, if $p$ is a prime such that $p \equiv 1 \mod 4$, then by Wilson's Theorem:
$$
(p-1)! \equiv -1 \mod p
$$

This can be written as:
$$
1 \cdot 2 \cdot 3 \cdot \ldots \cdot \left(\frac{p-1}{2}\right) \cdot \left(\frac{p+1}{2}\right) \cdot \ldots \cdot (p-1) \equiv -1 \mod p
$$

Notice that each pair of terms from $1$ to $\left(\frac{p-1}{2}\right)$ and from $\left(\frac{p+1}{2}\right)$ to $(p-1)$ are inverses of each other modulo $p$. That is, for each $k$ in $1, 2, \ldots, \left(\frac{p-1}{2}\right)$, there exists a $k^{-1}$ such that $k \cdot k^{-1} \equiv 1 \mod p$. Hence, all these terms will cancel each other out when multiplied together, except for $\left(\frac{p-1}{2}\right)!$. Therefore, we can infer that:
$$
\left[\left(\frac{p-1}{2}\right)!\right]^2 \equiv -1 \mod p
$$

Taking the modular square root, if it exists, gives us the value of $x$ such that:
$$
x \equiv \pm \left(\frac{p-1}{2}\right)! \mod p
$$

To find a concrete example, let's consider a small prime $p$ where $p \equiv 1 \mod 4$, say $p=5$.

Wilson's Theorem tells us that:
$$
4! \equiv -1 \mod 5
$$

Calculating $4!$ gives $24$, and indeed $24 \equiv -1 \mod 5$. Now for $x$:
$$
x \equiv \pm \left(\frac{5-1}{2}\right)! \mod 5
$$

This simplifies to:
$$
x \equiv \pm 2! \mod 5
$$

And since $2! = 2$, we have:
$$
x \equiv \pm 2 \mod 5
$$

Thus, the two solutions to $x^2 \equiv 1 \mod 5$ are $x \equiv 2 \mod 5$ and $x \equiv -2 \equiv 3 \mod 5$, which can be easily verified by squaring both $2$ and $3$ modulo $5$.

# A Better Method
The second part of the notes is focused on finding a solution to the congruence $x^2 \equiv 1 \mod p$ using properties of modular arithmetic when $p$ is a prime number congruent to $1$ modulo $4$. The method shown is rooted in the application of Euler's Criterion and Fermat's Little Theorem. 

**Euler's Criterion**: This theorem states that for a prime $p$ and an integer $a$ such that $\gcd(a, p) = 1$, we have
$$
a^{\frac{p-1}{2}} \equiv \left(\frac{a}{p}\right) \mod p,
$$
where $\left(\frac{a}{p}\right)$ is the Legendre symbol and can take values $1$, $-1$, or $0$. If $a$ is a quadratic residue modulo $p$, then $\left(\frac{a}{p}\right) = 1$, and if $a$ is a non-residue, then $\left(\frac{a}{p}\right) = -1$.

**Fermat's Little Theorem**: This theorem asserts that if $p$ is a prime and $a$ is an integer not divisible by $p$, then
$$
a^{p-1} \equiv 1 \mod p.
$$

In the notes, the following steps are outlined:

1. Choose a number $b$ such that $\gcd(b, p) = 1$.
2. Compute $a \equiv b^{\frac{p-1}{2}} \mod p$. 

From Euler's Criterion, we have two possible outcomes:
$$
b^{\frac{p-1}{2}} \equiv \pm 1 \mod p.
$$

Because of Fermat's Little Theorem, we know that $b^{p-1} \equiv 1 \mod p$, so squaring both sides of the congruence from Euler's Criterion, we get $a^2 \equiv (b^{\frac{p-1}{2}})^2 \equiv 1 \mod p$, which tells us that $a$ (or $-a$) is a solution to the original congruence $x^2 \equiv 1 \mod p$.

Let's illustrate this with an example:

Take $p = 5$, which is a prime number and satisfies $p \equiv 1 \mod 4$. Now, pick $b = 2$, noting that $\gcd(2, 5) = 1$.

Compute $a$ as:
$$
a \equiv b^{\frac{p-1}{2}} \mod p \equiv 2^{\frac{5-1}{2}} \mod 5 \equiv 2^2 \mod 5 \equiv 4 \mod 5.
$$

Now check $a^2 \mod p$:
$$
a^2 \equiv 4^2 \mod 5 \equiv 16 \mod 5 \equiv 1 \mod 5.
$$

So, $a = 4$ is indeed a solution to $x^2 \equiv 1 \mod 5$. The other solution is $-a$, which is $-4 \equiv 1 \mod 5$, because $5$ divides $4 + 1$.

In this way, using a combination of Euler's Criterion and Fermat's Little Theorem, we can efficiently find solutions to the congruence $x^2 \equiv 1 \mod p$ for any prime $p$.

[[Worst Case Exponential, but average case polynomial time]]

# Solving $x^2 \equiv -1 \mod 41$
The equation presented in the image, $x^2 \equiv -1 \mod 41$, asks for solutions $x$ such that when $x$ is squared, the result is congruent to $-1$ modulo $41$. 

To solve this, we look for an integer $x$ such that $x^2 + 1$ is divisible by $41$. This is a case of finding quadratic residues, and since $41$ is a prime, we can use Euler's Criterion to determine if $-1$ is a quadratic residue modulo $41$.

Euler's Criterion states that for a prime $p$ and an integer $a$ such that $\gcd(a, p) = 1$, the congruence $a^{(p-1)/2} \equiv \left(\frac{a}{p}\right) \mod p$ holds, where $\left(\frac{a}{p}\right)$ is the Legendre symbol.

For $a = -1$ and $p = 41$:
$$
(-1)^{(41-1)/2} \equiv \left(\frac{-1}{41}\right) \mod 41.
$$
Calculating the left-hand side, we get:
$$
(-1)^{20} \equiv 1 \mod 41,
$$
because the exponent $20$ is even, and $(-1)^{even} = 1$.

Since the left-hand side is congruent to $1$, the Legendre symbol $\left(\frac{-1}{41}\right)$ is also $1$, indicating that $-1$ is indeed a quadratic residue modulo $41$. This means there exists an integer $x$ such that $x^2 \equiv -1 \mod 41$.

Now, to find such an $x$, we can employ trial and error by checking the squares of integers modulo $41$ or use an algorithmic approach like the Tonelli-Shanks algorithm to find the square roots of $-1$ modulo $41$. Since $41$ is relatively small, we can feasibly find the solution with a simple computational search.

The solutions to the congruence $x^2 \equiv -1 \mod 41$ are $x = 9$ and $x = 32$. This means that $9^2$ and $32^2$ both leave a remainder of $-1$ when divided by $41$, satisfying the given congruence.

# Prime Testing using difference of squares
To test whether a given number $n$ is prime using the difference of squares method, we can follow these steps:

### Step 1: Express $n$ as $n = x^2 - y^2$ ###
We start by expressing the number $n$ as the difference of two squares, where $x$ and $y$ are positive integers such that $x > y$. Mathematically, this can be represented as:

$$
n = x^2 - y^2
$$

### Step 2: Calculate the Square Root of $n$ ###
Calculate the square root of $n$ and round it up to the nearest integer. Let's denote this as $\sqrt{n}$.

### Step 3: Iterate Through Possible Values of $y$ ###
We iterate through positive integers for the value of $y$ from $2$ to $\sqrt{n}$. For each value of $y$, we calculate the corresponding $x$ using the equation from step 1:

$$
x = \sqrt{n + y^2}
$$

### Step 4: Check if $x$ is an Integer ###
For each pair of $x$ and $y$ obtained in step 3, we check whether $x$ is an integer. If $x$ is not an integer, we continue to the next value of $y$. If $x$ is an integer, we proceed to the next step.

### Step 5: Check if $n$ Is Prime ###
We have found a pair of integers $(x, y)$ such that $x^2 - y^2 = n$. Now, we need to check if $n$ is prime. To do this, we can use the following theorem:

**Theorem**: If $n$ can be expressed as $n = a \cdot b$, where $a$ and $b$ are positive integers greater than $1$, then $n$ is not a prime number.

Therefore, if we find a pair $(x, y)$ such that $x^2 - y^2 = n$, and $x$ and $y$ are not equal to $1$, then we can conclude that $n$ is not prime.

### Step 6: Determine the Primality of $n$ ###
- If we find a pair of integers $(x, y)$ such that $x^2 - y^2 = n$, and both $x$ and $y$ are equal to $1$, then $n$ is equal to $1$, and it is not a prime number.
- If we find a pair of integers $(x, y)$ such that $x^2 - y^2 = n$, and at least one of $x$ and $y$ is greater than $1$, then $n$ is not a prime number.
- If we do not find any such pair for any value of $y$ in the range from $2$ to $\sqrt{n}$, then $n$ is a prime number.

By following these steps, we can determine whether a given number $n$ is prime using the difference of squares method. This method leverages the fact that composite numbers can be expressed as products of two integers greater than $1$, while prime numbers cannot.

[[Lecture 1 - Introduction to Number Theory - Revisited]]

# Miller Rabin Primality Test
The image describes a process that is related to primality testing, specifically an algorithm known as the Miller-Rabin primality test. The test is a probabilistic algorithm used to determine whether a given number, $m$, is prime. Here is the process as described in the image, followed by a more formal explanation:

To test if $m$ is prime:
1. Express $m-1$ as $2^s \cdot d$, where $d$ is odd.
2. Pick a random number $b$.
3. Compute $b^d \mod m$.
4. Square the result repeatedly, taking the modulus $m$ each time, until one of the following happens:
   - The number becomes 1, which may indicate that $m$ is prime.
   - The number becomes $m-1$, which indicates that $m$ is likely prime.
   - None of the squarings result in $m-1$. In this case, $m$ is composite.

Now, for the theorem and a rigorous explanation:

**Miller-Rabin Primality Test:**

**Theorem:** If $m$ is a prime number and $m-1 = 2^s \cdot d$ with $d$ odd, then for any base $a$ such that $1 < a < m-1$:
1. Either $a^d \equiv 1 \pmod{m}$.
2. Or there exists some $0 \leq r < s$ such that $a^{2^r \cdot d} \equiv -1 \pmod{m}$.

The Miller-Rabin test uses this theorem to check for non-primality. Here's the algorithm in a more formalized way:

1. Given an input number $m > 2$, write $m - 1$ as $2^s \cdot d$ where $d$ is odd. This is possible because any even number can be written as a power of 2 times an odd number.
2. Choose a random integer $a$ with $2 \leq a \leq m - 2$.
3. Compute $x = a^d \mod m$.
4. If $x = 1$ or $x = m - 1$, $m$ passes this round of the test.
5. For each $r$ from 1 to $s - 1$, compute $x = x^2 \mod m$. If $x = m - 1$, $m$ passes this round of the test.
6. If none of the squarings of $x$ result in $m - 1$, then $m$ is composite.
7. If $m$ passes several rounds of the test with different bases $a$, the probability that $m$ is prime increases. However, there is still a chance that $m$ is a strong pseudoprime to base $a$. To reduce the probability of a false positive, the test is repeated with different values of $a$.

The Miller-Rabin test is a probabilistic test because there is a small chance that a composite number could pass the test by coincidence; such numbers are called strong pseudoprimes. If $m$ is composite, the probability that it will pass the test for a random value of $a$ is at most $\frac{1}{4}$. By repeating the test for different values of $a$, the probability of mistakenly classifying a composite number as prime can be made arbitrarily small.


$$
\text{Given } m, \text{ write } m-1 = 2^s \cdot d \text{ where } d \text{ is odd.}
$$
$$
\text{Pick random } b, 1 < b < m-1.
$$
$$
\text{Compute } x = b^d \mod m.
$$
$$
\text{If } x = 1 \text{ or } x = m-1, \text{ then } m \text{ is probably prime.}
$$
$$
\text{For each } r \text{ from 1 to } s-1, \text{ compute } x = x^2 \mod m. \text{ If } x = m-1, \text{ stop and } m \text{ is probably prime.}
$$
$$
\text{If } x \neq m-1 \text{ for all } r, \text{ then } m \text{ is composite.}
$$

This test is widely used in computer algorithms for its efficiency, especially when dealing with very large numbers.



