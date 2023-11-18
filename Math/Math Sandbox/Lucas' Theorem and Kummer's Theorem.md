Lucas' Theorem and Kummer's Theorem are two significant results in number theory, particularly in the study of binomial coefficients and their divisibility properties. These theorems provide deep insights into the nature of binomial coefficients, especially in relation to prime numbers.

### Lucas' Theorem

Lucas' Theorem provides a method for determining the binomial coefficient \( \binom{n}{k} \) modulo a prime number \( p \). It states that if \( n \) and \( k \) are non-negative integers and \( p \) is a prime, then the binomial coefficient \( \binom{n}{k} \) modulo \( p \) is given by the product of binomial coefficients of the digits in the base-\( p \) expansions of \( n \) and \( k \).

Formally, if \( n \) and \( k \) are expressed in base \( p \) as:

$$
n = n_0 + n_1p + n_2p^2 + \ldots + n_rp^r \\
k = k_0 + k_1p + k_2p^2 + \ldots + k_rp^r
$$

then,

$$
\binom{n}{k} \equiv \binom{n_0}{k_0} \cdot \binom{n_1}{k_1} \cdot \binom{n_2}{k_2} \cdot \ldots \cdot \binom{n_r}{k_r} \pmod{p}
$$

Lucas' Theorem is particularly useful for computations involving large binomial coefficients and for proving certain types of divisibility properties of binomial coefficients by prime numbers.

### Kummer's Theorem

Kummer's Theorem provides a way to determine the highest power of a prime number \( p \) that divides a binomial coefficient \( \binom{n}{k} \). It is based on the number of carries when adding \( k \) and \( n-k \) in base \( p \).

Kummer's Theorem states that the highest power of \( p \) dividing \( \binom{n}{k} \) is equal to the number of carries in the addition of \( k \) and \( n-k \) in base \( p \). This theorem is instrumental in understanding the p-adic valuation of binomial coefficients and is particularly significant in combinatorial proofs and in the study of p-adic numbers.

### Implications and Uses

- **Divisibility Analysis**: These theorems are often used to analyze the divisibility of binomial coefficients by prime numbers, which is a crucial aspect of many combinatorial arguments and proofs.
- **Combinatorial Identities**: They help in proving or deriving certain combinatorial identities.
- **Number Theory**: These theorems contribute to the understanding of the behavior of numbers in different bases and the relationship between prime numbers and combinatorial structures.

In summary, Lucas' and Kummer's Theorems bridge combinatorics and number theory, providing elegant and powerful tools for investigating the properties of binomial coefficients, particularly in relation to prime numbers and divisibility.

# Explanation of Kummer's Theorem
In the context of Kummer's Theorem and the addition of numbers in base \(p\), the term "number of carries" refers to the count of times you need to carry over a digit from one place value to the next when adding two numbers digit by digit in base \(p\).

Here's a brief explanation of how it works:

In base \(p\), each digit can take on values from \(0\) to \(p-1\). When you add two numbers in this base, you start from the rightmost digits and move towards the left. If the sum of the digits in a particular place value is greater than or equal to \(p\), you need to carry over the excess to the next left place value. This process continues until you've added all the digits.

For example, let's say we are working in base \(10\) (decimal) and we want to add \(456\) and \(789\):

```
  456
+ 789
------
```

You start by adding the rightmost digits: \(6 + 9 = 15\). Since \(15\) is greater than \(10\), you carry over the \(1\) to the tens place and write down \(5\) in the units place. Then, you add the digits in the tens place: \(1 + 5 + 8 = 14\). Again, \(14\) is greater than \(10\), so you carry over another \(1\) to the hundreds place and write down \(4\) in the tens place. Finally, you add the digits in the hundreds place: \(1 + 4 + 7 = 12\). You carry over \(1\) to the thousands place and write down \(2\) in the hundreds place. The result is \(1245\).

In this example, there were three carries: one from the units place to the tens place, one from the tens place to the hundreds place, and one from the hundreds place to the thousands place.

In the context of Kummer's Theorem, when you're adding \(k\) and \(\binom{n}{k}\) in base \(p\), the "number of carries" refers to how many times you need to carry over from one place value to the next during this addition process. This concept is used to determine the highest power of \(p\) that divides \(\binom{n}{k}\), as described in the theorem.

# Proof of Lucas' Theorem
To provide a more detailed and explicit proof of Lucas' Theorem, let's delve into the specific steps and cases. We'll use a combination of combinatorial reasoning, modular arithmetic, and the properties of binomial coefficients.

### Proof of Lucas' Theorem

1. **Combinatorial Setup**: Consider the binomial coefficient \( \binom{n}{k} \) as the coefficient of \( x^k \) in the expansion of \( (1 + x)^n \) by the Binomial Theorem. This expansion is:

   $$
   (1 + x)^n = \sum_{k=0}^{n} \binom{n}{k} x^k
   $$

2. **Base \( p \) Expansion**: Write \( n \) and \( k \) in base \( p \) (where \( p \) is prime) as:

   $$
   n = n_rp^r + n_{r-1}p^{r-1} + \ldots + n_1p + n_0
   $$
   $$
   k = k_rp^r + k_{r-1}p^{r-1} + \ldots + k_1p + k_0
   $$

