
To address the problem of an algorithm with an exponential worst-case time complexity but an average time complexity that is polynomial, we need to explore the concept of average-case analysis and consider algorithms that exhibit such behavior.

**Average-Case Analysis**:
In average-case analysis, we assess the expected performance of an algorithm over a distribution of inputs. This analysis considers not only the worst-case scenario but also takes into account the likelihood of different inputs occurring in practice.

**Polynomial Time Complexity**:
An algorithm is said to have a polynomial time complexity if its runtime is bounded by a polynomial function of the input size. Mathematically, an algorithm has polynomial time complexity if there exist constants $c$ and $k$ such that the runtime $T(n)$ satisfies:

$$
T(n) \leq cn^k
$$

where $n$ is the input size. Common examples of algorithms with polynomial time complexity include linear time ($O(n)$), quadratic time ($O(n^2)$), and cubic time ($O(n^3)$) algorithms.

**Exponential Time Complexity**:
An algorithm is said to have an exponential time complexity if its runtime grows exponentially with the input size. Mathematically, an algorithm has exponential time complexity if the runtime $T(n)$ satisfies:

$$
T(n) = 2^n
$$

where $n$ is the input size. Exponential algorithms are known for their impracticality for large inputs.

**Algorithm with Exponential Worst-Case but Polynomial Average Time Complexity**:

An algorithm that fits this description is the **Quicksort** algorithm with a randomized pivot selection strategy. Quicksort's worst-case time complexity is $O(n^2)$, which occurs when it consistently chooses a poor pivot element. However, with a randomized pivot selection strategy, Quicksort exhibits an average-case time complexity of $O(n \log n)$.

**Explanation**:

1. Quicksort is a sorting algorithm that divides an array into smaller subarrays based on a chosen pivot element and recursively sorts these subarrays. The efficiency of Quicksort greatly depends on the choice of the pivot.

2. In the worst-case scenario, if the pivot is consistently chosen poorly (e.g., always picking the smallest or largest element), Quicksort can exhibit a time complexity of $O(n^2)$, which is quadratic and highly inefficient.

3. However, when a randomized pivot selection strategy is employed, where the pivot is chosen randomly or probabilistically, the average-case time complexity of Quicksort is $O(n \log n)$. This means that, on average, the algorithm efficiently sorts the array in a time proportional to $n \log n$.

4. The key insight here is that by introducing randomness in pivot selection, the algorithm avoids the worst-case behavior, and the probability of encountering a bad pivot repeatedly diminishes as the input size grows.

5. This behavior of Quicksort is often formally analyzed using probabilistic techniques, including the concept of expected values and probability distributions.

**Conclusion**:

In summary, the Quicksort algorithm with a randomized pivot selection strategy exemplifies an algorithm with an exponential worst-case time complexity ($O(n^2)$) but a polynomial average time complexity ($O(n \log n)$). This is achieved by introducing randomness in the algorithm's operation, leading to improved average-case performance while still having a poor worst-case scenario.