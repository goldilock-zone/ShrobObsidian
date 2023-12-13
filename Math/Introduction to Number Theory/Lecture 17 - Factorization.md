# Introduction
Advanced Factorization in Number Theory

In number theory, advanced factorization techniques are essential for understanding the properties of integers and for solving various mathematical problems. This guide will explore some advanced factorization methods and their applications.

### Unique Factorization Theorem
The Unique Factorization Theorem states that every positive integer can be factored into a unique product of prime numbers, up to the order of factors. This fundamental theorem forms the basis for many factorization techniques.

### Prime Factorization
Prime factorization is the process of expressing a positive integer as a product of prime numbers. For example, the prime factorization of 24 is $2^3 \cdot 3$, indicating that it is composed of three 2s and one 3.

### Divisibility Tests
Divisibility tests help identify factors quickly. Some common divisibility tests include:
- Divisibility by 2: A number is divisible by 2 if its last digit is even (0, 2, 4, 6, 8).
- Divisibility by 3: A number is divisible by 3 if the sum of its digits is divisible by 3.
- Divisibility by 5: A number is divisible by 5 if its last digit is 0 or 5.

### Factorization Algorithms
Several algorithms exist for factoring large numbers efficiently. Two notable ones are:
1. **Trial Division**: This simple method involves testing potential divisors one by one. It is suitable for small numbers but inefficient for large ones.
2. **Pollard's Rho Algorithm**: An advanced algorithm that employs randomization to factorize integers. It works well for large semiprime numbers.

### Fermat's Factorization Method
Fermat's Factorization Method is based on the observation that if a number can be expressed as the difference of two squares, i.e., $N = a^2 - b^2$, then it can be factored as $(a - b)(a + b)$. This method is particularly useful for finding factors of composite numbers.

### Pollard's p-1 Algorithm
Pollard's p-1 Algorithm is designed to factorize composite numbers with a large prime factor, p. It relies on the fact that if $a^{p-1} \equiv 1 \pmod{p}$ for some positive integer a, then $\text{gcd}(a^{p-1}-1, N)$ is a non-trivial factor of N.

### Quadratic Sieve
- **Quadratic Sieve**
	The Quadratic Sieve is an integer factorization algorithm used to factor a composite number into its prime factors. This algorithm is particularly efficient for numbers with small to medium-sized prime factors. Let's explore the Quadratic Sieve algorithm step by step.
	
	**Step 1: Choose a Smoothness Bound**
	To start the Quadratic Sieve, we first select a smoothness bound, denoted as B. This bound determines the size of the prime factors we aim to find. We will search for prime factors smaller than or equal to B.
	
	**Step 2: Generate Quadratic Polynomials**
	Next, we generate quadratic polynomials of the form:
	$$
	f(x) = x^2 - N
	$$
	where N is the number we want to factor. We choose different values of x and compute the corresponding values of f(x). The objective is to find x values such that f(x) is a perfect square modulo some small prime factors.
	
	**Step 3: Build the Matrix**
	For each chosen x, we factor the integer $f(x)$ into its prime factors. If the factors are all smaller than or equal to B and form an even power of each prime factor, we record this factorization in a matrix. The matrix will have rows representing different x values and columns representing the prime factors.
	
	**Step 4: Solve the Matrix Equation**
	Now, we have a matrix filled with factorizations of $f(x)$, which is essentially a system of linear equations. We attempt to solve this system to find a linear combination of rows whose product equals a perfect square modulo N. We can use linear algebra techniques, such as Gaussian elimination, to solve this equation.
	
	**Step 5: Extract the Factors**
	Once we find a linear combination of rows that results in a perfect square modulo N, we can extract the factors. The perfect square can be expressed as a product of two integers, which are the factors of N.
	
	**Step 6: Repeat the Process**
	If the algorithm does not succeed in finding the factors, we can repeat the process with different choices of x values and continue until we factor the composite number N completely.
	
	**Complexity and Optimizations**
	The efficiency of the Quadratic Sieve depends on the choice of the smoothness bound B and the size of the factor base. Various optimizations, such as selecting efficient x values, employing linear algebra techniques for matrix solving, and using a large enough factor base, can significantly improve the algorithm's performance.
	
	**Summary**
	The Quadratic Sieve is a powerful integer factorization algorithm used to factor composite numbers into their prime factors. By generating quadratic polynomials, building a matrix of factorizations, solving a system of linear equations, and extracting factors, it can efficiently factorize numbers with small to medium-sized prime factors. The choice of smoothness bound and factor base, as well as various optimizations, play crucial roles in its success.

