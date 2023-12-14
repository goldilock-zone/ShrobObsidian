Chevalley-Warning Theorem states that if $p$ is a prime number and $f_1, f_2, ..., f_r$ are polynomials in $\mathbb{Z}[x_1, x_2, ..., x_n]$ such that the sum of their degrees is less than $n$, then the number of common zeros of these polynomials modulo $p$ is a multiple of $p$. 

**Lemma (Euler's Criterion)**: Given a prime $p$ and an integer $a$ not divisible by $p$, $a$ is a quadratic residue modulo $p$ if and only if $a^{\frac{p-1}{2}} \equiv 1 \mod p$.

**Proof of Chevalley-Warning Theorem**:

Let us consider a vector space $V$ over the [[finite field]] $\mathbb{F}_p$. For each polynomial $f_i$, define the function $e_i: V \to \mathbb{F}_p$ by $e_i(\mathbf{x}) = \exp(2\pi i f_i(\mathbf{x})/p)$. The sum of the degrees of the $f_i$ is less than $n$, implying by the hypothesis of the theorem that $\sum_{i=1}^r \deg(f_i) < n$.

The number of solutions to the system $f_1 = f_2 = ... = f_r = 0$ modulo $p$ is the same as the number of $\mathbf{x} \in V$ such that $e_i(\mathbf{x}) = 1$ for all $i$. Consider the product $E(\mathbf{x}) = \prod_{i=1}^r e_i(\mathbf{x})$. By construction, $E(\mathbf{x}) = 1$ if and only if each $e_i(\mathbf{x}) = 1$, which occurs if and only if $\mathbf{x}$ is a common zero of the $f_i$ modulo $p$.

We want to evaluate the sum $S = \sum_{\mathbf{x} \in V} E(\mathbf{x})$. The term $E(\mathbf{x})$ contributes $1$ to the sum if $\mathbf{x}$ is a common zero and some non-one $p$-th root of unity otherwise. 

Now, if $\mathbf{x}$ is not a common zero, then at least one of the $f_i(\mathbf{x})$ is not divisible by $p$, and the corresponding $e_i(\mathbf{x})$ is a nontrivial $p$-th root of unity. The sum over all such $\mathbf{x}$ of any nontrivial $p$-th root of unity is $0$, since for each root of unity, there are precisely $p-1$ others that are its negatives.

Therefore, the sum $S$ reduces to counting just the common zeros of the $f_i$. This number is the same as $S$ modulo $p$, but $S$ is also the sum of $p^n$ $p$-th roots of unity. Since $\sum_{i=1}^r \deg(f_i) < n$, we have $p^n \equiv 0 \mod p$.

Thus, the number of common zeros, which is $S$, must be congruent to $0$ modulo $p$. This concludes the proof that the number of common zeros is a multiple of $p$.

**Corollary**: If $n$ is greater than the sum of the degrees of the polynomials, there is at least one non-trivial solution modulo $p$.

The Chevalley-Warning Theorem has implications in the field of number theory and algebraic geometry, particularly in the understanding of the distribution of solutions to polynomial equations over finite fields. It is related to results such as the Hasse-Weil bound and can be seen as a precursor to the more general Weil conjectures. 

The theorem is also used in combinatorics, specifically in the study of [[combinatorial nullstellensatz]], which provides a method for proving combinatorial statements using polynomial method. It is interesting to ponder the theorem's effectiveness in proving existence theorems where counting methods are insufficient. The theorem's strength lies in its ability to handle a system of polynomial equations rather than a single equation.    

# Alternate Version of Chevalley - Warning Theorem

Let $f(x_1, \ldots, x_n)$ be a polynomial in $n$ variables over a finite field $\mathbb{F}_p$, where $p$ is a prime. If the degree $d$ of $f$ is less than the number of variables $n$, then the number of solutions to the congruence $f(x_1, \ldots, x_n) \equiv 0 \mod p$ is divisible by $p$.

To provide a proof, we need to leverage several concepts from number theory and algebra:

**Lemma 1 (Fermat's Little Theorem)**: For any integer $a$ and a prime $p$, if $a$ is not divisible by $p$, then $a^{p-1} \equiv 1 \mod p$.

**Lemma 2 (Polynomial Factorization)**: Over a field, a polynomial of degree $d$ has at most $d$ roots.

**Lemma 3 (Lagrange's Theorem)**: In a finite group of order $m$, for any element $g$ of the group, the order of $g$ (the smallest positive integer $k$ such that $g^k$ is the identity element) divides $m$.

**Proof of Chevalley-Warning Theorem**:

Consider the polynomial $f(x_1, \ldots, x_n)$ over $\mathbb{F}_p$ and define the function $E: \mathbb{F}_p^n \to \mathbb{F}_p$ by $E(\mathbf{x}) = \exp(2\pi i f(\mathbf{x})/p)$, where $\mathbf{x} = (x_1, \ldots, x_n)$. 

The number of solutions to $f(x_1, \ldots, x_n) \equiv 0 \mod p$ is equal to the sum:
$$
S = \sum_{\mathbf{x} \in \mathbb{F}_p^n} E(\mathbf{x}).
$$
$E(\mathbf{x}) = 1$ if $f(\mathbf{x}) \equiv 0 \mod p$ and is a nontrivial $p$-th root of unity otherwise.

For each $a \in \mathbb{F}_p$, define the sum $T_a = \sum_{x \in \mathbb{F}_p} \exp(2\pi i a x/p)$. By the orthogonality of characters, $T_a = 0$ unless $a \equiv 0 \mod p$, in which case $T_a = p$.

We can then write $S$ as a product of sums, each of which is similar to $T_a$:
$$
S = \sum_{\mathbf{x} \in \mathbb{F}_p^n} \prod_{j=1}^n \exp(2\pi i f_j(\mathbf{x})/p),
$$
where $f_j$ is the $j$-th monomial term of $f$.

Since the degree of $f$ is less than $n$, each $f_j(\mathbf{x})$ contributes to a sum that is zero unless $f_j(\mathbf{x}) \equiv 0 \mod p$ for all $\mathbf{x}$. Thus, $S$ is non-zero only when each component sum is non-zero, which occurs only when $f(\mathbf{x}) \equiv 0 \mod p$. 

By expanding $S$ and using Lemma 1, we note that each summand $E(\mathbf{x})$ is $1$ for each solution to $f(\mathbf{x}) \equiv 0 \mod p$, and the sum of roots of unity otherwise. As such, $S$ is congruent to the number of solutions modulo $p$.

Finally, since $S$ is the sum of $p^n$ terms, each of which is a $p$-th root of unity, and $p^n \equiv 0 \mod p$, it follows that the number of solutions, which is $S$ modulo $p$, is also divisible by $p$. This completes the proof.

The Chevalley-Warning theorem implies that if the number of solutions is non-zero, it must be at least $p$, providing a lower bound on the number of solutions. This result can be applied recursively to sets of polynomials, leading to further implications in the study of algebraic varieties over finite fields.

# Sum of powers of integers modulo a prime number.

$$ 0^i + 1^i + 2^i + \ldots + (p-1)^i \equiv 0 \ (\text{mod}\ p) \quad \text{if} \ i < (p-1). $$
The lemma you're referring to is generally associated with properties that arise from Fermat's Little Theorem and can be seen as a specific case of the more general properties of sums in finite fields. The name of the lemma is not specified in the image you provided, and it might not have a specific name as it is a less commonly cited result than Fermat's Little Theorem or Euler's Theorem. Nonetheless, it is a property of the sum of powers of consecutive integers modulo a prime.

Let's prove the lemma:

Lemma Statement:
For a prime $p$ and an integer $i$ such that $0 \leq i < p-1$, the sum of the $i$-th powers of the first $p-1$ positive integers is divisible by $p$:
$$ 0^i + 1^i + 2^i + \ldots + (p-1)^i \equiv 0 \ (\text{mod}\ p). $$

Proof:
To prove this, we need to use the properties of arithmetic in $\mathbb{Z}_p$, the field of integers modulo $p$.

1. In $\mathbb{Z}_p$, the non-zero elements form a multiplicative group of order $p-1$. 

2. The sum in question can be written as a sum of geometric progressions if $i > 0$. For any non-zero element $a \in \mathbb{Z}_p$, the sequence $a^0, a^1, \ldots, a^{p-2}$ is a permutation of $1, 2, \ldots, p-1$ because the multiplicative group of non-zero elements of $\mathbb{Z}_p$ is cyclic.

3. Fermat's Little Theorem states that $a^{p-1} \equiv 1 \ (\text{mod}\ p)$ for any integer $a$ that is not divisible by $p$. 

4. For $1 \leq a \leq p-1$, we have $a^i \equiv (a^1)^i \equiv (a^2)^i \equiv \ldots \equiv (a^{p-1})^i \ (\text{mod}\ p)$, as raising to the $i$-th power is a homomorphism on the multiplicative group.

5. Thus, for each $a$, we have $p-1$ terms in the sequence $(a^0)^i, (a^1)^i, \ldots, (a^{p-2})^i$ that are congruent modulo $p$. The sum of these terms, by the geometric series formula (and since $i < p-1$, preventing us from simply having $p-1$ copies of $1$), is:

$$ \frac{a^{i(p-1)} - 1}{a^i - 1} \equiv 0 \ (\text{mod}\ p). $$

6. Since the denominator is not zero (as $i < p-1$ and thus $a^i \not\equiv 1$), and the numerator is zero (by Fermat's Little Theorem), the entire fraction is congruent to zero modulo $p$.

7. Since this is true for each $a$, the sum over all $a$ from $1$ to $p-1$ is also congruent to zero modulo $p$.

Therefore, the sum of the $i$-th powers of the first $p-1$ positive integers is divisible by $p$ when $i < p-1$. 

This result doesn't usually go by a specific name, as it is not as widely recognized as the theorems of Fermat or Euler, but it is a useful lemma in the study of the distribution of powers modulo a prime. 

Definitions:
- **Prime number ($p$)**: A natural number greater than 1 that has no positive divisors other than 1 and itself.
- **Modulo operation**: Given two numbers, $a$ and $b$, the modulo operation finds the remainder when $a$ is divided by $b$.
- **Congruence modulo $p$**: Two integers $a$ and $b$ are said to be congruent modulo $p$, denoted $a \equiv b \ (\text{mod}\ p)$, if $p$ divides the difference $a-b$.
- **Fermat's Little Theorem**: If $p$ is a prime number, then for any integer $a$ not divisible by $p$, $a^{p-1} \equiv 1 \ (\text{mod}\ p)$.

[[Norms of Field Extensions]]
