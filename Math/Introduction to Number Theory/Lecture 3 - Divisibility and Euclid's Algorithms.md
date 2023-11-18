<iframe width="930" height="480" src="https://www.youtube.com/embed/pVKhDtOjji8?list=PL8yHsr3EFj53L8sMbzIhhXSAOpuZ1Fov8" title="Introduction to number theory lecture 3: Divisibility and Euclid&#39;s algorithms." frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Notation for Divisibility
In mathematics, the concept of divisibility is articulated using specific notation that succinctly captures the relationship between two integers. When we say that an integer \( a \) is divisible by another integer \( b \), it means that when \( a \) is divided by \( b \), the result is an integer with no remainder. In other words, \( b \) is a divisor of \( a \), or \( a \) is a multiple of \( b \).

The common notation used to express divisibility is:

$$
b \mid a
$$

This is read as "b divides a". Here, \( a \) and \( b \) are integers, and the divisibility implies that there exists an integer \( k \) such that:

$$
a = bk
$$

For example, if we consider \( a = 12 \) and \( b = 3 \), we can say \( 3 \mid 12 \) because \( 12 = 3 \times 4 \), where \( 4 \) is an integer. 

Conversely, if \( b \) does not divide \( a \) (that is, if dividing \( a \) by \( b \) leaves a remainder), we use the notation:

$$
b \nmid a
$$

For instance, since \( 5 \) does not divide \( 12 \) evenly (as \( 12 = 5 \times 2 + 2 \) has a remainder of \( 2 \)), we write \( 5 \nmid 12 \).

# Combinatorics in Divisibility Proofs
The relationship between combinatorics, binomial coefficients, and divisibility is an intriguing aspect of number theory and discrete mathematics. Combinatorics, the study of counting, arrangement, and combination of objects, often utilizes binomial coefficients, which have inherent properties that intersect with concepts of divisibility.

### Binomial Coefficients

The binomial coefficient, denoted as \( \binom{n}{k} \), represents the number of ways to choose \( k \) elements from a set of \( n \) elements without considering the order of selection. It's defined as:

$$
\binom{n}{k} = \frac{n!}{k!(n - k)!}
$$

where \( n! \) denotes the factorial of \( n \).

### Role in Divisibility Proofs

1. **Divisibility Properties**: Binomial coefficients exhibit specific divisibility properties. For instance, Pascal's triangle, which is constructed using binomial coefficients, reveals patterns that can be analyzed for divisibility by certain numbers.

2. **Applications in Proofs**: In divisibility proofs, one might encounter scenarios where you need to demonstrate that a binomial coefficient is divisible by a number. For example, showing that \( \binom{n}{k} \) is divisible by a prime \( p \) under certain conditions. This often involves manipulating factorials and applying theorems from number theory, such as the Fundamental Theorem of Arithmetic or Euclid's lemma.

3. **Combinatorial Arguments**: Many divisibility proofs, especially those involving integers with specific properties (like being even, odd, or prime), can be framed as combinatorial problems. For instance, proving that a certain combination of objects satisfies a divisibility property might involve counting those combinations using binomial coefficients and analyzing their divisibility.

### Example: Proving Divisibility Using Combinatorics

Consider proving that \( \binom{2n}{n} \) is even for \( n \geq 1 \). This statement can be approached combinatorially:

1. **Combinatorial Interpretation**: \( \binom{2n}{n} \) represents the number of ways to choose \( n \) items from a set of \( 2n \) items.
2. **Divisibility Analysis**: Notice that \( \binom{2n}{n} = \frac{(2n)!}{n!n!} \). Since \( (2n)! \) includes more factors of 2 than either of the \( n! \) in the denominator (due to the presence of terms like \( 2n, 2n-2, \ldots, 2 \)), the fraction must be even.

### Further Implications

- **Lucas' Theorem and Kummer's Theorem**: These theorems provide insights into the divisibility of binomial coefficients by a prime number, linking number theory with combinatorics. [[Lucas' Theorem and Kummer's Theorem]]
- **Generating Functions**: In combinatorics, generating functions often involve binomial coefficients and can be analyzed for their divisibility properties.

In summary, combinatorics and binomial coefficients play a significant role in understanding and proving properties related to divisibility. They offer a framework for constructing and analyzing mathematical arguments in a discrete setting, often revealing deeper connections within number theory.

# Ideals of An Integer
[[Ideals of an Integer]]

