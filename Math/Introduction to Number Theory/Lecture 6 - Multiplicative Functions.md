# Arithmetical Functions
Arithmetical functions, in the realm of number theory, are functions $f: \mathbb{N} \to \mathbb{C}$ that assign a complex number to each natural number. They are the keystones of number theory, revealing the intricate patterns and properties inherent in the integers. To illuminate their nature, let us consider a few classic examples:

1. **Divisor Function ($\sigma_k(n)$)**: This function yields the sum of the $k^{th}$ powers of the divisors of $n$. For $k = 0$, it simplifies to the d-count function, $\sigma_0(n)$, counting the number of divisors of $n$. When $k = 1$, it becomes the sum of divisors function, $\sigma_1(n)$.

   $$ \sigma_k(n) = \sum_{d | n} d^k $$

2. **Euler's Totient Function ($\phi(n)$)**: It counts the totality of integers up to $n$ that are coprime to $n$. Coprime numbers share no common factors other than 1.

   $$ \phi(n) = n \prod_{p | n} \left(1 - \frac{1}{p}\right) $$

   Here, the product runs over all distinct prime factors $p$ of $n$.

3. **Möbius Function ($\mu(n)$)**: This function takes three distinct values based on the prime factorization of $n$. It is $1$ if $n$ is a square-free positive integer with an even number of prime factors, $-1$ if $n$ is a square-free positive integer with an odd number of prime factors, and $0$ if $n$ has a squared prime factor.

   $$ \mu(n) = 
   \begin{cases} 
   1 & \text{if } n \text{ is a square-free positive integer with an even number of prime factors}, \\
   -1 & \text{if } n \text{ is a square-free positive integer with an odd number of prime factors}, \\
   0 & \text{if } n \text{ has a squared prime factor}.
   \end{cases} $$

Arithmetical functions play a pivotal role in unraveling the mysteries of numbers, often surfacing in the study of prime numbers, [[Partition theory]], and analytic number theory. They are a testament to the elegance and depth of mathematical inquiry.  

Some arithmetical functions can also be formed as [[Dirichlet Characters]]

