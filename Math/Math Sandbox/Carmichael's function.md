Carmichael's function, denoted as $\lambda(n)$, is a number-theoretic function that plays a crucial role in the field of abstract algebra, particularly in the study of modular arithmetic and group theory. It is named after the mathematician Robert Carmichael. This function shares a close relationship with Euler's totient function $\varphi(n)$, but is distinct in several key aspects.

### Definition

Carmichael's function is defined for any positive integer $n$ as the smallest positive integer $m$ such that
$$
a^m \equiv 1 \pmod{n}
$$
for every integer $a$ that is coprime to $n$ (i.e., $\gcd(a, n) = 1$). 

### Properties

1. **Relation to Euler's Totient Function**: For any positive integer $n$, $\lambda(n)$ divides $\varphi(n)$. This is because if $a^{\varphi(n)} \equiv 1 \pmod{n}$ for all $a$ coprime to $n$ (Euler's theorem), then $\lambda(n)$, being the smallest such exponent, must divide $\varphi(n)$.

2. **Composite Numbers**: For a composite number $n$ with prime factorization $n = p_1^{k_1} p_2^{k_2} \cdots p_r^{k_r}$, Carmichael's function can be calculated using the formula:
   $$
   \lambda(n) = \text{lcm}(\lambda(p_1^{k_1}), \lambda(p_2^{k_2}), \ldots, \lambda(p_r^{k_r}))
   $$
   where lcm denotes the least common multiple.

3. **Prime Powers**: For a prime power $p^k$, where $p$ is a prime and $k$ is a positive integer, $\lambda(p^k)$ has a specific form:
   - If $p = 2$ and $k > 2$, $\lambda(2^k) = 2^{k-2}$.
   - For odd primes $p$, $\lambda(p^k) = \varphi(p^k) = p^{k-1}(p-1)$.

4. **Multiplicative Function**: Carmichael's function is a multiplicative function, meaning that if $m$ and $n$ are coprime, then $\lambda(mn) = \text{lcm}(\lambda(m), \lambda(n))$.

### Applications

Carmichael's function is significant in the realm of cryptography, especially in algorithms that rely on modular exponentiation, such as RSA encryption. Understanding the properties of $\lambda(n)$ helps in determining the efficiency and security of these cryptographic systems. The function is also instrumental in the study of cyclic groups and in finding the order of elements in multiplicative groups modulo $n$.