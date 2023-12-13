To solve the congruence $x^2 \equiv 7 \mod{3^{100}}$ using the Chinese Remainder Theorem (CRT) repeatedly, one would follow an iterative process, addressing $x$ modulo increasing powers of 3, and utilizing the results to tackle the subsequent power. This method hinges on the premise that possessing a solution modulo $3^k$ often facilitates the discovery of a solution modulo $3^{k+1}$. The methodology unfolds as follows:

#### Step 1: Solve for the Base Case mod 3

Address the congruence for the smallest non-trivial power of 3, which is $3^1$:
$$ x^2 \equiv 7 \equiv 1 \mod{3} $$

Here, $x \equiv 1 \mod{3}$ and $x \equiv 2 \mod{3}$ are viable solutions as $1^2 = 1$ and $2^2 = 4 \equiv 1 \mod{3}$.

#### Step 2: Solve for the Next Power of 3

Advance to solving for $x \mod{3^2} = 9$. If $x \equiv a \mod{9}$, where $a$ is an elevation of our mod 3 solution to mod 9, and given two potential values for $a$ from the prior step (1 and 2), it's necessary to identify which, upon squaring, aligns with a remainder of 7 modulo 9.

#### Step 3: Use Hensel's Lemma (If Applicable)

When scaling to loftier powers of the prime, Hensel's Lemma can upgrade solutions from $3^k$ to $3^{k+1}$ given certain criteria. If $f(x)$ is a polynomial with integer coefficients and $p$ is a prime with $f(a) \equiv 0 \mod{p^k}$ and $f'(a) \not\equiv 0 \mod{p}$, then a singular integer $b$ exists such that $f(b) \equiv 0 \mod{p^{k+1}}$ and $b \equiv a \mod{p^k}$.

Nonetheless, Hensel's Lemma isn't directly applicable since the derivative of $x^2$ is $2x$, which is null modulo 3 when $x$ is also null modulo 3. Hence, we can't apply Hensel's Lemma directly if our mod $3^k$ solution is a multiple of 3.

#### Step 4: Iterative Solution Building for Each Power

As Hensel's Lemma isn't directly usable, solutions for each power of 3 must be derived through trial and error or via other numerical properties. For each power of 3, we seek a number $x_k$ satisfying:
$$ x_k^2 \equiv 7 \mod{3^k} $$

Knowing $x_1 \equiv 1 \mod{3}$ or $x_1 \equiv 2 \mod{3}$, to determine $x_2$, we probe numbers in the form $3m + 1$ and $3m + 2$ where $m$ is an integer, and square them to check if they yield a remainder of 7 modulo 9. After pinpointing $x_2$, we quest for $x_3$ in the guise $3^2m + x_2$, and so forth, culminating at $x_{100}$.

#### Step 5: Generalize the Pattern

Upon establishing a pattern, the method can be universally applied in an iterative manner to derive the solution modulo $3^{100}$. Each stage effectively solves a lesser quadratic congruence modulo $3^k$ and leverages that resolution to ascend to $3^{k+1}$.

This procedural narrative is computationally demanding and unfeasible manually for towering exponents like $3^{100}$. Typically, a computer algebra system would be engaged for such calculations.

Notably, this explanation presupposes the presence of a solution at each juncture, which isn't always a given. The actual computations to confirm solution existence and to locate them would be far more intricate, surpassing mere theoretical exposition and necessitating tangible computation.

# Hensel's Lemma 
Hensel's Lemma is a fundamental result in number theory, particularly in the field of p-adic analysis. This lemma provides a powerful tool for lifting solutions of equations modulo prime powers to solutions modulo higher prime powers. In this discussion, we will explore the details of Hensel's Lemma, its corollaries, lemmas, and provide a proof of this important result.

**Hensel's Lemma Statement**

Let $f(x)$ be a polynomial with integer coefficients, and let $p$ be a prime number. Suppose there exists an integer $a$ such that $f(a) \equiv 0 \pmod{p}$ and $f'(a) \not\equiv 0 \pmod{p}$, where $f'(x)$ denotes the derivative of $f(x)$. Then, for any positive integer $n$, if $a_n$ is an integer satisfying $a_n \equiv a \pmod{p^n}$ and $f(a_n) \equiv 0 \pmod{p^{n+1}}$, then there exists an integer $a_{n+1}$ such that $a_{n+1} \equiv a_n \pmod{p^{n+2}}$ and $f(a_{n+1}) \equiv 0 \pmod{p^{n+2}}$.