# Euclid's Division Algorithm
Euclid's Division Algorithm is a classical approach to finding the greatest common divisor (GCD) of two integers. This algorithm is based on the principle that the GCD of two numbers also divides their difference. This fundamental algorithm not only plays a crucial role in number theory but also forms the basis for more complex algorithms in modern computational mathematics.

### Description of Euclid's Division Algorithm

The algorithm proceeds as follows for two integers \( a \) and \( b \):

1. **Ensure \( a \geq b \)**: If \( a < b \), swap the two numbers.

2. **Division Step**: Divide \( a \) by \( b \), expressing \( a \) as \( a = bq + r \), where \( q \) is the quotient and \( r \) is the remainder. Here, \( 0 \leq r < b \).

3. **Iterate or Terminate**:
   - If \( r = 0 \), then \( b \) is the GCD of \( a \) and \( b \).
   - If \( r \neq 0 \), replace \( a \) with \( b \) and \( b \) with \( r \), and repeat the division step.

4. **Repeat Until Remainder is Zero**: Continue this process until the remainder becomes zero. The non-zero remainder at the last non-zero step is the GCD of the original pair of numbers.

### Example

Let's demonstrate Euclid's Division Algorithm to find the GCD of \( 48 \) and \( 18 \):

1. **Initial Step**: \( a = 48 \), \( b = 18 \) (already \( a \geq b \)).
2. **First Division**: \( 48 = 18 \times 2 + 12 \) (quotient is 2, remainder is 12).
3. **Update and Repeat**: Now \( a = 18 \) and \( b = 12 \).
4. **Second Division**: \( 18 = 12 \times 1 + 6 \) (quotient is 1, remainder is 6).
5. **Update and Repeat**: Now \( a = 12 \) and \( b = 6 \).
6. **Third Division**: \( 12 = 6 \times 2 + 0 \) (quotient is 2, remainder is 0).
7. **Conclusion**: Since the remainder is now zero, the GCD is the last non-zero remainder, which is \( 6 \).

### Significance

Euclid's Division Algorithm is elegant and efficient, making it a fundamental tool in elementary number theory. It is not only used for finding GCDs but also forms the basis of more complex algorithms, including those in cryptography and computer science. Its simplicity and efficiency make it an essential algorithm in the toolkit of mathematicians and computer scientists alike.

## Note: 
- Euclid represented his algorithm as a line segment, trying to fill up the line with segments of the quotient number
- They didn't even count 0 as a number
- Q and R are unique in the algorithm

# Proof of d|x form an ideal closed under addition and subtraction

To prove that the set of integers divisible by a fixed integer \( d \) forms an ideal in the ring of integers \( \mathbb{Z} \) that is closed under addition and subtraction, we need to show that this set satisfies the defining properties of an ideal. Let's denote this set as \( I_d \), where

$$ I_d = \{ x \in \mathbb{Z} \mid d \mid x \}. $$

In other words, \( I_d \) contains all integers that are multiples of \( d \).

### Properties to Prove

1. **Closure under Addition**: For any two elements \( a, b \in I_d \), their sum \( a + b \) must also be in \( I_d \).
2. **Closure under Subtraction**: For any two elements \( a, b \in I_d \), their difference \( a - b \) must also be in \( I_d \).
3. **Closure under Multiplication by Ring Elements**: For any element \( a \in I_d \) and any ring element \( r \in \mathbb{Z} \), the product \( ra \) must be in \( I_d \).

### Proof

1. **Closure under Addition**:
   - Suppose \( a, b \in I_d \). By definition, \( d \) divides \( a \) and \( b \), so there exist integers \( k, l \) such that \( a = dk \) and \( b = dl \).
   - Consider their sum: \( a + b = dk + dl = d(k + l) \).
   - Since \( k + l \) is an integer (integers are closed under addition), \( a + b \) is a multiple of \( d \).
   - Therefore, \( a + b \in I_d \).

2. **Closure under Subtraction**:
   - Again, let \( a, b \in I_d \), with \( a = dk \) and \( b = dl \) for some integers \( k, l \).
   - Consider their difference: \( a - b = dk - dl = d(k - l) \).
   - Since \( k - l \) is an integer (integers are closed under subtraction), \( a - b \) is a multiple of \( d \).
   - Therefore, \( a - b \in I_d \).

3. **Closure under Multiplication by Ring Elements**:
   - Let \( a \in I_d \) and \( r \in \mathbb{Z} \), with \( a = dk \) for some integer \( k \).
   - Consider the product: \( ra = r(dk) = d(rk) \).
   - Since \( rk \) is an integer (integers are closed under multiplication), \( ra \) is a multiple of \( d \).
   - Therefore, \( ra \in I_d \).