### Elliptic Curve Factorization
Elliptic Curve Factorization is an advanced technique that uses elliptic curves over finite fields to factorize integers. This method is particularly effective for numbers with no small prime factors.

### Applications
Factorization plays a crucial role in various areas of mathematics and computer science, including:
- Cryptography: Factoring large semiprime numbers is computationally difficult and forms the basis of security for many encryption schemes.
- Number Theory: Understanding the properties of prime factors helps solve Diophantine equations and explore divisibility properties.
- Algorithms: Efficient factorization algorithms are essential for solving complex mathematical problems and optimizing computer algorithms.

In conclusion, advanced factorization techniques are indispensable tools in number theory and have far-reaching applications in various fields. These methods enable us to explore the properties of integers, solve mathematical equations, and ensure the security of modern cryptography.

# Pollard's Rho Method
**Pollard's Rho Method**

Pollard's Rho method is an algorithm used for integer factorization. It is particularly efficient when dealing with composite numbers with small prime factors. The method is based on the idea of finding a non-trivial factor of a composite number by studying the behavior of a certain sequence of numbers.

**Floyd's Cycle Detection Algorithm**

Pollard's Rho method employs Floyd's cycle detection algorithm to identify cycles in a sequence of numbers generated by a specific function. The function used is typically a recurrence relation that depends on the current value of the sequence.

Floyd's cycle detection algorithm works as follows:

1. We start with two pointers, often referred to as "tortoise" and "hare," initialized to the same value in the sequence.

2. In each iteration, the tortoise advances one step at a time, while the hare advances two steps at a time within the sequence.

3. If the sequence contains a cycle, the hare will eventually catch up to the tortoise. This happens because the hare moves twice as fast, and if it enters the cycle, it will loop around and meet the tortoise within the cycle.

4. Once the hare and tortoise meet, we have detected a cycle in the sequence.

**Application in Pollard's Rho Method**

In the context of Pollard's Rho method, the sequence of numbers is generated using a function related to the modular arithmetic of the composite number to be factored. The function can be represented as:

$$
f(x) = (x^2 + c) \mod n
$$

Here, $x$ is the current value in the sequence, $c$ is a randomly chosen constant, and $n$ is the composite number we want to factor.

The idea is to generate a sequence of values by repeatedly applying the function $f(x)$ and use Floyd's cycle detection algorithm to find a cycle in the sequence. Once a cycle is detected, we can derive information about the factors of $n$.

**Using Floyd's Cycle Detection in Pollard's Rho Method**

1. Start with two pointers, tortoise and hare, both initialized to the same value $x_0$.

2. In each iteration, calculate $x_{\text{tortoise}} = f(x_{\text{tortoise}})$ and $x_{\text{hare}} = f(f(x_{\text{hare}}))$.

3. Continue iterating until the tortoise and hare pointers meet. When they meet, we have found a cycle in the sequence.

4. Once a cycle is detected, we can use it to derive information about the factors of $n$. The length of the cycle can provide valuable information about the factors.

   - If the cycle length is even, we can use the greatest common divisor (GCD) of $n$ and $|x_{\text{tortoise}} - x_{\text{hare}}|$ to find a non-trivial factor of $n$.
   
   - If the cycle length is odd, we may need to try a different value of $c$ and repeat the process.

**Closing Thoughts**

Pollard's Rho method, along with Floyd's cycle detection algorithm, offers an efficient way to factor composite numbers. By exploiting the properties of modular arithmetic and detecting cycles in a sequence generated by a specific function, we can make progress towards finding the prime factors of a composite number, contributing to the field of number theory and cryptography.

# Birthday Paradox
The Birthday Paradox

The Birthday Paradox is a classic problem in probability theory that explores the likelihood of two or more people sharing the same birthday in a group. The problem statement is as follows:

**Problem Statement**: In a group of *n* people, what is the probability that at least two people share the same birthday?

Let's approach this problem using probability theory and combinatorics.

**Assumptions**:
1. We assume that each person's birthday is equally likely to fall on any of the 365 days of the year (ignoring leap years).
2. We also assume that each person's birthday is independent of the others.

**Solution**:

To solve this problem, we can consider the complementary probability, i.e., the probability that no one shares a birthday. Then, we subtract this probability from 1 to get the probability that at least two people share a birthday.

1. Probability that the first person has a unique birthday: There are 365 possible birthdays, so the probability that the first person has a unique birthday is 1.

2. Probability that the second person has a unique birthday: Since there are 365 days, the probability that the second person has a birthday different from the first is (365 - 1) / 365.

3. Probability that the third person has a unique birthday, given that the first two have unique birthdays: Now, there are two people with unique birthdays, so the probability that the third person has a birthday different from the first two is (365 - 2) / 365.

We continue this process until we consider all *n* people.

Therefore, the probability that all *n* people have unique birthdays is given by:

$$
\frac{365}{365} \cdot \frac{364}{365} \cdot \frac{363}{365} \cdot \ldots \cdot \frac{(365 - n + 1)}{365}
$$

Now, the probability that at least two people share a birthday is the complement of the above probability:

$$
1 - \frac{365}{365} \cdot \frac{364}{365} \cdot \frac{363}{365} \cdot \ldots \cdot \frac{(365 - n + 1)}{365}
$$

We can use this formula to calculate the probability for different values of *n*.

**Observations**:

1. As *n* increases, the probability that at least two people share a birthday also increases rapidly. This is the surprising aspect of the Birthday Paradox.
2. The probability exceeds 50% when *n* is relatively small, around 23.

**Discussion**:

The Birthday Paradox highlights the counterintuitive nature of probability. It's natural to think that in a group of 23 people, the probability of two sharing a birthday would be quite low, but it's actually greater than 50%. This paradox has practical applications in fields like cryptography and random number generation.

**Related Theorems and Concepts**:

1. **Complementary Probability**: The solution to the Birthday Paradox is based on the concept of complementary probability, where we calculate the probability of the event not happening and then subtract it from 1 to find the probability of the event occurring.

2. **Pigeonhole Principle**: The Birthday Paradox is an application of the pigeonhole principle, which states that if you have more objects to put into boxes than there are boxes, at least one box must contain more than one object.

3. **Binomial Coefficient**: The probability calculation involves multiplying several fractions. This is akin to choosing combinations, and it relates to binomial coefficients.

4. **Exponential Growth**: The rapid increase in the probability as *n* grows is an example of exponential growth, a fundamental concept in mathematics.

In summary, the Birthday Paradox is a fascinating problem in probability theory that demonstrates how our intuitions about probability can be deceiving. It also showcases the power of combinatorics and the pigeonhole principle in solving real-world problems.

# Soft Pigeonhole principle leading to Pollard's Rho Algorithm

Pollard's Rho algorithm is a probabilistic algorithm used for integer factorization. It is designed to find a nontrivial factor of a composite number $n$ by using a pseudorandom sequence and a detection of a cycle in this sequence. The basic idea relies on the birthday paradox, which implies that in a group of randomly chosen numbers, some pair of them will have a certain property (in this case, a nontrivial common factor with $n$) with a reasonably high probability.

The meta argument in the title seems to be related to the expected number of steps before such a pair is found. Let's use $p$ to denote the smallest prime factor of $n$. The heuristic argument is that once you have a set $A$ of group elements created by the algorithm (typically modulo $n$), the probability of two randomly chosen elements having the same property (leading to a nontrivial gcd with $n$) increases.

The notation $U_1, U_2, \ldots, U_k$ represent the sequence of values (or 'states') generated by the pseudorandom function used in the algorithm. The claim seems to be that after about $\sqrt{p}$ steps, the probability of finding a pair $(U_i, U_j)$ that leads to the discovery of the factor $p$ is reasonably high.

In the context of Pollard's Rho, the $\sqrt{p}$ arises from the birthday paradox, where the expected number of random draws (with replacement) from a set of $p$ elements to obtain a repeat is approximately $\sqrt{\pi p/2}$, often approximated as $\sqrt{p}$ for large $p$.

The "reasonable chance" part of the argument is generally taken to mean a probability that is better than a mere guess, often interpreted as over 50%. Thus, after approximately $\sqrt{p}$ steps, the probability of the algorithm succeeding in finding a factor is high enough to consider it efficient for that range of $p$.

In formal terms, if $k$ is the number of steps taken, then we want to find $k$ such that:

$$
P(\text{success after } k \text{ steps}) \geq \text{desired probability}
$$