**Proof of Hensel's Lemma**

To prove Hensel's Lemma, we will use Taylor series expansion and the notion of p-adic numbers. First, let's expand $f(x)$ using Taylor's series around $a$:

$$
f(x) = f(a) + (x-a)f'(a) + \frac{(x-a)^2}{2!}f''(a) + \frac{(x-a)^3}{3!}f'''(a) + \ldots
$$

Since $f(a) \equiv 0 \pmod{p}$, we have:

$$
f(x) \equiv (x-a)f'(a) \pmod{p}
$$

Now, let's consider the congruence modulo $p^2$:

$$
f(x) \equiv (x-a)f'(a) \pmod{p^2}
$$

Since $f'(a) \not\equiv 0 \pmod{p}$, we can find an integer $b_1$ such that:

$$
b_1f'(a) \equiv 1 \pmod{p}
$$

Multiplying both sides by $b_1$ in the congruence above, we get:

$$
b_1f(x) \equiv b_1(x-a) \pmod{p^2}
$$

Now, let $a_1 = a + b_1(x-a)$. We can see that $a_1 \equiv a \pmod{p}$ and $b_1f(x) \equiv a_1 - a \pmod{p^2}$. Therefore, $a_1$ satisfies the conditions for $n = 1$ in Hensel's Lemma.

We can repeat this process for higher powers of $p$. Given $a_n$ satisfying $a_n \equiv a \pmod{p^n}$ and $f(a_n) \equiv 0 \pmod{p^{n+1}}$, we can find an integer $b_n$ such that:

$$
b_nf(x) \equiv a_n - a \pmod{p^{n+1}}
$$

Now, let $a_{n+1} = a_n + b_n(x-a)$. We have $a_{n+1} \equiv a_n \pmod{p^{n+2}}$, and using the congruence $b_nf(x) \equiv a_n - a \pmod{p^{n+1}}$, we can show that $f(a_{n+1}) \equiv 0 \pmod{p^{n+2}}$. This completes the induction step, and we have shown that Hensel's Lemma holds for all positive integers $n$.

**Corollaries and Applications**

Hensel's Lemma has several important corollaries and applications in number theory:

1. **Corollary 1**: If $f(x)$ is a polynomial with integer coefficients, and there exists an integer $a$ such that $f(a) \equiv 0 \pmod{p}$ and $f'(a) \not\equiv 0 \pmod{p}$, then for any integer $b$ satisfying $b \equiv a \pmod{p}$, there exists a unique integer $x$ such that $x \equiv b \pmod{p}$ and $f(x) \equiv 0 \pmod{p}$.

2. **Corollary 2**:

 Hensel's Lemma can be used to find square roots modulo prime powers. Given a prime $p$ and an integer $a$ such that $a \equiv b^2 \pmod{p}$ for some integer $b$, Hensel's Lemma can be applied to find the square root of $a$ modulo higher powers of $p$.

3. **Applications in Diophantine Equations**: Hensel's Lemma is a valuable tool for solving Diophantine equations of the form $f(x) \equiv 0 \pmod{p^n}$, where $f(x)$ is a polynomial with integer coefficients. It allows us to lift solutions from modulo $p^n$ to modulo $p^{n+1}$ until we obtain a solution in the integers.

4. **p-Adic Analysis**: Hensel's Lemma plays a crucial role in p-adic analysis, a branch of number theory that extends the concepts of real and complex analysis to the p-adic numbers. It helps in understanding the local behavior of functions and equations in the p-adic number field.

**Conclusion**

Hensel's Lemma is a powerful tool in number theory, particularly in the study of p-adic numbers and Diophantine equations. It allows us to lift solutions modulo prime powers to solutions modulo higher prime powers, making it a valuable asset in various mathematical applications. The proof of Hensel's Lemma relies on Taylor series expansion and the use of p-adic integers, and its corollaries find applications in solving congruences and Diophantine equations. This lemma stands as a fundamental result in number theory, providing deeper insights into the properties of prime numbers and their role in mathematics.

