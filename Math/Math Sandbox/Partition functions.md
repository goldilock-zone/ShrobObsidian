Partition functions are fundamental objects in both number theory and statistical mechanics, although they have distinct meanings in each context. Following the structured format you prefer:

1. **Partition Functions in Number Theory**:
   - **Definition**: In number theory, a partition of a positive integer \( n \) is a way of writing \( n \) as a sum of positive integers, where the order of addends does not matter. The partition function \( p(n) \) counts the number of distinct partitions of \( n \).
   - **Example**: For \( n = 4 \), the partitions are \( 4 \), \( 3 + 1 \), \( 2 + 2 \), \( 2 + 1 + 1 \), and \( 1 + 1 + 1 + 1 \), so \( p(4) = 5 \).

2. **Generating Function of Partition Function**:
   - **Representation**: The generating function for \( p(n) \) is an infinite product:
     $$
     \sum_{n=0}^{\infty} p(n)q^n = \prod_{k=1}^{\infty} \frac{1}{1 - q^k}
     $$
   - **Significance**: This representation connects partition functions to modular forms and \( q \)-series, providing a rich field of study in number theory.

3. **Hardy-Ramanujan Asymptotic Formula**:
   - **Asymptotic Behavior**: Hardy and Ramanujan derived a famous asymptotic formula for \( p(n) \), showing that it grows exponentially with the square root of \( n \).
   - **Formula**: The formula is \($$ p(n) \sim \frac{1}{4n\sqrt{3}} e^{\pi \sqrt{\frac{2n}{3}}} \) as \( n \rightarrow \infty $$\).

4. **Partition Functions in Statistical Mechanics**:
   - **Physical Context**: In statistical mechanics, a partition function is a sum over all possible states of a system, weighted by the Boltzmann factor \( e^{-\beta E} \), where \( \beta \) is the inverse temperature and \( E \) is the energy of a state.
   - **Role**: It plays a central role in determining the macroscopic properties of a system, like temperature, pressure, and entropy, from its microscopic states.

5. **Significance Across Fields**:
   - **Number Theory**: In number theory, partition functions reveal deep insights into the arithmetic and combinatorial properties of numbers.
   - **Physics**: In physics, the partition function is a cornerstone of statistical mechanics, essential for understanding thermodynamics and quantum field theory.

Partition functions, therefore, embody critical concepts in both number theory and physics, showcasing the beauty and utility of mathematical structures in diverse fields.