According to the heuristic and empirical evidence, setting $k \approx \sqrt{p}$ gives a good balance between running time and probability of success.


$$
k \approx \sqrt{p}
$$

where $k$ is the number of iterations needed and $p$ is the smallest prime factor of $n$ that we are trying to find.


# Example of Pollard Rho
The algorithm uses a function \( f(x) \) to generate a sequence of values, and by computing the greatest common divisor (gcd) of differences of these values, it attempts to find a nontrivial factor of the number in question.

In this case, the function used is \( f(x) = x^2 + 1 \). The algorithm iteratively computes values \( U_i \) using this function and a chosen starting value. The gcd of differences between these computed values and the number to factor (7913 in this case) is then taken to check for a factor. When the gcd is a number greater than 1 and less than the number itself, a nontrivial factor has been found.

The note shows that when comparing \( U_{14} \) and \( U_{7} \), as well as \( U_{13} \) and \( U_{6} \), the gcd of their differences with 7913 is 41, which is a factor of 7913.

Here's a detailed breakdown in mathematical format:

1. Choose a function \( f(x) \), for Pollard's Rho algorithm \( f(x) = x^2 + 1 \).
2. Start with an initial value, say \( U_2 = 2 \)
3. Compute the sequence \( U_i \) using the recursion \( U_{i+1} = f(U_i) \mod 7913 \).
4. Check the gcd of \( U_i - U_j \) with 7913 for various \( i \neq j \).
5. If \( \text{gcd}(U_i - U_j, 7913) \) is a factor of 7913, then it will be a nontrivial factor.

In the note, the specific values of \( U_i \) are not given, but two successful gcd computations are shown:

$$
\text{gcd}(U_{14} - U_{7}, 7913) = 41
$$
$$
\text{gcd}(U_{13} - U_{6}, 7913) = 41
$$

Since 41 is a factor of 7913, we can conclude that:

$$
7913 = 41 \times 193
$$

Thus, the algorithm successfully factors 7913 by finding one of its nontrivial factors. The full factorization of 7913 is the product of 41 and 193, both of which are prime numbers.

# Why is Pollard's Rho Method called so:
Pollard's Rho algorithm is named "Rho" because the pattern of the sequence of values it produces, when graphed, resembles the Greek letter rho ($\rho$). The algorithm typically uses a function that generates a sequence of values modulo $n$, the number to be factored. This function is iterated to produce a sequence that eventually enters a cycle, much like the tail and loop of the $\rho$ shape.

To visualize this, imagine plotting the sequence of values on a graph. Starting from some initial value $x_0$, we apply the function $f(x)$ to generate the next value in the sequence. This process is repeated, and due to the modular arithmetic involved, the sequence will eventually repeat because there are a finite number of possible residues mod $n$. When the sequence enters this loop, we have the cycle that resembles the loop of the $\rho$.

Mathematically, the detection of the cycle uses Floyd's cycle-finding algorithm, which requires two pointers moving through the sequence at different speeds, often called the "tortoise and the hare." When they meet, it indicates the presence of a cycle.

The function $f(x)$ typically used in Pollard's Rho algorithm is $f(x) = x^2 + c \mod n$, where $c$ is a constant chosen to avoid fixed points and $n$ is the integer to factor. The sequence of values $x_0, x_1, x_2, \ldots$ will at some point repeat a value, and the difference between two of these values, say $x_i$ and $x_j$, will have a nontrivial greatest common divisor with $n$ with high probability. This is due to the Birthday Paradox, which suggests that in a set of $N$ randomly chosen numbers, some pair will match with a probability that increases significantly with $N$.

In terms of theorems and lemmas, the algorithm implicitly uses the property that if $a^2 \equiv b^2 \mod n$ and $a \not\equiv \pm b \mod n$, then $\gcd(a-b, n)$ is a nontrivial factor of $n$. The expected running time of Pollard's Rho is $O(\sqrt{p})$, where $p$ is the smallest prime factor of $n$, derived from the random walk in a finite group induced by $f(x)$.

Considering the algorithm's reliance on cycle detection and modular arithmetic, one might ask how different choices of the function $f(x)$ and the constant $c$ affect the efficiency and success rate of the algorithm. Also, under what conditions would Pollard's Rho method be less efficient than other factoring algorithms, and how does the size of the smallest prime factor influence the number of iterations required before a cycle is detected?