# Example using Hensel's Lemma
Let's delve into a specific example to understand Hensel's Lemma better. We'll consider the polynomial $f(x) = x^2 - 2$ and work with the prime $p = 3$. Our objective is to find a solution to $f(x) \equiv 0 \pmod{3^n}$ for some $n > 1$.

**Step 1: Initial Conditions**

We begin by identifying an integer $a$ such that $f(a) \equiv 0 \pmod{3}$ and $f'(a) \not\equiv 0 \pmod{3}$. 

- $f(x) = x^2 - 2$
- $f'(x) = 2x$

Upon examination, we discover that $f(1) = 1^2 - 2 = -1 \equiv 2 \pmod{3}$ and $f'(1) = 2 \cdot 1 = 2 \not\equiv 0 \pmod{3}$. Therefore, we select $a = 1$.

**Step 2: Applying Hensel's Lemma**

Our next step is to find $a_2$ such that $f(a_2) \equiv 0 \pmod{3^2}$. According to Hensel's Lemma, we seek $b_1$ satisfying $b_1f'(a) \equiv 1 \pmod{3}$. We have:

- $f'(1) = 2$
- $b_1 \cdot 2 \equiv 1 \pmod{3}$

We find that $b_1 = 2$ fulfills this criterion, as $2 \cdot 2 = 4 \equiv 1 \pmod{3}$.

We then calculate $a_2$:

- $a_2 = a + b_1(f(a) \div p)$
- Given $f(1) = -1$, we obtain $a_2 = 1 + 2(-1 \div 3) = 1$ (noting that $-1 \div 3$ is 0 in integer division).

**Step 3: Verify Solution**

We now verify if $f(a_2) \equiv 0 \pmod{3^2}$:

- $f(1) = 1^2 - 2 = -1 \equiv 8 \pmod{9}$

Thus, $a_2 = 1$ does not solve $f(x) \equiv 0 \pmod{9}$.

**Conclusion**

In this scenario, Hensel's Lemma does not yield a solution to $f(x) \equiv 0 \pmod{9}$ starting from $a = 1$. This example illustrates that while Hensel's Lemma is a potent tool, it doesn't guarantee a solution for every polynomial and modulus $p^n$. The outcome is contingent on initial conditions and the specific polynomial. For certain polynomials and moduli, the process may require multiple iterations or a different initial $a$, and in some cases, no solution can be elevated to higher powers of $p$.

# "Lifting"
In the context of Hensel's Lemma and number theory, "lifting" refers to the process of finding a solution to a congruence equation at a higher power of a prime, given a solution at a lower power. This concept is specifically relevant when working with modular arithmetic and polynomial equations.

To illustrate:

1. **Initial Solution:** You start with a solution to a congruence equation modulo a prime number $p$, for instance, finding $a$ such that $f(a) \equiv 0 \pmod{p}$.

2. **Lifting to a Higher Power:** The process of "lifting" involves extending this solution to a higher power of $p$, say $p^n$. The goal is to find an integer $a_n$ such that $f(a_n) \equiv 0 \pmod{p^n}$, where $a_n$ is congruent to $a$ modulo $p$.

3. **Hensel's Lemma:** This lemma provides a methodical approach to lifting solutions. It stipulates the conditions under which a solution to $f(x) \equiv 0 \pmod{p}$ can be "lifted" to a solution modulo $p^n$.

In summary, in this context, "lifting" means systematically elevating a solution from a simpler congruence equation (modulo $p$) to a more complex one (modulo $p^n$), while maintaining the congruence relationship.

# Examples of Lifting
To demonstrate the concept of lifting in the context of Hensel's Lemma, let's consider two examples – one where lifting can take place and another where it cannot. These examples will help appeal to your intuition about the underlying principles.

### Example 1: Lifting Can Take Place

**Polynomial:** $f(x) = x^2 - 1$

**Prime:** $p = 2$

#### Initial Conditions
- We need to solve $f(x) \equiv 0 \pmod{2}$.
- $f(1) = 1^2 - 1 = 0$, so $x = 1$ is a solution modulo 2.

