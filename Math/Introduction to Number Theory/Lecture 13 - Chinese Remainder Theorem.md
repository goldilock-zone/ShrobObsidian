To solve linear congruences, we can use the following approach:

1. **Given Linear Congruence**: Start with a linear congruence in the form:
   $$ax \equiv b \pmod{m}$$
   Where:
   - $a$ is the coefficient of the variable $x$.
   - $b$ is a constant.
   - $m$ is the modulus.

2. **Check for Solvability**: First, check if there is a solution to the congruence. It exists if and only if the greatest common divisor (GCD) of $a$ and $m$ divides $b$. In mathematical terms:
   $$\text{If } \text{gcd}(a, m) \nmid b, \text{ there is no solution.}$$

3. **Find the Modular Multiplicative Inverse**: If the congruence is solvable, proceed to find the modular multiplicative inverse of $a$ modulo $m$. The modular multiplicative inverse of $a$ (if it exists) is denoted as $a^{-1}$ and satisfies the equation:
   $$a \cdot a^{-1} \equiv 1 \pmod{m}$$
   You can find $a^{-1}$ using methods like the Extended Euclidean Algorithm.

4. **Solve for $x$**: Once you have found $a^{-1}$, you can solve for $x$ by multiplying both sides of the congruence by $a^{-1}$:
   $$x \equiv a^{-1} \cdot b \pmod{m}$$
   This equation gives you the solution for $x$ modulo $m$.

5. **Express the Solution Set**: The solution to the linear congruence is not unique. It forms an equivalence class modulo $m$. Therefore, you can express the solution set as follows:
   $$x \equiv a^{-1} \cdot b + k \cdot m, \text{ where } k \in \mathbb{Z}$$
   This represents all possible solutions for $x$.

6. **Final Solution**: If you need a specific representative of the solution set, you can choose one by setting a suitable value for $k$. Common choices include choosing the smallest non-negative integer or the unique representative in the range $[0, m-1]$.

This approach ensures that you find a solution for the given linear congruence, and it provides a general representation for all possible solutions in terms of modular arithmetic.


# Solving non-linear congruences
In number theory, solving non-linear congruences involves finding solutions to equations of the form:

$$
f(x) \equiv 0 \pmod{m}
$$

Here, $f(x)$ is a non-linear function of $x$, and we want to find values of $x$ that satisfy the congruence modulo $m$.

1. **Existence of Solutions**: To determine if solutions exist, we often rely on the properties of modular arithmetic. If $f(x)$ and $m$ have no common factors (i.e., they are coprime), then a solution exists if and only if $f(x) \equiv 0 \pmod{m}$ has a solution in the integers.

2. **Trial and Error**: Solving non-linear congruences often involves trial and error, systematically checking different values of $x$ modulo $m$ to see if they satisfy the congruence. For some simple non-linear congruences, this method may suffice.

3. **Modular Inverses**: If $f(x)$ is a polynomial or a function that involves an inverse operation (e.g., division), we may need to find modular inverses. For example, if $f(x) = 2x \pmod{7}$, we need to find the modular inverse of $2$ modulo $7$, which is $4$, and then solve $4x \equiv 0 \pmod{7}$.

4. **Quadratic Residues**: When dealing with quadratic congruences of the form $ax^2 \equiv b \pmod{m}$, where $a$ and $m$ are coprime, techniques such as the Legendre symbol and quadratic reciprocity may be employed to determine solvability and find solutions.

5. **Chinese Remainder Theorem**: For more complex congruences involving multiple moduli, the Chinese Remainder Theorem can be applied to break down the problem into simpler congruences and solve them individually.

6. **Computer Algorithms**: In practical applications and when dealing with large values of $m$, computer algorithms like the Extended Euclidean Algorithm or the Tonelli-Shanks algorithm may be used to efficiently find solutions to non-linear congruences.

Solving non-linear congruences in number theory can be a challenging task, and the approach taken depends on the specific form of the congruence and the tools available for analysis.


# Chinese Remainder Theorem
The Chinese Remainder Theorem (CRT) is a fundamental result in number theory that provides a way to solve systems of simultaneous congruences. It is often used in modular arithmetic and has various applications in computer science and cryptography.

Suppose we have a system of congruences:

$$
x \equiv a_1 \ (\text{mod}\ m_1)
$$

$$
x \equiv a_2 \ (\text{mod}\ m_2)
$$

$$
\vdots
$$

$$
x \equiv a_k \ (\text{mod}\ m_k)
$$

