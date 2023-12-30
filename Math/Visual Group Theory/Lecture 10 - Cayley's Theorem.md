Cayley's Theorem is a fundamental result in group theory that provides a powerful connection between abstract groups and permutations. It was named after the British mathematician Arthur Cayley and has significant implications for understanding group structures. This theorem can be succinctly stated as follows:

**Cayley's Theorem:** Every group $G$ is isomorphic to a subgroup of the symmetric group $S_n$, where $n$ is the order (number of elements) of the group $G$.

Let's break down the components of Cayley's Theorem and explore its implications:

1. **Group Isomorphism:** An isomorphism between two groups $G$ and $H$ is a bijective function $\phi: G \rightarrow H$ that preserves the group operation. In other words, for all $a, b \in G$, $\phi(ab) = \phi(a)\phi(b)$. When two groups are isomorphic, they have the same group structure, despite potentially having different elements.

2. **Symmetric Group $S_n$:** The symmetric group $S_n$ consists of all permutations of $n$ elements. In this context, permutations are bijective functions that rearrange the elements without altering their identity.

Now, let's explore the key points related to Cayley's Theorem:

### Proof of Cayley's Theorem:
The proof of Cayley's Theorem relies on considering the group of permutations of $G$ itself, denoted as $S_G$. This group consists of bijective functions from $G$ to itself.

1. **Construction of the Isomorphism:** The proof constructs an isomorphism $\phi: G \rightarrow H$, where $H$ is a subgroup of $S_G$. The isomorphism $\phi$ maps each element $g \in G$ to the permutation $\sigma_g \in H$, where $\sigma_g$ is defined as $\sigma_g(x) = gx$ for all $x \in G$.

2. **Show Isomorphism Properties:** The proof then proceeds to show that $\phi$ preserves the group operation in both $G$ and $H$. Specifically, it demonstrates that for all $g_1, g_2 \in G$, $\phi(g_1g_2) = \sigma_{g_1g_2}$ is equivalent to $\phi(g_1)\phi(g_2) = \sigma_{g_1}\sigma_{g_2}$.

3. **Bijectiveness of $\phi$:** The proof establishes that $\phi$ is bijective, meaning it has an inverse $\phi^{-1}$, which implies that $G$ and $H$ have the same order (cardinality).

4. **Conclusion:** As a result of the above steps, it is concluded that $G$ is isomorphic to a subgroup of $S_G$, which is the symmetric group of permutations of $G$. This subgroup of $S_G$ is essentially the set of left-regular permutations induced by the elements of $G$.

### Implications of Cayley's Theorem:
Cayley's Theorem has several important implications and applications in group theory:

- It allows us to study the abstract properties of a group by examining its permutations, which are often more concrete and easier to work with.
- It provides a way to represent any group as a subgroup of a symmetric group, facilitating the classification of groups and the exploration of their structural properties.
- Cayley's Theorem is a foundational result used in various areas of mathematics, including algebra, combinatorics, and representation theory.

Overall, Cayley's Theorem serves as a bridge between the abstract algebraic structure of groups and the more concrete realm of permutations, enabling deeper insights into group theory.

# Association of a group with a set of permutations
Given a group, we can associate it with a set of permutations using a concept known as group actions. This process allows us to understand how elements of the group can act on a set, effectively producing permutations of that set. Let's explore this concept in a formal and axiomatic manner.

### Group Actions and Permutations:

**Definition 1 (Group Action):** Let $G$ be a group and $X$ be a set. A group action of $G$ on $X$ is a function $\cdot : G \times X \rightarrow X$ that satisfies the following properties for all $g, h \in G$ and $x \in X$:

1. **Identity Element:** $e \cdot x = x$, where $e$ is the identity element of $G$.
2. **Compatibility with Group Operation:** $(gh) \cdot x = g \cdot (h \cdot x)$, for all $g, h \in G$.
   
**Theorem 1 (Permutation Representation):** Given a group action of a group $G$ on a set $X$, there exists a [[homomorphism]] from $G$ to the symmetric group $S_X$, where $S_X$ is the group of permutations on the set $X$. This homomorphism is defined as $\phi: G \rightarrow S_X$, such that for each $g \in G$, $\phi(g)$ is the permutation of $X$ induced by the action of $g$.

**Proof:** 
1. For each $g \in G$, define $\phi(g): X \rightarrow X$ as $\phi(g)(x) = g \cdot x$ for all $x \in X$.

2. Show that $\phi(g)$ is a permutation of $X$:
   - **Injectivity:** If $\phi(g)(x_1) = \phi(g)(x_2)$ for some $x_1, x_2 \in X$, then $g \cdot x_1 = g \cdot x_2$. By the cancellation property in groups, we can conclude that $x_1 = x_2$, which proves injectivity.
   - **Surjectivity:** For any $y \in X$, since $g \cdot (g^{-1} \cdot y) = (g g^{-1}) \cdot y = e \cdot y = y$, we see that $\phi(g)(g^{-1} \cdot y) = y$. Therefore, $\phi(g)$ covers the entire set $X$, confirming surjectivity.
   
3. Show that $\phi$ is a homomorphism:
   - $\phi(gh)(x) = (gh) \cdot x = g \cdot (h \cdot x) = \phi(g)(\phi(h)(x))$ for all $x \in X$. This demonstrates that $\phi(gh) = \phi(g)\phi(h)$, preserving the group operation.

### Implications and Interpretation:

1. **Permutations Induced by Group Elements:** The homomorphism $\phi$ allows us to associate each group element $g \in G$ with a permutation $\phi(g)$ of the set $X$. This permutation represents how the group element acts on the set.

2. **Symmetry Groups and Group Actions:** Group actions provide a way to understand the symmetry inherent in group structures. For example, if $G$ is a group of symmetries, such as the group of rotations and reflections of a geometric object, then the action of $G$ on the points of that object naturally leads to permutations.

3. **Applications:** Group actions and the associated permutation representations find applications in various areas, including algebraic topology, group theory, and combinatorics. They help in analyzing the symmetries and transformations of objects and spaces.

In summary, given a group, we associate it with a set of permutations through the concept of group actions. This association provides a deeper understanding of the group's structure by revealing how its elements act on a given set, leading to permutations that capture these actions. Theorems and definitions from group theory formalize this process and its implications.