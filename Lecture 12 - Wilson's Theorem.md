Wilson's Theorem is a beautiful and classic result in number theory. It states that for any integer $p > 1$, $p$ is a prime number if and only if the following congruence holds:

$$(p - 1)! \equiv -1 \, (\text{mod}\, p).$$

In more poetic terms, Wilson's Theorem whispers a profound truth about the delicate interplay between prime numbers and factorials. Here, $(p - 1)!$ represents the factorial of $p - 1$, which is the product of all positive integers less than $p$. The congruence symbol $\equiv$ signifies that $(p - 1)!$ and $-1$ leave the same remainder when divided by $p$.

This theorem elegantly encapsulates a fundamental characteristic of prime numbers, serving as both a test and a reflection of their primality. It's a mathematical gem, linking the concept of multiplication (through factorials) with the modular world, where arithmetic operates in a cyclic fashion.

To illustrate this theorem with an example, consider the prime number $p = 5$:

$$(5 - 1)! = 4! = 4 \times 3 \times 2 \times 1 = 24.$$

Now, checking the congruence:

$$24 \equiv -1 \, (\text{mod}\, 5),$$

since $24 + 1 = 25$, which is a multiple of $5$. Hence, the theorem holds for this prime.

However, for a non-prime like $p = 6$:

$$(6 - 1)! = 5! = 5 \times 4 \times 3 \times 2 \times 1 = 120,$$

and $120$ is not congruent to $-1$ modulo $6$, which aligns with the fact that $6$ is not a prime.

The beauty of Wilson's Theorem lies in its simplicity and deep connection to the fundamental properties of numbers, painting a vivid picture of the harmonic dance between factorials and primes in the modular realm.

# Proof of Wilson's Theorem
Wilson's Theorem states that for any integer $p > 1$, $p$ is a prime number if and only if 
$$(p-1)! \equiv -1 \ (\text{mod} \ p).$$

**Proof:**

Let's consider the two parts of this biconditional statement separately.

1. **If $p$ is a prime, then $(p-1)! \equiv -1 \ (\text{mod} \ p)$:**

   Since $p$ is prime, the numbers $1, 2, \ldots, p-1$ are all relatively prime to $p$. Consider the set $\{1, 2, \ldots, p-1\}$. Except for $1$ and $p-1$, each of these numbers has a multiplicative inverse modulo $p$ within this set. This is because for each $a$ in the set, there exists a $b$ such that $ab \equiv 1 \ (\text{mod} \ p)$, and $a \neq b$ unless $a$ is $1$ or $p-1$.

   Therefore, when we compute $(p-1)! = 1 \cdot 2 \cdot \ldots \cdot (p-1)$ modulo $p$, all terms except for $1$ and $p-1$ cancel out with their inverses. Hence, $(p-1)! \equiv 1 \cdot (p-1) \equiv -1 \ (\text{mod} \ p)$.

2. **If $(p-1)! \equiv -1 \ (\text{mod} \ p)$, then $p$ is a prime:**

   This is the contrapositive of the statement "If $p$ is not a prime, then $(p-1)! \not\equiv -1 \ (\text{mod} \ p)$." Assume $p$ is not prime, so $p$ has a divisor $d$ such that $1 < d < p$. Since $d$ divides $p$, and $d < p$, it follows that $d$ divides $(p-1)! = 1 \cdot 2 \cdot \ldots \cdot (p-1)$. Hence, $(p-1)! \equiv 0 \ (\text{mod} \ p)$ when $p$ is not prime, which is a contradiction to our assumption that $(p-1)! \equiv -1 \ (\text{mod} \ p)$.

Therefore, Wilson's Theorem is proven.

# Application of Wilson's Theorem to find the square root of minus 1 mod p

Wilson's Theorem states that for any prime number $p$, it holds that
$$(p-1)! \equiv -1 \mod p.$$

To apply Wilson's Theorem to find the square root of -1 in a modular arithmetic setting, we need to find a prime $p$ and a number $x$ such that
$$x^2 \equiv -1 \mod p,$$
which can also be written as
$$x^2 \equiv p - 1 \mod p.$$

For such a solution to exist, $p - 1$ should be a quadratic residue modulo $p$. Not all primes $p$ will satisfy this condition. For instance, if $p = 2$, we can see that $1^2 \equiv -1 \mod 2$. However, for larger primes, we need to find $p$ for which $p - 1$ is a quadratic residue.

A common approach is to look at primes of the form $4k + 1$, where $k$ is an integer. For these primes, by Fermat's theorem on sums of two squares, $p$ can be expressed as the sum of two squares, and one of these squares is a square root of -1 modulo $p$.

Let's take an example with $p = 5$. We have $5 = 4 \cdot 1 + 1$, and $2^2 \equiv -1 \mod 5$. Therefore, 2 is a square root of -1 modulo 5.

For a computational example, we can find a square root of -1 modulo a prime $p$ of the form $4k + 1$. Let's choose $p = 13$ and compute.

For the prime $p = 13$, which is of the form $4k + 1$, we find that $5^2 \equiv -1 \mod 13$. Therefore, $5$ is a square root of -1 modulo 13. This approach demonstrates the application of Wilson's Theorem in finding the square root of -1 in modular arithmetic for certain primes.



# Proof: $(\frac{p-1}{2})!$ is $\sqrt{ -1 }$ if $p \equiv 1 \pmod{4}$