Where:
- $x$ is the unknown value we want to find.
- $a_1, a_2, \ldots, a_k$ are the remainders when $x$ is divided by $m_1, m_2, \ldots, m_k$ respectively.
- $m_1, m_2, \ldots, m_k$ are pairwise coprime (i.e., their greatest common divisors are 1).

The Chinese Remainder Theorem states that if the moduli $m_1, m_2, \ldots, m_k$ are pairwise coprime, then there exists a unique solution for $x$ modulo $m_1 \cdot m_2 \cdot \ldots \cdot m_k$. This means that there is a solution $x$ within the range from 0 to $m_1 \cdot m_2 \cdot \ldots \cdot m_k - 1$ that satisfies all the congruences simultaneously.

The formula to compute this unique solution for $x$ is given by:

$$
x \equiv \left( a_1 \cdot M_1 \cdot y_1 + a_2 \cdot M_2 \cdot y_2 + \ldots + a_k \cdot M_k \cdot y_k \right) \ (\text{mod}\ m_1 \cdot m_2 \cdot \ldots \cdot m_k)
$$

Where:
- $M_i = \frac{m_1 \cdot m_2 \cdot \ldots \cdot m_k}{m_i}$ (the product of all moduli except $m_i$).
- $y_i$ is the modular multiplicative inverse of $M_i$ modulo $m_i$.

The CRT is particularly useful in solving problems involving modular arithmetic, such as finding solutions to linear congruences, representing large integers in a more manageable form, and in certain cryptographic algorithms. It provides an efficient method to work with modular equations when the moduli are coprime, allowing us to break down complex modular problems into simpler ones and then combine their solutions to find the final solution.

# Existence and Uniqueness of Solutions
The Chinese Remainder Theorem (CRT) is a fundamental theorem in number theory that provides a way to solve a system of simultaneous congruences. It states the following:

**The Chinese Remainder Theorem (CRT):** Let $n_1, n_2, \ldots, n_k$ be pairwise coprime positive integers (i.e., their greatest common divisors are all 1), and let $a_1, a_2, \ldots, a_k$ be any integers. Then, for any integer $x$, there exists a unique integer $0 \leq x < N$, where $N = n_1 \cdot n_2 \cdot \ldots \cdot n_k$, such that:

$$
x \equiv a_1 \pmod{n_1} \\
x \equiv a_2 \pmod{n_2} \\
\vdots \\
x \equiv a_k \pmod{n_k}
$$

In other words, the CRT provides a solution for the value of $x$ that satisfies a set of congruences with pairwise coprime moduli. Here's a brief outline of the proof for the Chinese Remainder Theorem:

**Proof:**

1. **Existence of Solution:** We first prove that a solution $x$ exists. Consider the number $N = n_1 \cdot n_2 \cdot \ldots \cdot n_k$. For each $i$, let $N_i = \frac{N}{n_i}$. Since $n_i$ is coprime with $N_i$, we can use the extended Euclidean algorithm to find integers $y_i$ such that $N_i \cdot y_i \equiv 1 \pmod{n_i}$.

2. **Constructing $x$:** Now, let's construct $x$ as follows:
   $$x = \sum_{i=1}^{k} a_i \cdot N_i \cdot y_i$$
   By the construction, $x$ satisfies each congruence $x \equiv a_i \pmod{n_i}$ because:
   $$x \equiv a_i \cdot N_i \cdot y_i \equiv a_i \cdot 1 \cdot y_i \equiv a_i \pmod{n_i}$$

3. **Uniqueness:** To prove uniqueness, assume there are two solutions, say $x_1$ and $x_2$, that satisfy the congruences. Then, we have:
   $$x_1 \equiv a_i \equiv x_2 \pmod{n_i}$$
   Since $n_i$ divides $N$, it follows that $n_i$ divides $(x_1 - x_2)$ for all $i$. Since the moduli $n_1, n_2, \ldots, n_k$ are pairwise coprime, their product $N$ is their least common multiple (LCM). Therefore, $x_1 - x_2$ is a multiple of $N$. However, since we restrict $0 \leq x < N$, $x_1$ and $x_2$ must be congruent modulo $N$, and hence, $x_1 \equiv x_2 \pmod{N}$.

This proves the existence and uniqueness of a solution $x$ that satisfies the given system of congruences, as required by the Chinese Remainder Theorem.

# Strength of pairwise coprimality
Pairwise coprimality is a stronger condition than conjunctive coprimality because it imposes a stricter requirement on the relationships between a set of numbers.