### Conclusion

The set \( I_d \) of all integers divisible by \( d \) satisfies the necessary properties to be an ideal in the ring of integers \( \mathbb{Z} \). It is closed under addition, subtraction, and multiplication by any element in \( \mathbb{Z} \). Thus, \( I_d \) forms an ideal in \( \mathbb{Z} \).

# Fast Algorithm to find GCD
The most efficient and widely used method for finding the greatest common divisor (GCD) of two integers is the Euclidean Algorithm. This algorithm is based on the principle that the GCD of two numbers also divides their difference. Its beauty lies in its simplicity and speed, especially for large numbers.

Here's a brief outline of the algorithm:

1. **Start with Two Numbers**: Suppose you have two integers, \( a \) and \( b \), and you wish to find their GCD.

2. **Division Step**: Divide \( a \) by \( b \), and take note of the remainder. Mathematically, this can be represented as \( a = bq + r \), where \( q \) is the quotient and \( r \) is the remainder.

3. **Update the Numbers**: Now, replace \( a \) with \( b \) and \( b \) with \( r \).

4. **Iterate**: Repeat the division step with the updated values.

5. **Termination**: The algorithm terminates when the remainder becomes zero. At this point, the divisor (\( b \)) is the GCD of the original two numbers.

6. **Result**: The last non-zero remainder is the GCD of \( a \) and \( b \).

The Euclidean Algorithm is fast because it rapidly reduces the size of the numbers involved, thereby converging quickly to the GCD. For example, to find the GCD of 48 and 18:

1. \( 48 = 18 \times 2 + 12 \)
2. Replace \( 48 \) with \( 18 \) and \( 18 \) with \( 12 \).
3. \( 18 = 12 \times 1 + 6 \)
4. Replace \( 18 \) with \( 12 \) and \( 12 \) with \( 6 \).
5. \( 12 = 6 \times 2 + 0 \)

So, the GCD of 48 and 18 is 6.

This method is highly efficient for computational purposes and is the standard approach used in many algorithms where GCD calculation is a fundamental step.

**We use this because factoring large numbers are really hard.** What might be the computationally simpler method to factor numbers? #toread

It is actually non trivial: the GCD finding algorithm. Also we can easily see why this algorithm works.

- This algorithm terminates, because the remainders on each iteration are decreasing

# Computational Complexity of Euclid's Algorithm

The time complexity of the Euclidean Algorithm for computing the greatest common divisor (GCD) of two integers is often analyzed in terms of the number of digits of the input numbers, rather than the size of the input itself (which is the usual way of expressing complexity in the Big O notation). This is because the number of steps required by the algorithm depends more directly on the number of digits than on the absolute values of the numbers.

The Euclidean Algorithm's complexity is \( O(\log(\min(a, b))) \), where \( a \) and \( b \) are the two input integers. This logarithmic time complexity is derived from the following considerations:

1. **Worst-Case Scenario**: The worst-case scenario for the Euclidean Algorithm occurs when the two numbers are consecutive Fibonacci numbers. This is because the Fibonacci sequence has the property that the ratio of consecutive terms converges to the golden ratio, and this ratio represents the slowest possible convergence for the Euclidean Algorithm.
	   The worst-case scenario for the Euclidean Algorithm occurs when the algorithm takes the maximum number of steps to find the GCD of two numbers. This situation arises when the two numbers involved are consecutive Fibonacci numbers. Let's denote these numbers as \( F_n \) and \( F_{n-1} \), where \( F_n \) is the \( n \)-th Fibonacci number.
	
	The Fibonacci sequence is defined recursively as:
	$$
	F_n = F_{n-1} + F_{n-2}
	$$
	with initial conditions \( F_0 = 0 \) and \( F_1 = 1 \).
	
	In the Euclidean Algorithm, the recursive relation between the remainders in each step can be expressed as follows. Let's denote the remainder at the \( i \)-th step as \( r_i \). Then, in the context of Fibonacci numbers, the algorithm proceeds like this:
	
	1. **Initial Step**: Start with \( F_n \) and \( F_{n-1} \).
	2. **First Iteration**: Compute the remainder when \( F_n \) is divided by \( F_{n-1} \). Since \( F_n = F_{n-1} + F_{n-2} \), the remainder is \( F_{n-2} \). So, \( r_1 = F_{n-2} \).
	3. **Subsequent Iterations**: In each subsequent iteration, the algorithm essentially reduces to finding the GCD of \( F_{n-1} \) and \( F_{n-2} \), then \( F_{n-2} \) and \( F_{n-3} \), and so on. Thus, the remainder sequence follows the reverse of the Fibonacci sequence:
	   $$
	   r_i = F_{n-(i+1)}
	   $$
	   for \( i = 1, 2, \ldots, n-1 \).
	4. **Termination**: The algorithm terminates when it reaches the GCD of \( F_2 \) and \( F_1 \), which is 1, since these are the first two non-zero Fibonacci numbers.
	
	Therefore, the recursive relation in the context of the Fibonacci sequence is:
	$$
	r_i = F_{n-(i+1)}
	$$
	where \( r_i \) represents the remainder at the \( i \)-th step of the Euclidean Algorithm, and \( F_k \) is the \( k \)-th Fibonacci number. This relationship demonstrates the inefficiency of the algorithm in this specific case, as it requires a number of steps linear in the position of the Fibonacci number in the sequence, which is logarithmic in the value of the Fibonacci number itself.