# Pollard's p-1 Method
Pollard's $p-1$ method is a factorization algorithm used to find non-trivial factors of composite integers. It is particularly effective when one of the factors has a small prime factor, denoted as $p$, and when $p-1$ is composed of only small prime factors. The method is based on Fermat's Little Theorem, which states that if $p$ is a prime number and $a$ is an integer not divisible by $p$, then $a^{p-1} \equiv 1 \pmod{p}$.

The algorithm proceeds as follows:

1. Select a random integer $a$.
2. Compute $d = \text{gcd}(a^{p-1} - 1, N)$, where $N$ is the composite integer to be factored.
3. If $d$ is a non-trivial factor of $N$, then we have successfully found a factor of $N$, and the algorithm terminates.
4. If $d$ is equal to $1$, increment the value of $a$ and repeat steps 2 and 3 until a non-trivial factor is found or until a maximum number of iterations is reached.

The key idea behind Pollard's $p-1$ method is that if $p-1$ has a small prime factor, then $a^{p-1} - 1$ will be a multiple of that prime factor. Thus, the greatest common divisor ($\text{gcd}$) calculation in step 2 is likely to yield a non-trivial factor of $N$.

It's important to note that Pollard's $p-1$ method may not always succeed in finding factors, especially if $p$ is large or if $p-1$ does not have small prime factors. In such cases, other factorization methods like the Quadratic Sieve or Pollard's Rho method may be more effective.

Now, let's address some questions related to Pollard's $p-1$ method:

**Q1:** How does the choice of the random integer $a$ affect the success of the algorithm?

**A1:** The choice of the random integer $a$ can significantly impact the success of the algorithm. If $a$ is poorly chosen, it may not lead to the discovery of a non-trivial factor. Ideally, $a$ should be selected with some randomness to maximize the chances of finding a factor. In practice, multiple trials with different values of $a$ may be conducted to increase the likelihood of success.

**Q2:** Is there a limit to the size of $p$ that Pollard's $p-1$ method can handle effectively?

**A2:** Yes, there is a practical limit to the size of $p$ that Pollard's $p-1$ method can handle effectively. If $p$ is very large, then $a^{p-1}$ becomes a huge number, making the computation in step 2 computationally infeasible. Therefore, the method is most effective when $p$ is a small prime or has small prime factors.

**Q3:** Are there any theoretical guarantees regarding the runtime of Pollard's $p-1$ method?

**A3:** Pollard's $p-1$ method does not have guaranteed runtime bounds. The algorithm's performance depends on the choice of $a$ and the properties of the composite integer $N$. In some cases, a factor may be found quickly, while in other cases, it may take a long time or may not find a factor at all. The algorithm's runtime is probabilistic and can vary widely.

In summary, Pollard's $p-1$ method is a useful factorization algorithm for finding non-trivial factors of composite integers with small prime factors. Its success depends on the choice of $a$ and the properties of the integer being factored, and it does not have guaranteed runtime bounds.

# Smoothness in Primes
**Smoothness in the Context of Primes**

In number theory, the concept of "smoothness" plays a crucial role when studying the distribution of prime numbers. Smooth numbers are integers that have only small prime factors, making them important in various mathematical algorithms and cryptographic applications. To understand smoothness in the context of primes, we will explore its definition and significance.

**Definition of Smooth Numbers:**

A positive integer $n$ is said to be "smooth" if all its prime factors are relatively small. More formally, for a given positive integer $n$, we say that $n$ is $B$-smooth if and only if all its prime factors are less than or equal to a certain threshold $B$. In mathematical notation, we can express this as:

$$
n \text{ is } B\text{-smooth} \iff \text{all prime factors of } n \text{ are }\leq B
$$

**Significance of Smooth Numbers:**

Smooth numbers have several important applications in number theory and computational mathematics:

1. **Factorization Algorithms:** Smooth numbers are fundamental in integer factorization algorithms, such as the Quadratic Sieve and Pollard's $p-1$ method. These algorithms are used to factorize large composite numbers into their prime factors. Smooth numbers are essential in the sieving process, where they help identify potential factors.

2. **Cryptographic Security:** In cryptography, the RSA encryption algorithm relies on the difficulty of factoring the product of two large prime numbers. Smooth numbers can be used in attacks against RSA when the encryption parameters are not chosen carefully. Therefore, understanding smoothness is crucial for ensuring the security of cryptographic systems.