1. **Pairwise Coprimality**:
   When a set of numbers is pairwise coprime, it means that any two distinct numbers in the set have no common prime factors except for 1. In other words, for every pair of numbers in the set, their greatest common divisor (GCD) is equal to 1. Mathematically, if we have a set of numbers {a1, a2, a3, ..., an}, they are pairwise coprime if and only if GCD(ai, aj) = 1 for all i ≠ j, where 1 ≤ i, j ≤ n.

   This condition is stronger because it ensures that there are no shared prime factors between any pair of numbers in the set, making them relatively prime to each other in every possible combination.

2. **Conjunctive Coprimality**:
   Conjunctive coprimality, on the other hand, only requires that there exists a single number (usually 1) that is a common divisor for all the numbers in the set. In other words, a set of numbers {a1, a2, a3, ..., an} is conjunctively coprime if and only if there exists a number x (typically 1) such that GCD(ai, x) = 1 for all 1 ≤ i ≤ n.

   This condition is weaker because it allows for the presence of common factors among the numbers in the set, as long as there is one number that can be used to make them coprime by taking its GCD with each element.

In summary, pairwise coprimality requires that every pair of numbers in the set has no common prime factors except for 1, while conjunctive coprimality only necessitates the existence of a single number that can be used to make all the numbers coprime. Pairwise coprimality is a stricter condition and provides stronger assurances of the absence of shared prime factors within the set.

# Sunzi's Problem
Sunzi's problem, also known as the "Chinese Remainder Theorem," is a mathematical problem that dates back to the 3rd century in ancient China. This problem was introduced and solved by the Chinese mathematician and scholar Sunzi (also spelled Sun Tzu or Sun Zi) in his famous work "Sunzi Suanjing" or "Mathematical Manual of Sunzi."

The problem can be summarized as follows:

Given a set of congruences, each in the form:

$$
x \equiv a_i \pmod{m_i}
$$

where $x$ is the unknown value we want to find, $a_i$ are known remainders, and $m_i$ are pairwise coprime (meaning they have no common prime factors), the goal is to find a solution for $x$ that satisfies all these congruences simultaneously.

Sunzi's contribution in the 3rd century was to provide a systematic method for finding a solution to this problem. His approach laid the foundation for what we now know as the Chinese Remainder Theorem (CRT). The CRT is an essential concept in number theory and modular arithmetic and has applications in various fields, including computer science, cryptography, and error-correcting codes.

Sunzi's work on this problem demonstrates his significant contribution to mathematics and the development of mathematical techniques that continue to be relevant and widely used to this day.

# Linear Algebraic Method of showing the uniqueness of solutions
The Chinese Remainder Theorem (CRT) is a theorem in number theory that deals with finding solutions to a system of modular congruences. One way to demonstrate the uniqueness of the solution to the CRT using a linear algebraic method is by representing the system of congruences as a system of linear equations.

Let's say we have a system of congruences:

$$
\begin{align*}
x &\equiv a_1 \pmod{m_1} \\
x &\equiv a_2 \pmod{m_2} \\
&\vdots \\
x &\equiv a_k \pmod{m_k}
\end{align*}
$$

Where $a_1, a_2, \ldots, a_k$ are remainders, and $m_1, m_2, \ldots, m_k$ are pairwise coprime moduli.

To show the uniqueness of the solution, we can interpret this system as a system of linear equations in the following way:

1. For each congruence $x \equiv a_i \pmod{m_i}$, we can create a linear equation:
   $$
   x = a_i + m_i \cdot y_i
   $$
   Where $y_i$ is an unknown integer.

2. Now, we have a system of linear equations:
   $$
   \begin{align*}
   x &= a_1 + m_1 \cdot y_1 \\
   x &= a_2 + m_2 \cdot y_2 \\
   &\vdots \\
   x &= a_k + m_k \cdot y_k
   \end{align*}
   $$

3. We can rewrite this system of linear equations in matrix form. Let's define vectors and matrices:
   - Let $\mathbf{x}$ be the column vector $[x]$.
   - Let $\mathbf{a}$ be the column vector $[a_1, a_2, \ldots, a_k]$.
   - Let $\mathbf{y}$ be the column vector $[y_1, y_2, \ldots, y_k]$.
   - Let $\mathbf{M}$ be the diagonal matrix with diagonal entries $[m_1, m_2, \ldots, m_k]$.

   The system of equations can then be written as:
   $$
   \mathbf{x} = \mathbf{a} + \mathbf{M}\mathbf{y}
   $$

4. Now, we can express the uniqueness of the solution. If $\mathbf{x}_1$ and $\mathbf{x}_2$ are two solutions to the system of congruences, it implies that they both satisfy the matrix equation:
   $$
   \mathbf{x}_1 = \mathbf{a} + \mathbf{M}\mathbf{y}_1
   $$
   and
   $$
   \mathbf{x}_2 = \mathbf{a} + \mathbf{M}\mathbf{y}_2
   $$

