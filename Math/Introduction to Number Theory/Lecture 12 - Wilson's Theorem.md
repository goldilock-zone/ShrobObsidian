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
To prove that $(\frac{p-1}{2})! \equiv \sqrt{-1} \pmod{p}$ for a prime $p$ where $p \equiv 1 \pmod{4}$, we can follow these steps, utilizing Wilson's Theorem and modular arithmetic properties:

1. **Wilson's Theorem**: It states $(p-1)! \equiv -1 \pmod{p}$ for a prime $p$.

2. **Given Condition**: Given $p \equiv 1 \pmod{4}$, it follows that $p = 4k + 1$ for some integer $k$.

3. **Expanding $(p-1)!$**: Express $(p-1)!$ as $1 \cdot 2 \cdot 3 \cdot \ldots \cdot (p-1)$.

4. **Pairing Terms**: For each number $a$ in this sequence, there exists an inverse $b$ such that $ab \equiv 1 \pmod{p}$, except for numbers that are their own inverses. This is true for $a = \pm 1$ and $a = \pm \sqrt{-1}$ when $p \equiv 1 \pmod{4}$.

5. **Simplifying the Product**: Pairs where $ab \equiv 1 \pmod{p}$ cancel out, leaving $(p-1)! \equiv (-1) \cdot (\sqrt{-1})^2 \pmod{p}$, considering self-inverse elements.

6. **Using Wilson's Theorem**: We know $(p-1)! \equiv -1 \pmod{p}$. This implies $(\sqrt{-1})^2 \equiv -1 \pmod{p}$.

7. **Isolating $(\frac{p-1}{2})!$**: It follows that $(\frac{p-1}{2})!$ must be equivalent to $\sqrt{-1}$ modulo $p$, as it's the only term that, squared, results in $-1$ modulo $p$.

In conclusion, when $p \equiv 1 \pmod{4}$, $(\frac{p-1}{2})!$ is equivalent to $\sqrt{-1}$ modulo $p$, demonstrating an elegant connection between number theory and modular arithmetic.

# Using a specific case of Wilson's Theorem to prove Fermat's and Euler's Theorem

# Note: The proof given below is very weak
Wilson's Theorem states that for any prime number $p$, the product of all positive integers less than $p$ is congruent to $-1$ modulo $p$. Mathematically, this is expressed as:

$$ (p - 1)! \equiv -1 \pmod{p} $$

This theorem can be used to prove Fermat's Little Theorem and Euler's Theorem in specific cases.

### Fermat's Little Theorem

Fermat's Little Theorem states that for any integer $a$ and a prime $p$, if $p$ does not divide $a$, then $a^{p-1} \equiv 1 \pmod{p}$. 

Using Wilson's Theorem, we can prove Fermat's Little Theorem in the case where $a = p - 1$. Here's how:

1. From Wilson's Theorem, we know $(p - 1)! \equiv -1 \pmod{p}$.
2. Expanding $(p - 1)!$, we get $(p-1)(p-2)(p-3)\ldots(2)(1)$.
3. Notice that each element in this product, except for $(p - 1)$, has an inverse modulo $p$. This means that when you multiply each number by its inverse, you get $1$ modulo $p$.
4. Thus, all terms except $(p - 1)$ cancel out, leaving us with $(p - 1) \equiv -1 \pmod{p}$.
5. Raising both sides to the power of $p-1$, we get $(p - 1)^{p-1} \equiv (-1)^{p-1} \pmod{p}$.
6. Since $p$ is odd (being prime and greater than $2$), $(-1)^{p-1} = -1 \times -1 \times \ldots = 1$.
7. Therefore, $(p - 1)^{p-1} \equiv 1 \pmod{p}$, which is Fermat's Little Theorem for $a = p - 1$.

### Euler's Theorem

Euler's Theorem generalizes Fermat's Little Theorem. It states that for any integer $a$ and $n$ where $\gcd(a, n) = 1$, $a^{\phi(n)} \equiv 1 \pmod{n}$, where $\phi(n)$ is Euler's totient function.