3. **Prime Number Distribution:** Studying smooth numbers provides insights into the distribution of prime numbers. Prime numbers are, by definition, not smooth, as they only have two distinct factors: 1 and themselves. Analyzing the density of smooth numbers helps mathematicians understand the gaps between prime numbers and develop conjectures like the Prime Number Theorem.

**Questions to Explore:**

1. How does the concept of smoothness relate to the Fundamental Theorem of Arithmetic, which states that every positive integer can be uniquely represented as a product of prime numbers?

2. Are there any known results or theorems that provide bounds on the density of smooth numbers as a function of their size or smoothness threshold?

3. In cryptography, how does the choice of smooth numbers (or their absence) impact the security of encryption schemes like RSA? Are there any specific strategies to mitigate vulnerabilities related to smoothness?

4. Can smooth numbers be efficiently generated or identified within a given range, and how does this process connect with factorization algorithms?

# Fermat's Theorem of Factorization
Fermat's Little Theorem states that if $p$ is a prime number and $a$ is an integer not divisible by $p$, then $a^{p-1} \equiv 1 \mod p$. This theorem can be used in various ways for primality testing and factorization.

The method shown seems to involve picking a large number $M$ which is the product of many small primes. In the context of factorization, a common strategy is to find a number $a$ such that $a^2 \equiv 1 \mod M$, because this means that $(a-1)(a+1)$ is a multiple of $M$. If $a$ is chosen randomly and $a^2 - 1$ is a multiple of $M$, then the greatest common divisor (gcd) of $a-1$ and $M$ may yield a non-trivial factor of $M$.

To elaborate, if $M$ is the number to be factored, and we can find an $a$ such that $a^2 - 1 = (a-1)(a+1)$ is a multiple of $M$, then computing $\gcd(a-1, M)$ or $\gcd(a+1, M)$ could give us a factor of $M$. This is because $a-1$ and $a+1$ are consecutive even numbers and one of them might share a factor with $M$.

This factorization method can be efficient if $M$ is a product of two primes that are close together, as then $a$ can be found such that $a-1$ and $a+1$ straddle the two prime factors.

To use this method:
1. Choose a number $M$ to be factored.
2. Pick a random number $a$.
3. Compute $a^2 - 1$.
4. Calculate $\gcd(a-1, M)$ and $\gcd(a+1, M)$.
5. If either gcd is not 1 or $M$, then it is a non-trivial factor of $M$.

Keep in mind that this is a probabilistic method and may need to be repeated several times with different choices of $a$ to find a factor. It is part of a larger set of algorithms known as "Fermat's factorization method", which is generally used for numbers that are a product of two primes that are close to each other.

# Elliptic Curve Factorization
Elliptic curve factorization is a method of finding a non-trivial factor of a composite number $N$ using properties of elliptic curves. The basic idea is to use an elliptic curve $E$ over the ring $\mathbb{Z}/N\mathbb{Z}$ and a point $P$ on $E$. If $N$ is not prime, certain operations with $P$ can reveal a factor of $N$.

To understand the process, let's review some background on elliptic curves. An elliptic curve over $\mathbb{Z}/N\mathbb{Z}$ is given by an equation of the form
$$
y^2 \equiv x^3 + ax + b \mod N
$$
where $4a^3 + 27b^2 \not\equiv 0 \mod N$ to ensure that the curve is non-singular.

The factorization method involves the following steps:

1. **Choose an Elliptic Curve and a Point**: Select coefficients $a$ and $b$ such that $4a^3 + 27b^2 \not\equiv 0 \mod N$. Choose a point $P = (x, y)$ on the curve.

2. **Scalar Multiplication**: Compute a multiple of $P$, say $kP$, for some large integer $k$. The process of scalar multiplication involves adding $P$ to itself $k$ times. 

3. **Detecting a Non-trivial Factor**: While performing scalar multiplication, we may encounter a non-invertible element in $\mathbb{Z}/N\mathbb{Z}$. If, during the computation, we need to calculate $1/d$ mod $N$ and find that $\gcd(d, N) \neq 1$ and $d \neq N$, then we have discovered a non-trivial factor of $N$.

Let's go through the scalar multiplication step in more detail, as this is where the factorization occurs. For two points $P = (x_1, y_1)$ and $Q = (x_2, y_2)$ on $E$, the sum $P + Q = (x_3, y_3)$ is given by:

- If $P \neq Q$, then 
$$
\lambda \equiv \frac{y_2 - y_1}{x_2 - x_1} \mod N, \quad x_3 \equiv \lambda^2 - x_1 - x_2 \mod N, \quad y_3 \equiv \lambda(x_1 - x_3) - y_1 \mod N.
$$

- If $P = Q$, then
$$
\lambda \equiv \frac{3x_1^2 + a}{2y_1} \mod N, \quad x_3 \equiv \lambda^2 - 2x_1 \mod N, \quad y_3 \equiv \lambda(x_1 - x_3) - y_1 \mod N.
$$

In both cases, if the denominator of $\lambda$ is not invertible mod $N$, we compute $\gcd(denominator, N)$. If the gcd is greater than $1$ and less than $N$, it is a non-trivial factor of $N$.

A crucial aspect of this method is the random selection of elliptic curves and starting points because some choices of $E$ and $P$ might not lead to factorization for a given $N$. The method is probabilistic and may require several attempts with different curves and points. 

# Elliptic Curve Factorization: Example
Let's consider a concrete example of elliptic curve factorization. We will attempt to find a non-trivial factor of a composite number $N$ using an elliptic curve $E$ and a point $P$ on $E$. For simplicity, let's take $N = 91$, which is a composite number ($7 \times 13$).

Step 1: Choose an Elliptic Curve and a Point
---
We'll define an elliptic curve $E$ over $\mathbb{Z}/91\mathbb{Z}$ with the equation $y^2 \equiv x^3 + ax + b \mod 91$. We choose $a = 1$ and $b = 1$ for simplicity, ensuring that $4a^3 + 27b^2 \not\equiv 0 \mod 91$ to avoid a singular curve. We then select a point $P = (x, y)$ on $E$. Let's take $P = (0, 1)$, which is on $E$ since $1^2 \equiv 0^3 + 0 + 1 \mod 91$.

Step 2: Scalar Multiplication
---
We will perform scalar multiplication of $P$ by an integer $k$. For demonstration, let's choose $k = 2$, so we need to calculate $2P = P + P$.

Step 3: The Doubling Formula
---
Since we are adding $P$ to itself, we use the doubling formula:
$$
\lambda \equiv \frac{3x^2 + a}{2y} \mod N
$$
For our point $P = (0, 1)$, we compute:
$$
\lambda \equiv \frac{3 \cdot 0^2 + 1}{2 \cdot 1} \equiv \frac{1}{2} \mod 91
$$
Here, we encounter an issue: $2$ has no multiplicative inverse mod $91$ because $\gcd(2, 91) = 1$. Normally, we would need to calculate $1/2$ mod $91$, but we can't. So instead, we compute:
$$
\gcd(2, 91)
$$
Upon calculation, we find $\gcd(2, 91) = 1$, which does not give us a factor. Hence, we would continue with other values or methods to find the multiplicative inverse of $2$ mod $91$. In this case, we know that $91$ is odd, so we can find an integer $k$ such that $2k \equiv 1 \mod 91$. Let's say we've found that $k = 46$ fulfills this condition.

Now we can compute $\lambda$:
$$
\lambda \equiv 46 \cdot 1 \equiv 46 \mod 91
$$
And then calculate $x_3$ and $y_3$ for $2P$:
$$
x_3 \equiv \lambda^2 - 2x_1 \mod 91
$$
$$
x_3 \equiv 46^2 - 2 \cdot 0 \mod 91
$$
$$
x_3 \equiv 2116 \mod 91
$$
$$
x_3 \equiv 56 \mod 91
$$
And for $y_3$:
$$
y_3 \equiv \lambda(x_1 - x_3) - y_1 \mod 91
$$
$$
y_3 \equiv 46(0 - 56) - 1 \mod 91
$$
$$
y_3 \equiv -46 \cdot 56 - 1 \mod 91
$$
$$
y_3 \equiv -2576 \mod 91
$$
$$
y_3 \equiv -64 \mod 91
$$
$$
y_3 \equiv 27 \mod 91
$$
So, $2P = (56, 27)$. If at any point during these calculations we encountered a non-invertible element in $\mathbb{Z}/91\mathbb{Z}$ and the gcd was not $1$ or $91$, we would have found a non-trivial factor of $91$.

This process can be repeated with larger multiples of $P$ or different points and curves until a factor is found. Since this is a probabilistic algorithm, there's no guarantee of success on the first try or any specific number of tries. Would you like to continue with this example or see a different approach?