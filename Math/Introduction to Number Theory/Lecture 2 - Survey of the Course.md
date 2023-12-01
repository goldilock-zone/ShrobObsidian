<iframe width="893" height="558" src="https://www.youtube.com/embed/mduJOLdKrak?list=PL8yHsr3EFj53L8sMbzIhhXSAOpuZ1Fov8" title="Introduction to number theory lecture 2: Survey." frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

**Congruences**: Some things can be very easily checked using modular arithmetic

# Fermat's Little Theorem
If \(p\) is a prime number and \(a\) is an integer not divisible by \(p\), then \(a^{p-1}\) is congruent to \(1\) modulo \(p\). In mathematical notation, this can be written as:

$$
a^{p-1} \equiv 1 \pmod{p}
$$
Here's what this theorem means:

1. \(p\) is a prime number: This condition specifies that \(p\) must be a prime number.

2. \(a\) is an integer not divisible by \(p\): The integer \(a\) should be relatively prime to \(p\), meaning that they have no common factors other than 1. In other words, \(a\) and \(p\) are coprime.

3. \(a^{p-1}\) is congruent to \(1\) modulo \(p\): This part of the theorem states that when you raise the integer \(a\) to the power of \(p-1\) and then take the result modulo \(p\), the remainder will always be \(1\).

Fermat's Little Theorem is a powerful tool in number theory and modular arithmetic. It has many applications, including in primality testing algorithms and cryptography. It forms the basis for various cryptographic protocols, such as the RSA algorithm, which is widely used in secure communication and encryption.

# Aside: Euler's Totient Function

Instead of: \( \phi(n) \), use: $$ \phi(n) $$

The Euler Totient function, denoted as \( \phi(n) \), is a mathematical function that counts the number of positive integers less than or equal to \( n \) that are relatively prime (coprime) to \( n \). In other words, it calculates the number of integers from 1 to \( n \) that share no common factors (other than 1) with \( n \).

The formula for Euler's Totient function is:

$$
\phi(n) = n \left(1 - \frac{1}{p_1}\right) \left(1 - \frac{1}{p_2}\right) \cdots \left(1 - \frac{1}{p_k}\right)
$$

Where:
- \( n \) is the positive integer for which you want to calculate \( \phi(n) \).
- \( p_1, p_2, \ldots, p_k \) are the distinct prime factors of \( n \).

To calculate \( \phi(n) \), you find all the prime factors of \( n \), subtract the reciprocal of each prime factor from 1, and then multiply these values together along with \( n \).

For example, if \( n = 10 \), the prime factorization is \( 10 = 2 \cdot 5 \). Using the formula:

$$
\phi(10) = 10 \left(1 - \frac{1}{2}\right) \left(1 - \frac{1}{5}\right) = 10 \cdot \frac{1}{2} \cdot \frac{4}{5} = 2 \cdot 4 = 8
$$

So, \( \phi(10) = 8 \), which means there are 8 positive integers less than or equal to 10 that are relatively prime to 10: {1, 3, 7, 9}.

# Euler's Totient Function as an analog of Fermat's Little Theorem

Fermat's Little Theorem states that for a prime number \(p\) and an integer \(a\) not divisible by \(p\):
$$
a^{p-1} \equiv 1 \pmod{p}
$$

Now, using Euler's Totient Function, you can generalize this result for any positive integer \(n\), not just prime numbers. The analog of Fermat's Little Theorem using Euler's Totient Function is:

If \(a\) is an integer coprime (relatively prime) to \(n\), then:
$$
[a^{\phi(n)} \equiv 1 \pmod{n}
$$

Where \(\phi(n)\) is Euler's Totient Function, which counts the number of positive integers less than or equal to \(n\) that are relatively prime to \(n\).

This generalization allows you to apply a similar concept to non-prime moduli. It states that if \(a\) is coprime to \(n\), then raising \(a\) to the power of \(\phi(n)\) and taking the result modulo \(n\) will yield \(1\). This property is useful in various number theoretic and cryptographic applications.

# Test if N is prime


$$
\text{Test if } N \text{ is prime}
$$

To test if \( N \) is prime using Fermat's Little Theorem:

1. Choose an integer \( a \) such that \( 1 < a < N \).

2. Compute \( a^{N-1} \) modulo \( N \) using modular exponentiation.

3. If the result is congruent to \( 1 \) modulo \( N \), then \( N \) may be prime (with high probability).

4. Repeat the test with different values of \( a \) to increase confidence in the result.

If \( a^{N-1} \) is not congruent to \( 1 \) modulo \( N \) for any chosen \( a \), then \( N \) is definitely composite. If \( a^{N-1} \) is congruent to \( 1 \) modulo \( N \) for multiple values of \( a \), it's still possible that \( N \) is composite, and further testing may be required using a probabilistic primality test like the Miller-Rabin test.

This is a basic approach to primality testing using Fermat's Little Theorem, but it's important to note that there are more efficient and reliable algorithms available for practical primality testing, especially for large numbers.

# Miller Rabin Test

^b62d2d

1. **Representation of \( n \):** 
   If \( n \) is prime and \( n > 2 \), it can be written as 
   $$
   n = 2^s \cdot d + 1
   $$
   where \( d \) is odd. This represents \( n-1 \) as a product of a power of two and an odd number.

2. **Randomness:** 
   The test picks a random number \( a \) such that 
   $$
   2 \leq a \leq n-2.
   $$

3. **Modular Exponentiation:** 
   Compute 
   $$
   x = a^d \mod n.
   $$
   If \( x = 1 \) or \( x = n-1 \), \( n \) passes this round of the test.

4. **Squaring:** 
   Square \( x \) and take the result modulo \( n \), i.e., 
   $$
   x = x^2 \mod n.
   $$
   If \( x = n-1 \), \( n \) passes this round of the test.

5. **Iteration:** 
   Repeat the squaring step \( s-1 \) times. If none of these iterations result in \( x = n-1 \), then \( n \) is composite.

6. **Probability:** 
   If \( n \) passes several rounds of the test with different values of \( a \), it is likely prime. The more rounds \( n \) passes, the higher the confidence in its primality. The error probability decreases exponentially with the number of rounds, typically being less than 
   $$
   2^{-k}
   $$
   after \( k \) independent rounds.

# Hasse Principle
The Hasse Principle, named after the German mathematician Helmut Hasse, is a fundamental concept in number theory, particularly in the study of Diophantine equations. It relates to the solvability of equations over global fields (like rational numbers) and their local fields (like \( p \)-adic numbers). In the context of prime numbers, the Hasse Principle can be intriguingly applied, though it's more commonly associated with quadratic forms and elliptic curves.

- Aside: [[Global and Local Fields]]

Let's explore the Hasse Principle with a focus on its relationship to prime numbers:

1. **Hasse Principle for Quadratic Forms:**
   A classical application of the Hasse Principle is for quadratic forms. It states that a quadratic form over the rational numbers has a non-trivial solution if and only if it has a non-trivial solution in all \( p \)-adic completions of the rational numbers and in the real numbers. Here, \( p \) represents a prime number, and each \( p \)-adic field is a local field associated with that prime.

2. **Hasse Principle and Primes:**
   When considering the Hasse Principle in relation to primes, we look at the solvability of equations modulo various primes. If an equation has solutions in all \( p \)-adic fields for all primes \( p \) (and in the reals), the Hasse Principle would suggest that it should have a solution in the rational numbers. However, the principle does not always hold. There are notable counterexamples, especially in the context of elliptic curves and higher degree forms.

3. **Counterexamples and Birch–Swinnerton-Dyer Conjecture:**
   One of the famous counterexamples to the Hasse Principle involves certain elliptic curves. The Birch–Swinnerton-Dyer conjecture, a major unsolved problem in number theory, gives a deep insight into the relationship between the rank of an elliptic curve and the behavior of its L-function at \( s = 1 \). This conjecture and the study of elliptic curves over global fields shed light on the limitations of the Hasse Principle, particularly in cases involving prime numbers and their properties.

4. **Brauer–Manin Obstruction:**
   The Brauer–Manin obstruction is an advanced concept that provides a framework for understanding some of the failures of the Hasse Principle. It uses algebraic and analytic methods to investigate the solvability of Diophantine equations, considering obstructions arising from the Brauer group of a variety.

In conclusion, while the Hasse Principle provides a powerful tool for understanding the solvability of equations over global fields based on their solvability over local fields, its application in the context of primes, especially in more complex scenarios like elliptic curves, can reveal its limitations and the need for more sophisticated approaches.

## Aside: p-adic numbers
[[p-adic numbers]]

# Quadratic Residues and Quadratic Reciprocity Law

Quadratic residues and their behavior modulo a prime \( p \) form a fundamental aspect of number theory, particularly in the study of congruences and Diophantine equations. Let's delve into these concepts:

### Quadratic Residues

1. **Definition:**
   An integer \( a \) is a quadratic residue modulo \( p \) (where \( p \) is a prime) if there exists an integer \( x \) such that
   $$
   x^2 \equiv a \mod p.
   $$
   If no such \( x \) exists, then \( a \) is called a quadratic non-residue modulo \( p \).

2. **Properties:**
   - There are exactly \( \frac{p-1}{2} \) non-zero quadratic residues modulo \( p \).
   - The product of two quadratic residues or two non-residues is a residue, while the product of a residue and a non-residue is a non-residue.
   - If \( p \) is an odd prime, then \( -1 \) is a quadratic residue modulo \( p \) if and only if \( p \equiv 1 \mod 4 \).

3. **Example:**
   Consider \( p = 7 \). The quadratic residues modulo 7 are the squares of \( 1, 2, 3 \), namely \( 1^2 = 1, 2^2 = 4, 3^2 = 2 \) (mod 7). So, 1, 2, and 4 are quadratic residues modulo 7, while 3, 5, and 6 are non-residues.

### Legendre Symbol

The Legendre symbol is a convenient notation for working with quadratic residues. For an integer \( a \) and an odd prime \( p \), the Legendre symbol
$$ \left( \frac{a}{p} \right) $$ is defined as:
- \( 1 \) if \( a \) is a quadratic residue modulo \( p \) and \( a \not\equiv 0 \mod p \),
- \( -1 \) if \( a \) is a non-residue modulo \( p \),
- \( 0 \) if \( a \equiv 0 \mod p \).

### Euler's Criterion

Euler's Criterion provides a way to compute the Legendre symbol. It states that for an odd prime \( p \) and any integer \( a \),
$$
\left( \frac{a}{p} \right) \equiv a^{\frac{p-1}{2}} \mod p.
$$

### Law of Quadratic Reciprocity

This law, one of the most famous results in number theory, describes the relationship between the quadratic residues of two different odd primes. It states that for odd primes \( p \) and \( q \),
$$
\left( \frac{p}{q} \right) \left( \frac{q}{p} \right) = (-1)^{\frac{p-1}{2} \cdot \frac{q-1}{2}}.
$$

### Applications

Quadratic residues have applications in various areas of mathematics and computer science, including cryptography, coding theory, and the proof of various theorems in number theory. They also play a role in solving quadratic congruences and understanding the structure of the multiplicative group of integers modulo \( p \).

Understanding quadratic residues and their behavior modulo primes provides deep insights into the properties of numbers and forms the foundation for more advanced studies in algebraic number theory and arithmetic geometry.

- Note: Number Theory is looking for some hidden structure

# Additive Number Theory

Additive number theory, a branch of number theory, primarily focuses on the properties of integers under the operation of addition. This field investigates the ways in which numbers (especially integers) can be expressed as the sum of other numbers, and the properties of these representations. Here's an introduction to some key concepts and areas within additive number theory:

### 1. Sumsets

- **Definition:** The sumset of two sets of integers \( A \) and \( B \) is defined as the set \( A + B = \{ a + b : a \in A, b \in B \} \).
- **Example:** If \( A = \{1, 2\} \) and \( B = \{3, 4\} \), then \( A + B = \{4, 5, 6\} \).

### 2. Partition Theory

- **Focus:** This area studies the ways in which numbers can be partitioned into summands. 
- **Example:** The number 4 can be partitioned as \( 4, 3+1, 2+2, 2+1+1, 1+1+1+1 \).

### 3. Ramsey Theory
Notes: [[Ramsey Theory]]
- **Concept:** Part of additive number theory is concerned with Ramsey theory, which deals with conditions under which order or structure must appear.
- **Application:** It includes problems like the party problem: how many people must be at a party to guarantee that three of them either all know each other or none of them do?

### 4. Additive Bases

- **Definition:** A set of numbers \( A \) is an additive basis of order \( h \) if every sufficiently large integer can be written as the sum of \( h \) elements in \( A \).
- **Example:** The set of squares \( \{1, 4, 9, 16, \ldots\} \) is an additive basis of order 4 (Lagrange's four-square theorem).

### 5. Goldbach's Conjecture
 [[Attempts at solving Goldbach's Conjecture]]
- **Statement:** One of the most famous unsolved problems in additive number theory. It asserts that every even integer greater than 2 can be expressed as the sum of two primes.
- **Example:** \( 10 = 3 + 7 \), \( 12 = 7 + 5 \).

### 6. Waring's Problem 

Notes: [[Waring's Problem]]
- **Question:** Waring's problem asks if there exists a positive integer \( k \) such that every positive integer is the sum of at most \( k \) powers of \( n \)-th powers.
- **Result:** It's known that such a \( k \) exists for all \( n \), but determining the exact value of \( k \) for each \( n \) is a deep problem.

### 7. Density and Counting

- **Aspect:** Additive number theory also deals with the density of certain sets of integers and counting functions related to additive properties.
- **Example:** The density of prime numbers as described by the Prime Number Theorem. ^c16ae1

### 8. Connections to Other Areas

- **Combinatorics:** Many problems in additive number theory have a combinatorial nature.
- **Analytic Number Theory:** Tools from analysis are often used, like in studying the distribution of prime numbers.

### Conclusion

Additive number theory is rich with problems that range from elementary to highly complex, many of which have direct implications for other fields in mathematics and computer science. Its allure lies in the simplicity of its questions and the often surprising complexity of their answers.

## Aside: Arithmetic Progressions of Primes
Note: [[APs of Primes]]

# Recreational Number Theory
- Discrete Dynamical System
	- Discrete dynamical systems are a branch of mathematics used to model systems that evolve in discrete time steps, rather than continuously. These systems are defined by a function which describes how the state of the system changes at each step. Discrete dynamical systems are widely used in various fields including biology, economics, physics, and computer science, for modeling phenomena where changes occur at distinct intervals.
	
	### Basic Concept
	
	- **Definition:** A discrete dynamical system is described by a state space and a rule that specifies the next state of the system given its current state. Mathematically, if \( X \) is the state space, the dynamical system is defined by a function \( f: X \rightarrow X \). The state of the system at the \( n \)-th time step is given by \( f^n(x_0) \), where \( x_0 \) is the initial state and \( f^n \) is the \( n \)-th iterate of \( f \).
	
	### Key Features
	
	1. **Iterations:** The key operation in a discrete dynamical system is iteration, applying the function \( f \) repeatedly.
	
	2. **Fixed Points and Periodic Points:** A point \( x \) is a fixed point if \( f(x) = x \). A point is periodic with period \( n \) if \( f^n(x) = x \) and \( n \) is the smallest positive integer for which this holds.
	
	3. **Orbits:** The orbit of a point \( x \) under \( f \) is the sequence \( x, f(x), f^2(x), \ldots \). It represents the trajectory of the system from the initial state \( x \).
	
	4. **Stability:** A fixed or periodic point is stable if states close to it remain close under iteration, and unstable if they diverge.
	
	5. **Chaos:** In some systems, small changes in initial conditions can lead to drastically different outcomes, a phenomenon known as chaos.
	
	### Examples
	
	1. **Logistic Map:** A classic example in the study of chaos and nonlinear dynamics. The logistic map is defined by the equation \( x_{n+1} = r x_n (1 - x_n) \), where \( r \) is a parameter.
	
	2. **Population Models:** Models like the Leslie matrix in ecology, used to model changes in population demographics over time.
	
	3. **Economic Models:** Models of investment or consumption over time, where the system evolves in discrete time steps.
	
	### Applications
	
	- **Modeling Natural Phenomena:** Discrete dynamical systems are used to model biological processes, chemical reactions, and population dynamics.
	
	- **Computer Science:** In computer algorithms and computational models, discrete dynamical systems can describe the evolution of computational processes.
	
	- **Chaos Theory:** Understanding chaotic systems and their sensitive dependence on initial conditions.
	
	### Conclusion
	
	Discrete dynamical systems provide a powerful framework for understanding complex behaviors in systems that evolve over time. The study of these systems blends mathematical theory with practical applications, revealing intricate patterns and behaviors in a wide array of scientific and mathematical disciplines.
	Example: [[Collatz Conjecture]]


# Algebraic Number Theory
Algebraic number theory is a branch of mathematics that deals with the generalizations and extensions of the number system, focusing on the algebraic properties of numbers, particularly in the context of number fields and algebraic integers. This field blends concepts from algebra and number theory to explore a variety of problems about the nature and behavior of numbers beyond the familiar integers and rational numbers.

### Key Concepts and Topics

1. **Number Fields:**
   - **Definition:** A number field is a finite field extension of the rational numbers $$\mathbb{Q} $$ These are typically expressed as $$\mathbb{Q}(\alpha) $$, where \( \alpha \) is an algebraic number (a root of a non-zero polynomial equation with rational coefficients).
   - **Examples:** Quadratic fields of the form \( $$\mathbb{Q}(\sqrt{d}) $$\), where \( d \) is a square-free integer, are among the simplest examples.

2. **Algebraic Integers:**
   - **Definition:** These are generalizations of integers. An algebraic integer is a complex number that is a root of a monic polynomial (a polynomial whose leading coefficient is 1) with integer coefficients.
   - **Properties:** Algebraic integers form a ring within each number field.

3. **Ideals and Unique Factorization:**
   - **Concept:** In rings of algebraic integers, ideals play a critical role, particularly because unique factorization into prime elements does not always hold. However, unique factorization of ideals into prime ideals is always possible in these rings (Dedekind domains).

4. **Unit Group and Class Group:**
   - **Unit Group:** Consists of the invertible elements (units) in the ring of algebraic integers. It plays a crucial role in understanding the structure of these rings.
   - **Class Group:** A concept that measures the failure of unique factorization. It's trivial in rings with unique factorization.

5. **Diophantine Equations:**
   - **Application:** Algebraic number theory provides tools to solve Diophantine equations, which are polynomial equations with integer coefficients, seeking integer or rational solutions.

6. **Galois Theory:**
   - **Relation:** Galois theory helps in understanding the symmetry and structure of number fields, particularly through the study of field automorphisms.

7. **L-functions and Zeta Functions:**
   - **Advanced Tools:** Generalizations of the Riemann zeta function, like Dedekind zeta functions and L-functions, are used to explore the distribution of primes in number fields.

### Importance and Applications

- **Understanding Primes:** Algebraic number theory extends the study of prime numbers to more general settings.
- **Cryptographic Applications:** Concepts from algebraic number theory are used in modern cryptography, including public-key cryptosystems.
- **Theoretical Advances:** It provides insights into classical problems in number theory, such as Fermat’s Last Theorem, and into the structure and properties of numbers.

### Conclusion

Algebraic number theory is a rich and deep field, expanding the horizons of classical number theory into more abstract realms. It provides a framework for understanding numbers at a more fundamental level, revealing beautiful structures and properties that have significant implications both within mathematics and in practical applications like cryptography.


# Fermat's Theorem on Sums of Two Squares

#### Statement of the Theorem

Fermat's theorem on the sum of two squares states that:

- A prime number \( p \) can be expressed as the sum of two squares, 
  $$
  p = a^2 + b^2,
  $$
  where \( a \) and \( b \) are integers, if and only if \( p \) is of the form \( 4n + 1 \) or \( p = 2 \). In modular arithmetic terms, this can be written as:
  $$
  p \equiv 1 \mod 4 \quad \text{or} \quad p = 2.
  $$

#### Proof Concepts

1. **Proof Techniques:**
   - The proof involves elementary number theory, particularly modular arithmetic and quadratic residues.
   - An alternative proof uses the ring of Gaussian integers, \( $$ \mathbb{Z}[i] $$\), where factorization properties play a key role.

2. **Quadratic Residues:**
   - The theorem is related to the property of \( -1 \) being a quadratic residue modulo \( p \). Specifically, \( -1 \) is a quadratic residue modulo \( p \) if and only if 
     $$
     p \equiv 1 \mod 4.
     $$

#### Examples

- **For Prime \( p = 5 \):**
  $$
  5 = 1^2 + 2^2,
  $$
  since \( 5 \equiv 1 \mod 4 \).

- **For Prime \( p = 7 \):**
  There are no integers \( a \) and \( b \) such that 
  $$
  7 = a^2 + b^2,
  $$
  because \( 7 \equiv 3 \mod 4 \).

#### Extensions

- **Composite Numbers:**
  - A composite number can be expressed as the sum of two squares if and only if every prime factor of the form \( 4n + 3 \) occurs to an even power in its prime factorization.

- **Relation to Pythagorean Triples:**
  - This theorem has implications for Pythagorean triples, which are sets of three integers \( (a, b, c) \) satisfying 
    $$
    a^2 + b^2 = c^2.
    $$

### Conclusion

Fermat's theorem elegantly connects the worlds of prime numbers, quadratic forms, and modular arithmetic, showcasing the depth and interconnectivity of concepts within number theory.

# Formula for Partitions
The number of partitions of an integer is a fundamental concept in partition theory, a branch of combinatorial number theory. A partition of a positive integer \( n \) is a way of writing \( n \) as a sum of positive integers, where the order of the addends does not matter. The function that counts the number of partitions of \( n \) is denoted by \( p(n) \).

### Formula for \( p(n) \)

There isn't a simple closed-form expression for \( p(n) \), but there are various ways to compute or approximate it:

1. **Generating Function:**
   The generating function for \( p(n) \) is given by the infinite product:
   $$
   \sum_{n=0}^{\infty} p(n) x^n = \prod_{k=1}^{\infty} \frac{1}{1 - x^k}.
   $$
   This expression encapsulates the partition function but doesn't directly give the number of partitions for a specific \( n \).

2. **Recurrence Formula:**
   There's a recursive way to compute \( p(n) \) using earlier values of \( p \). Though not a closed-form formula, it's often used for computational purposes.

3. **Approximation by Hardy-Ramanujan Formula:**
   The Hardy-Ramanujan asymptotic formula provides an approximation for \( p(n) \) for large \( n \):
   $$
   p(n) \approx \frac{1}{4n\sqrt{3}} \exp\left(\pi \sqrt{\frac{2n}{3}}\right).
   $$
   This formula gives a good approximation for \( p(n) \) when \( n \) is large.

4. **Rademacher's Exact Formula:**
   Hans Rademacher provided an exact convergent series expression for \( p(n) \), improving upon the Hardy-Ramanujan formula. Rademacher's formula involves Dedekind eta function and Kloosterman sums, and it's quite complex:
   $$
   p(n) = \frac{1}{\pi \sqrt{2}} \sum_{k=1}^{\infty} A_k(n) \sqrt{k} \frac{d}{dn} \left( \frac{\sinh \left( \frac{\pi}{k} \sqrt{\frac{2}{3}(n - \frac{1}{24})} \right)}{\sqrt{n - \frac{1}{24}}} \right),
   $$
   where \( A_k(n) \) involves Kloosterman sums and is quite intricate to compute.

### Examples

- **Small Values:**
  - \( p(1) = 1 \) since the only partition of 1 is \( 1 \).
  - \( p(4) = 5 \) since the partitions of 4 are \( 4 \), \( 3+1 \), \( 2+2 \), \( 2+1+1 \), and \( 1+1+1+1 \).

### Conclusion

While there's no simple formula for \( p(n) \), the various methods provide means to compute and approximate it. The study of \( p(n) \) has deep connections to other areas of mathematics, including number theory, combinatorics, and mathematical analysis, and has inspired significant advancements in these fields.