However, Wilson's Theorem cannot be directly used to prove Euler's Theorem in general, as it specifically deals with prime numbers, while Euler's Theorem applies to any $n$ with $\gcd(a, n) = 1$. Wilson's Theorem is a specific case and does not provide a direct pathway to proving Euler's Theorem for composite numbers. 

In summary, Wilson's Theorem can be used to prove Fermat's Little Theorem in a specific case where $a = p - 1$, but it does not provide a direct method for proving Euler's Theorem for composite numbers.

# A better proof of Fermat using Wilson
The image depicts a handwritten note regarding the proof of Fermat's Little Theorem using Wilson's Theorem. Here is how to connect the two theorems rigorously:

**Fermat's Little Theorem** states that if $p$ is a prime number and $a$ is an integer not divisible by $p$, then $a^{p-1} \equiv 1 \mod p$. In formal notation, this is written as:

$$ a^{p-1} \equiv 1 \mod p, \quad \text{where } \gcd(a,p) = 1. $$

**Wilson's Theorem** states that for a prime number $p$, the factorial $(p-1)!$ is congruent to $-1$ modulo $p$:

$$ (p-1)! \equiv -1 \mod p. $$

To prove Fermat's Little Theorem using Wilson's Theorem, consider the set of integers $\{1, 2, \ldots, p-1\}$ modulo $p$. Because $p$ is prime, each element $a$ in the set has a multiplicative inverse modulo $p$ (which is also in the set). This means that each number in the set pairs up with its inverse to give a product congruent to $1$ modulo $p$, except for the numbers $1$ and $p-1$ which are their own inverses.

So, taking the product of all numbers in the set, we get:

$$ 1 \cdot 2 \cdot \ldots \cdot (p-1) \equiv (p-1)! \equiv -1 \mod p. $$

Now, if we multiply each element by $a$ (where $\gcd(a,p) = 1$), we obtain the sequence $a, 2a, \ldots, (p-1)a$. Since $a$ is coprime to $p$, multiplication by $a$ permutes the original set $\{1, 2, \ldots, p-1\}$ modulo $p$. The product of all elements in this new sequence is also congruent to $-1$ modulo $p$:

$$ a \cdot (2a) \cdot \ldots \cdot ((p-1)a) \equiv a^{p-1} \cdot (p-1)! \equiv -1 \mod p. $$

Given that $(p-1)! \equiv -1 \mod p$ from Wilson's Theorem, we can divide both sides of the congruence by $(p-1)!$ to obtain Fermat's Little Theorem:

$$ a^{p-1} \cdot (p-1)! \equiv -1 \mod p, $$
$$ a^{p-1} \equiv \frac{-1}{(p-1)!} \mod p, $$
$$ a^{p-1} \equiv 1 \mod p, $$

where the last step follows from Wilson's Theorem. This concludes the proof.

# Connection of the above proof to Group Theory
The proof of Fermat's Little Theorem using Wilson's Theorem can indeed be framed in the context of abstract group theory, particularly using concepts from Lagrange's Theorem and the properties of Abelian groups. Here's how:

### Background Concepts

1. **Lagrange's Theorem:** In group theory, Lagrange's Theorem states that the order (number of elements) of any subgroup of a finite group divides the order of the group. In the context of modular arithmetic, the relevant group is the multiplicative group of integers modulo $p$, denoted as $(\mathbb{Z}/p\mathbb{Z})^*$, where $p$ is a prime number.

2. **Abelian Groups:** A group is Abelian if it is commutative, meaning that the operation, in this case multiplication, commutes: $ab = ba$ for all elements $a$ and $b$ in the group. The group $(\mathbb{Z}/p\mathbb{Z})^*$ is an Abelian group.

### Connecting the Concepts to the Theorem

1. **Multiplicative Group Modulo $p$:** Consider the multiplicative group $(\mathbb{Z}/p\mathbb{Z})^*$, which consists of all integers from $1$ to $p-1$ that are coprime to $p$. Since $p$ is prime, this includes all integers from $1$ to $p-1$.