5. If both $\mathbf{x}_1$ and $\mathbf{x}_2$ satisfy these equations, then their difference $\mathbf{x}_1 - \mathbf{x}_2$ must satisfy:
   $$
   \mathbf{0} = \mathbf{M}(\mathbf{y}_1 - \mathbf{y}_2)
   $$

6. Because $\mathbf{M}$ is a diagonal matrix with pairwise coprime entries, the only way for this equation to hold is if $\mathbf{y}_1 - \mathbf{y}_2 = \mathbf{0}$ (the zero vector).

7. This means that $\mathbf{y}_1 = \mathbf{y}_2$, which implies that $\mathbf{x}_1 = \mathbf{a} + \mathbf{M}\mathbf{y}_1 = \mathbf{a} + \mathbf{M}\mathbf{y}_2 = \mathbf{x}_2$.

8. Therefore, there is only one unique solution to the system of congruences, as any other solution would lead to the same values for $\mathbf{y}_1$ and $\mathbf{y}_2$, making the solutions equal.

In summary, by representing the Chinese Remainder Theorem as a system of linear equations and using linear algebraic techniques, we can prove that the solution to the system of congruences is unique, ensuring that there is only one valid solution for the given remainders and moduli.

Note: [[Coset and Coset Representatives]]

# Alternative Proof of Chinese Remainder Theorem

1. **System of Congruences**: 
   - It starts with a system of congruences:
     $$ x \equiv a_1 \mod m_1 $$
     $$ x \equiv a_2 \mod m_2 $$

2. **Solution Existence**: 
   - It states that there exists a solution modulo $m_1m_2$ if the moduli $m_1$ and $m_2$ are coprime, i.e., $\gcd(m_1, m_2) = 1$.

3. **Moduli Product**: 
   - It lists the complete set of residues modulo $m_1m_2$, which are $0, 1, 2, ..., m_1m_2 - 1$.

4. **Coprimality**: 
   - It notes that the coprimality condition $(m_1, m_2) = 1$ allows us to write the Bézout's identity:
     $$ m_1n_2 + m_2n_1 = 1 $$

5. **Injection**: 
   - The proof seems to assert that there is an injection from pairs $(x, y)$ that satisfy the congruences to pairs $(x \mod m_1, y \mod m_2)$. 
   - The injection is such that if $x$ and $y$ are distinct, they remain distinct when reduced modulo $m_1$ and $m_2$ respectively.
   - If $x \equiv y \mod m_1$ and $x \equiv y \mod m_2$, then by the definition of congruence, $m_1 | (x-y)$ and $m_2 | (x-y)$. Since $m_1$ and $m_2$ are coprime, it must be that $m_1m_2 | (x-y)$, which implies $x \equiv y \mod m_1m_2$.
   
- Obviously, the elements on both sides of the injection are the same. therefore, there exists a surjection between the sets, and together they form a bijection. This is what wanted to prove in the first place. 
- If the $m_1$ and $m_2$ are not coprime, they may not be surjective (because at the lcm element of the two numbers, there a repetition of the zero element) and hence cannot be bijective

# Example of CRT being used for solving non linear congruences
The Chinese Remainder Theorem (CRT) is a powerful tool in number theory for solving systems of linear congruences. While it's primarily designed for linear congruences, it can sometimes be adapted to solve certain non-linear congruence problems. Let's illustrate this with an example:

Suppose we have a non-linear congruence of the form:
$$ x^2 \equiv a \pmod{m} $$

To solve this using the CRT, we first factorize $m$ into coprime factors (assuming $m$ can be factorized in such a way). Let's say $m = p_1 \times p_2 \times \ldots \times p_k$, where each $p_i$ is a prime number or a power of a prime number, and they are pairwise coprime. Then we solve the congruence:
$$ x^2 \equiv a \pmod{p_i} $$ 
for each $p_i$.

After finding all solutions for each prime factor, we use the CRT to combine these solutions into a solution modulo $m$.

### Example:

Let's consider a specific example. Suppose we want to solve:
$$ x^2 \equiv 5 \pmod{21} $$
Here, $21$ can be factorized as $3 \times 7$. So, we need to solve the system:
1. $x^2 \equiv 5 \pmod{3}$
2. $x^2 \equiv 5 \pmod{7}$