1. **Number of Digits**: The number of digits in a number \( n \) is approximately proportional to \( \log(n) \). Therefore, the time complexity can be expressed in terms of the logarithm of the smaller number.

2. **Number of Iterations**: In each iteration of the Euclidean Algorithm, at least one digit of the number is eliminated, meaning that the number of iterations is proportional to the number of digits in the smaller number. Thus, the total number of iterations is \( O(\log(\min(a, b))) \).

This logarithmic complexity makes the Euclidean Algorithm extremely efficient for even very large numbers, which is one of the reasons why it is so widely used in computational mathematics and algorithms involving number theory.

# Upper and Lower bounds of the growth of Fibonacci
The Fibonacci sequence, defined by the recurrence relation \( F_n = F_{n-1} + F_{n-2} \) with initial conditions \( F_0 = 0 \) and \( F_1 = 1 \), exhibits a well-known growth pattern. To understand its growth, we consider both the upper and lower bounds.

### Lower Bound

The lower bound can be established by observing that each term in the Fibonacci sequence is the sum of the two previous terms. This implies that the sequence grows at least as fast as a sequence where each term is twice the previous term after the first few terms. Thus, a lower bound is given by exponential growth of the form \( 2^{n-1} \) for \( n \geq 1 \), or more precisely:
$$
F_n \geq 2^{n-1} \text{ for } n \geq 1.
$$

### Upper Bound

The upper bound of the Fibonacci sequence is intimately connected to the golden ratio, denoted as \( \phi \), where \( \phi = \frac{1 + \sqrt{5}}{2} \approx 1.61803398875 \). The nth Fibonacci number can be approximated using Binet's Formula ([[Proof For Binet's Formula]]), which is an exact expression involving \( \phi \):
$$
F_n = \frac{\phi^n - (1-\phi)^n}{\sqrt{5}}.
$$
Since \( |1-\phi| < 1 \), the term \( (1-\phi)^n \) becomes negligible for large \( n \). Therefore, the Fibonacci numbers can be approximated by:
$$
F_n \approx \frac{\phi^n}{\sqrt{5}}.
$$
Thus, the upper bound can be expressed as:
$$
F_n \leq \frac{\phi^n}{\sqrt{5}}.
$$

### Summary

In summary, the growth of the Fibonacci sequence is bounded between an exponential lower bound and an upper bound tied to the powers of the golden ratio:
$$
2^{n-1} \leq F_n \leq \frac{\phi^n}{\sqrt{5}} \text{ for large } n.
$$
These bounds highlight the exponential nature of the Fibonacci sequence's growth, with the golden ratio playing a central role in its behavior.

# The Fibonacci Sequence as a Finite Difference Equation

[[Finite Difference Equations]]
The Fibonacci sequence can indeed be expressed as a finite difference equation. The Fibonacci sequence is defined by the recurrence relation:
$$
F_{n} = F_{n-1} + F_{n-2}
$$
with initial conditions \( F_0 = 0 \) and \( F_1 = 1 \).

In terms of finite difference equations, this recurrence relation can be interpreted as a second-order linear homogeneous finite difference equation. The equation relates the difference between successive terms of the sequence. 

The finite difference equation for the Fibonacci sequence can be expressed as:
$$
F_{n} - F_{n-1} - F_{n-2} = 0
$$
for \( n \geq 2 \).

This equation reflects the essence of the Fibonacci sequence: each term (starting from the third term) is the sum of the two preceding terms. In finite difference terms, the 'difference' here is not in the sense of subtracting adjacent terms but in the sense of equating the sum of specific terms to zero, which is characteristic of homogeneous equations.