2. **Order of the Group:** The order of $(\mathbb{Z}/p\mathbb{Z})^*$ is $p-1$, because there are $p-1$ elements in the group.

3. **Applying Lagrange's Theorem:** According to Lagrange's Theorem, the order of any element $a$ in $(\mathbb{Z}/p\mathbb{Z})^*$ (i.e., the smallest positive integer $m$ such that $a^m \equiv 1 \mod p$) must divide the order of the group, which is $p-1$. Therefore, $a^{p-1} \equiv 1 \mod p$ for all $a \in (\mathbb{Z}/p\mathbb{Z})^*$.

4. **Wilson's Theorem as a Special Case:** Wilson's Theorem, which states that $(p-1)! \equiv -1 \mod p$, can be seen as a special case of this result. It reflects the product of all elements in the group $(\mathbb{Z}/p\mathbb{Z})^*$, demonstrating the nature of the group's structure and its relation to modular arithmetic.

5. **Fermat's Little Theorem from Lagrange's Theorem:** Since the order of every non-zero element modulo $p$ divides $p-1$, raising any element to the power $p-1$ results in $1$ modulo $p$, which is precisely Fermat's Little Theorem.

### Conclusion

In summary, Fermat's Little Theorem is a natural consequence of the properties of the multiplicative group modulo $p$, specifically its Abelian nature and the implications of Lagrange's Theorem. This abstract group theory perspective provides a broader and deeper understanding of the theorem's place within the structure of mathematics.


# Discussion on the Product of numbers Co Prime to a, modulo m
The behavior of units modulo $n$ can indeed exhibit complex patterns, especially when $n$ is composite. Let's delve deeper into the structure and behavior of the group of units, $U(m)$, for a given positive integer $m$.

### Understanding $U(m)$ and Its Product Behavior

1. **Definition of $U(m)$**: The group $U(m)$ consists of all integers less than $m$ that are coprime to $m$. These elements have multiplicative inverses modulo $m$.

2. **Wilson's Theorem for Prime $p$**: For a prime number $p$, Wilson's theorem states that $(p-1)! \equiv -1 \mod p$. This theorem highlights a specific behavior of the product of units modulo a prime number.

3. **Behavior for Composite $m$**:
   - **Case $m = 4$**: The units are $\{1, 3\}$. The product $1 \cdot 3 \equiv 3 \equiv -1 \mod 4$. This mirrors Wilson's theorem.
   - **Case $m = 8$**: The units are $\{1, 3, 5, 7\}$. The product $1 \cdot 3 \cdot 5 \cdot 7 = 105 \equiv 1 \mod 8$, which differs from the Wilson's theorem prediction.

4. **Generalization for Composite $m$**: 
   - **Prime Factorization of $m$**: If $m$ has the prime factorization $p_1^{k_1} p_2^{k_2} \cdots p_r^{k_r}$, the behavior of the product of elements in $U(m)$ is influenced by the structure of $U(m)$.
   - **Behavior Based on $U(m)$**: For powers of odd primes and for $2$ and $4$, the product of units is $-1 \mod m$. For higher powers of $2$ (like $8$), it is $1 \mod m$. This variation arises from the non-cyclic nature of $U(m)$ for certain $m$.

5. **Group Structure of $U(m)$**:
   - **Cyclic vs. Non-Cyclic**: For some $m$, $U(m)$ forms a cyclic group, but for others, particularly for higher powers of $2$, it does not.
   - **Example with $m = 8$**: $U(8)$ is not cyclic and resembles a direct sum of $\mathbb{Z}/2\mathbb{Z}$ and $\mathbb{Z}/2\mathbb{Z}$.

### Implications and Applications

- **Number Theory**: These behaviors are crucial in advanced number theory, especially in understanding the properties of modular arithmetic in non-prime systems.
- **Cryptography**: The properties of $U(m)$ are significant in cryptographic algorithms like RSA, where the choice of $m$ (as a product of two primes) is essential.