#### Lifting the Solution
- Next, we want to lift this solution to solve $f(x) \equiv 0 \pmod{4}$ (i.e., $p^n$ with $n=2$).
- $f'(x) = 2x$. Thus, $f'(1) = 2 \not\equiv 0 \pmod{2}$.
- This satisfies the condition for lifting as per Hensel's Lemma.

#### Finding the Lifted Solution
- We find $b$ such that $b \cdot f'(1) \equiv 1 \pmod{2}$. Here, $b = 1$ works.
- Calculate $x_2 = 1 + 1 \cdot 0 = 1$. (Note: $f(1)$ is 0, so the term $1 \cdot 0$ becomes 0).
- Verify: $f(1) = 1^2 - 1 = 0 \equiv 0 \pmod{4}$.

#### Conclusion
- The solution $x = 1$ modulo 2 is successfully lifted to $x = 1$ modulo 4.

### Example 2: Lifting Cannot Take Place

**Polynomial:** $f(x) = x^2 + 1$

**Prime:** $p = 2$

#### Initial Conditions
- Solve $f(x) \equiv 0 \pmod{2}$.
- $f(0) = 0^2 + 1 = 1$ and $f(1) = 1^2 + 1 = 2 \equiv 0 \pmod{2}$, so $x = 1$ is a solution modulo 2.

#### Attempting to Lift the Solution
- Now, let's try to lift this solution to $p^n$ with $n=2$, i.e., modulo 4.
- $f'(x) = 2x$. Thus, $f'(1) = 2 \equiv 0 \pmod{2}$.

#### Why Lifting Fails
- For lifting to occur, $f'(a)$ must not be congruent to 0 modulo $p$. Here, $f'(1) = 2 \equiv 0 \pmod{2}$.
- This violates the condition of Hensel's Lemma. Hence, we cannot find a suitable $b$ that satisfies the necessary congruence for lifting.

#### Conclusion
- The solution $x = 1$ modulo 2 cannot be lifted to a solution modulo 4 for the polynomial $f(x) = x^2 + 1$ using Hensel's Lemma.

### Intuitive Understanding
- In the first example, the derivative of the polynomial at the solution was non-zero modulo $p$, allowing us to "adjust" the solution as we moved to a higher modulus.
- In the second example, the derivative was zero modulo $p$, leaving us with no room to adjust the solution for a higher modulus, thus failing the lifting process.
- Think of lifting as tweaking a solution at a lower level to fit a more complex level, like adjusting a key to fit a more complex lock. If the initial conditions don't provide enough "wiggle room" (non-zero derivative), this adjustment isn't possible.

# Key Point of Integer Coefficient
The integral coefficient condition in Hensel's Lemma is crucial for ensuring that the solutions we lift from a lower modulus to a higher modulus remain within the realm of integers. This is particularly important because Hensel's Lemma operates in the setting of modular arithmetic and polynomial equations, where solutions are expected to be integers.

Let's break down the significance of this condition:

1. **Polynomial with Integral Coefficients:** Hensel's Lemma is applied to polynomials with integral coefficients. This means each term of the polynomial is an integer multiplied by a power of the variable. For example, in a polynomial $f(x) = a_n x^n + a_{n-1} x^{n-1} + \ldots + a_1 x + a_0$, each $a_i$ is an integer.

2. **Maintaining Integer Solutions:** One of the objectives of Hensel's Lemma is to find integer solutions to congruences. When we start with a polynomial with integral coefficients, the arithmetic operations involved in the process (like addition, multiplication, and taking moduli) all preserve the integrality of the solutions. This is crucial because if the coefficients were not integral, the operations could lead to non-integral solutions, which are not meaningful in this context.

3. **Lifting Process:** When lifting a solution from a modulus of $p$ to $p^n$, we often deal with expressions that involve the coefficients of the polynomial. The fact that these coefficients are integers ensures that the lifted solutions (and intermediary calculations) also yield integer values. This keeps the solutions applicable within the realm of modular arithmetic, where non-integer solutions are not relevant.

4. **Consistency and Applicability:** The condition of integral coefficients ensures that the solutions and processes of Hensel's Lemma are consistent and applicable within number theory and related fields. It ensures that the lemma is grounded in the standard framework of integers and modular arithmetic.