#### Solving the Individual Congruences:
1. For $x^2 \equiv 5 \pmod{3}$, we check each residue class modulo $3$: $0^2, 1^2, 2^2$ and find that $x \equiv 1 \pmod{3}$ and $x \equiv 2 \pmod{3}$ are solutions.
   
2. For $x^2 \equiv 5 \pmod{7}$, we check each residue class modulo $7$: $0^2, 1^2, 2^2, \ldots, 6^2$ and find that $x \equiv 3 \pmod{7}$ and $x \equiv 4 \pmod{7}$ are solutions.

#### Applying the CRT:
We now have two sets of congruences: $x \equiv 1 \text{ or } 2 \pmod{3}$ and $x \equiv 3 \text{ or } 4 \pmod{7}$. Using the CRT, we find combinations of these solutions that will work for the original congruence modulo $21$.

This might involve solving systems like:
1. $x \equiv 1 \pmod{3}$ and $x \equiv 3 \pmod{7}$
2. $x \equiv 1 \pmod{3}$ and $x \equiv 4 \pmod{7}$
3. $x \equiv 2 \pmod{3}$ and $x \equiv 3 \pmod{7}$
4. $x \equiv 2 \pmod{3}$ and $x \equiv 4 \pmod{7}$

Each of these systems will give a unique solution modulo $21$. The final step involves applying the CRT formula or algorithm to these sets of congruences to find the complete set of solutions modulo $21$. 

This example demonstrates how the CRT, primarily a tool for linear congruences, can be creatively applied to certain types of non-linear congruences by breaking down the problem into simpler parts.


# Solving a more general case
To solve the congruence $f(x) \equiv 0 \pmod{4}$, we need to find the values of $x$ that satisfy this modular equation. To do this, we can break down the problem using the Chinese Remainder Theorem (CRT). 

The Chinese Remainder Theorem states that if we have a system of simultaneous congruences, where each congruence has a different modulus, and the moduli are pairwise coprime (i.e., they have no common factors), then there exists a unique solution modulo the product of all the moduli.

In this case, we have a single congruence $f(x) \equiv 0 \pmod{4}$. To apply CRT, we first factorize $4$ into its prime factors, which is $4 = 2^2$. So, we will solve the congruence modulo each prime factor separately.

1. Solve $f(x) \equiv 0 \pmod{2}$:
   We find the solutions to $f(x) \equiv 0 \pmod{2}$ by looking at the even and odd values of $x$. If $x$ is even, then $f(x)$ is divisible by $2$. If $x$ is odd, then $f(x)$ is not divisible by $2$. So, the solutions modulo $2$ are the even values of $x$.

2. Solve $f(x) \equiv 0 \pmod{2^2}$:
   To solve $f(x) \equiv 0 \pmod{4}$, we need to find solutions that are multiples of $4$. Using CRT, we combine the solutions from step 1 (modulo $2$) and solutions modulo $2^2$ to find the solutions modulo $4$. These solutions are the even values of $x$.

In summary, to solve $f(x) \equiv 0 \pmod{4}$, we find that the solutions are the even values of $x$. There are infinite even integers, so there are infinitely many solutions to the congruence $f(x) \equiv 0 \pmod{4}$.

# Another Example
The Chinese Remainder Theorem (CRT) is applicable for solving systems of congruences with coprime moduli. Given the equation $x^2 \equiv \text{mod}\ 680$, we need to factorize 680 to apply CRT.

The prime factorization of 680 is $2^3 \cdot 5 \cdot 17$. So, we can write the original congruence as a system of congruences:

$$
\begin{align*}
x^2 &\equiv 0 \ (\text{mod}\ 2^3), \\
x^2 &\equiv 0 \ (\text{mod}\ 5), \\
x^2 &\equiv 0 \ (\text{mod}\ 17).
\end{align*}
$$

For each congruence, the solution set is as follows:

1. $x^2 \equiv 0 \ (\text{mod}\ 2^3)$: This has one solution, $x \equiv 0 \ (\text{mod}\ 8)$.
2. $x^2 \equiv 0 \ (\text{mod}\ 5)$: This has one solution, $x \equiv 0 \ (\text{mod}\ 5)$.
3. $x^2 \equiv 0 \ (\text{mod}\ 17)$: This has one solution, $x \equiv 0 \ (\text{mod}\ 17)$.

Since the moduli are coprime, by CRT, there is a unique solution modulo the product of the moduli, which in this case is 680. Thus, there is one solution to the given congruence, which is $x \equiv 0 \ (\text{mod}\ 680)$. 

This means any integer $x$ that is a multiple of 680 will satisfy the equation $x^2 \equiv \text{mod}\ 680$.