3. **Expanding Each Term Separately**: We focus on the expansion of \( (1 + x)^{n_ip^i} \) for each digit \( n_i \) of \( n \) in base \( p \). The key is to use the Binomial Theorem and then apply Fermat's Little Theorem, which states that for any integer \( a \), \( a^p \equiv a \pmod{p} \).

4. **Application of Fermat's Little Theorem**: This theorem simplifies each term in the expansion:

   $$
   (1 + x)^{p^i} = 1 + x^{p^i} \pmod{p}
   $$

   because all intermediate terms \( \binom{p^i}{j} x^j \) for \( 1 \leq j \leq p^i - 1 \) are divisible by \( p \) and thus vanish modulo \( p \).

5. **Multiplying the Expansions**: The expansion of \( (1 + x)^n \) can be represented as the product of these individual expansions:

   $$
   (1 + x)^n = (1 + x)^{n_0} (1 + x^p)^{n_1} (1 + x^{p^2})^{n_2} \ldots (1 + x^{p^r})^{n_r} \pmod{p}
   $$

6. **Extracting the Coefficient of \( x^k \)**: The coefficient of \( x^k \) in this product is equivalent to taking the product of the coefficients of \( x^{k_i} \) from each factor \( (1 + x^{p^i})^{n_i} \) modulo \( p \). This product gives the binomial coefficients \( \binom{n_i}{k_i} \) for each digit in the base \( p \) expansions of \( n \) and \( k \).

7. **Final Congruence**: Thus, the coefficient of \( x^k \) in the expansion of \( (1 + x)^n \) modulo \( p \) is exactly the product of these binomial coefficients:

   $$
   \binom{n}{k} \equiv \binom{n_r}{k_r} \binom{n_{r-1}}{k_{r-1}} \ldots \binom{n_1}{k_1} \binom{n_0}{k_0} \pmod{p}
   $$

### Conclusion

In this proof, we have explicitly used the base \( p \) expansions of \( n \) and \( k \), along with Fermat's Little Theorem, to decompose the problem into smaller, more manageable parts. Each step adheres to the principles of combinatorial reasoning and modular arithmetic, ultimately leading to the elegant result stated in Lucas' Theorem. This theorem not only provides a practical tool for computing binomial coefficients modulo a prime but also highlights the beautiful interplay between number theory and combinatorics.

# Proof Of Kummers' Theorem
Kummer's Theorem provides a way to determine the highest power of a prime number \( p \) that divides a binomial coefficient \( \binom{n}{k} \). The theorem states that this power is equal to the number of carries when adding \( k \) and \( n-k \) in base \( p \). Let's go through a detailed proof of this theorem.

### Proof of Kummer's Theorem

1. **Base \( p \) Expansion**: Consider the base \( p \) expansions of \( n \), \( k \), and \( n-k \). Let

   $$
   n = n_rp^r + n_{r-1}p^{r-1} + \ldots + n_1p + n_0
   $$
   $$
   k = k_rp^r + k_{r-1}p^{r-1} + \ldots + k_1p + k_0
   $$
   $$
   n-k = (n-k)_rp^r + (n-k)_{r-1}p^{r-1} + \ldots + (n-k)_1p + (n-k)_0
   $$

2. **Factorial Expansion and p-adic Valuation**: The binomial coefficient \( \binom{n}{k} \) can be written as

   $$
   \binom{n}{k} = \frac{n!}{k!(n-k)!}
   $$

   Consider the p-adic valuation (the highest power of \( p \) dividing a number) of each of these factorials. The p-adic valuation of \( n! \) is the sum of the quotients \( \left\lfloor \frac{n}{p^i} \right\rfloor \) for \( i \geq 1 \). This counts the number of multiples of \( p, p^2, p^3, \ldots \) in the product \( 1 \times 2 \times \ldots \times n \).

3. **Counting Carries**: The key observation is that the carry operation when adding \( k \) and \( n-k \) in base \( p \) occurs precisely when the sum of the corresponding digits of \( k \) and \( n-k \) exceeds \( p \). Each carry increases the p-adic valuation of the denominator \( k!(n-k)! \) but does not affect the numerator \( n! \).

4. **p-adic Valuation of Binomial Coefficients**: The p-adic valuation of \( \binom{n}{k} \) is the difference between the p-adic valuation of \( n! \) and the sum of the p-adic valuations of \( k! \) and \( (n-k)! \). Each carry in the addition of \( k \) and \( n-k \) decreases this difference by 1, as it adds one more factor of \( p \) to the denominator that is not canceled by the numerator.

5. **Conclusion**: Therefore, the number of carries in the addition of \( k \) and \( n-k \) in base \( p \) is exactly the additional power of \( p \) dividing the denominator of \( \binom{n}{k} \) compared to the numerator. This number is the highest power of \( p \) dividing \( \binom{n}{k} \).

### Summary

Kummer's Theorem elegantly links the combinatorial concept of binomial coefficients with the number-theoretic concept of p-adic valuation. It shows that the divisibility of binomial coefficients by a prime \( p \) can be understood by simply analyzing the carries in the addition of two numbers in base \( p \). This theorem has profound implications in combinatorics, number theory, and even in the study of algebraic structures and topology.

# Notes:
Damn this is so useful