In summary, the integral coefficient condition is essential in Hensel's Lemma to maintain the integrity and applicability of the solutions within the integer domain, which is the foundation of modular arithmetic and many areas of number theory.

# Newton's Method for mod $p^n$
Newton's method, also known as the Newton-Raphson method, is a powerful technique for finding successively better approximations to the roots (or zeroes) of a real-valued function. Its application in the context of modular arithmetic, specifically for $\mod p^n$ where $p$ is a prime and $n$ is a positive integer, involves a few modifications to adapt it to the discrete nature of modular arithmetic.

The basic idea of Newton's method in this context is to find an integer $x$ such that $f(x) \equiv 0 \mod p^n$, where $f$ is a polynomial with integer coefficients. The method involves iterating an equation to improve an initial guess $x_0$ until a satisfactory approximation of the root is achieved.

Here's how it works:

1. **Initial Guess**: Start with an initial guess $x_0$ such that $f(x_0) \equiv 0 \mod p$. This is often the hardest part and may involve some trial and error or other methods to find a suitable $x_0$.

2. **Iteration**: Given a current approximation $x_k$, compute the next approximation $x_{k+1}$ using the formula:
   $$ x_{k+1} = x_k - \frac{f(x_k)}{f'(x_k)} \mod p^n $$
   where $f'(x_k)$ is the derivative of $f$ evaluated at $x_k$.

3. **Convergence**: Repeat the iteration until $x_{k+1} \equiv x_k \mod p^n$, which means a sufficiently accurate approximation has been found.

4. **Handling Derivative Inverses**: In modular arithmetic, division is not always straightforward. The term $\frac{1}{f'(x_k)}$ actually means the modular inverse of $f'(x_k)$ modulo $p^n$, which exists if $f'(x_k)$ is not divisible by $p$.

5. **Accuracy and Precision**: The accuracy of the approximation improves with each iteration, and the number of correct digits roughly doubles with each step. However, care must be taken to ensure that the intermediate calculations are performed with sufficient precision.

The method is particularly useful for finding square roots modulo $p^n$ and for solving polynomial equations where other methods are less efficient. The key to its success lies in a good initial guess and careful handling of the modular arithmetic involved.

# Example of Newton Raphson Method 
Let's consider a concrete example of using Newton-Raphson's method in modular arithmetic. Suppose we want to find the square root of a number $a$ modulo $p^n$, where $p$ is a prime and $n$ is a positive integer. The square root of $a$ is a number $x$ such that $x^2 \equiv a \mod p^n$.

**Problem Statement**: Find a square root of $a = 10$ modulo $p^n$ where $p = 3$ and $n = 2$ (i.e., modulo $9$).

1. **Function and Derivative**: 
   - We define $f(x) = x^2 - a$.
   - Its derivative is $f'(x) = 2x$.

2. **Initial Guess ($x_0$)**: 
   - Choose an initial guess $x_0$ such that $f(x_0) \equiv 0 \mod p$. 
   - For simplicity, let's choose $x_0 = 1$ (since $1^2 \equiv 1 \mod 3$ and $10 \equiv 1 \mod 3$).

3. **Iteration Formula**: 
   - $x_{k+1} = x_k - \frac{f(x_k)}{f'(x_k)} \mod 9$.

4. **Modular Inverse**: 
   - We need to find the modular inverse of $f'(x_k) = 2x_k \mod 9$ in each iteration.

5. **Iteration Process**:
   - We iterate this process, starting from $x_0 = 1$, and continue until we find a $x_{k+1}$ such that $x_{k+1}^2 \equiv a \mod 9$.

Let's perform these calculations using Python to find the square root of $10$ modulo $9$.

Using Newton-Raphson's method in modular arithmetic, we find that the square root of $10$ modulo $9$ ($3^2$) is $1$. This means that $1^2 \equiv 10 \mod 9$. 

In this example, the method converged quickly, likely because the initial guess $x_0 = 1$ was already quite close to the solution. The process is iterative and in each step, it refines the approximation based on the modular arithmetic principles. The key steps were defining the function and its derivative, choosing an initial guess, and then iteratively applying the Newton-Raphson formula in the context of modular arithmetic.