# Ansatz Approach to Solving the Fibonacci

The Fibonacci sequence, a classic example of a recursive sequence, is defined by the relations:

$$
F_0 = 0, \quad F_1 = 1,
$$
and
$$
F_{n} = F_{n-1} + F_{n-2} \quad \text{for} \quad n \geq 2.
$$

To derive a closed-form formula for the Fibonacci sequence, we employ an approach known as the "ansatz." This method, deeply rooted in mathematical physics and differential equations, involves making an educated guess about the form of the solution and then determining the constants or functions in the guess by substituting into the equation and solving for these unknowns.

For the Fibonacci sequence, we consider the ansatz:

$$
F_n = \alpha r^n + \beta s^n,
$$

where \( \alpha \), \( \beta \), \( r \), and \( s \) are constants to be determined. This form is chosen because it suggests that each term of the sequence is a linear combination of two geometric sequences.

Substituting \( F_n \) and \( F_{n-1} \) into the recursive relation, we obtain:

$$
\alpha r^n + \beta s^n = \alpha r^{n-1} + \beta s^{n-1} + \alpha r^{n-2} + \beta s^{n-2}.
$$

Rearranging and factoring, we find:

$$
\alpha r^n (1 - r - r^{-1}) + \beta s^n (1 - s - s^{-1}) = 0.
$$

Since this relation must hold for all \( n \), we deduce that each term in parentheses must equal zero, leading to the characteristic equation:

$$
x^2 - x - 1 = 0.
$$

Solving this quadratic equation, we find the roots:

$$
r = \frac{1 + \sqrt{5}}{2}, \quad s = \frac{1 - \sqrt{5}}{2}.
$$

These are the famous golden ratio and its conjugate. Now, using the initial conditions \( F_0 = 0 \) and \( F_1 = 1 \), we can solve for \( \alpha \) and \( \beta \):

1. \( F_0 = \alpha + \beta = 0 \) yields \( \beta = -\alpha \).
2. \( F_1 = \alpha r + \beta s = 1 \) allows us to find \( \alpha \) and \( \beta \).

- To find alpha and beta, just plug in to the base case equation

# Funny Identities of Fibonacci Numbers
The Fibonacci sequence is replete with fascinating and sometimes unexpected properties. Here are a few that stand out for their mathematical elegance and curiosity:

1. **Golden Ratio Convergence**: As the Fibonacci sequence progresses, the ratio of consecutive terms \( \frac{F_{n+1}}{F_n} \) converges to the golden ratio, \( \phi = \frac{1 + \sqrt{5}}{2} \). This is a reflection of the sequence's intimate connection with the golden ratio.

2. **Coprime Terms**: Any two consecutive Fibonacci numbers are coprime, meaning they have no common divisor other than 1. This property emerges from the recursive nature of the sequence.

3. **Sum of Squares**: The sum of the squares of the first \( n \) Fibonacci numbers equals the product of the \( n \)th and \( (n+1) \)th Fibonacci numbers:
   
   $$
   F_1^2 + F_2^2 + \cdots + F_n^2 = F_n \cdot F_{n+1}.
   $$

4. **Divisibility Property**: If a number \( m \) divides a number \( n \), then \( F_m \) divides \( F_n \). For example, since 3 divides 6, \( F_3 \) (which is 2) divides \( F_6 \) (which is 8).

5. **Zeckendorf's Theorem**: Every positive integer can be uniquely represented as the sum of one or more distinct, non-consecutive Fibonacci numbers. This representation is known as the Zeckendorf representation.

6. **Fibonacci and Prime Numbers**: Although not all Fibonacci numbers are prime, a Fibonacci number that is prime must have a prime or 4 as its index. This is not a two-way implication, however, as not all Fibonacci numbers with prime indices are prime themselves.

7. **Periodicity Modulo n (Pisano Period)**: When Fibonacci numbers are taken modulo \( n \), the sequence becomes periodic. The length of this period, known as the Pisano period, varies with \( n \) and is a fascinating subject of study in modular arithmetic.

8. **Cassini's Identity**: For any positive integer \( n \), the following identity holds:
   
   $$
   F_{n+1}F_{n-1} - F_n^2 = (-1)^n.
   $$

9. **Fibonacci Lattice Points**: The Fibonacci sequence can be used to create a spiral that approximates the golden spiral. This spiral appears frequently in nature and art, illustrating the sequence's connection to natural and aesthetic patterns.

Each of these properties unveils a different facet of the Fibonacci sequence, demonstrating its richness and depth in mathematical theory and its applications across various disciplines.

