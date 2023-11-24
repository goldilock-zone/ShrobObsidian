Cayley's Theorem is a fundamental result in group theory, a branch of abstract algebra. It states that every group $G$ is isomorphic to a subgroup of the symmetric group acting on $G$. This implies that every abstract group can be represented concretely as a group of permutations of a set.

To understand this theorem, consider the following key concepts:

- A **group** is a set equipped with an operation that combines any two elements to form a third element, satisfying four conditions: closure, associativity, the existence of an identity element, and the existence of inverse elements.
- The **symmetric group** on a set $G$, denoted as $S_G$, consists of all bijective functions (permutations) from $G$ to itself.
- An **isomorphism** between two groups is a bijective function that respects the group operation.

Cayley's Theorem essentially says that any group $G$ of order $n$ (i.e., having $n$ elements) can be represented as a subgroup of the [[symmetric group]] $S_n$. 

The isomorphism is constructed as follows:

1. For each element $g$ in $G$, define a function $\sigma_g : G \rightarrow G$ by $\sigma_g(x) = gx$ for all $x$ in $G$.
2. The set of these functions, $\{\sigma_g | g \in G\}$, forms a subgroup of the symmetric group $S_G$.
3. The mapping $\phi: G \rightarrow S_G$ defined by $\phi(g) = \sigma_g$ is an isomorphism.

Therefore, every element of $G$ corresponds to a permutation of the elements of $G$, and the group operation in $G$ corresponds to the composition of permutations in $S_G$. This theorem demonstrates the universality of the concept of permutation in the study of groups.

# Algorithm to make a group out of symmetries
To construct a group from a set of symmetries, you can employ an algorithmic approach rooted in the principles of group theory, a branch of mathematics that studies such structures. The central idea is to formalize the symmetries of a given object (like a geometric shape) as transformations and then define a group structure on these transformations. Here's a step-by-step description of the algorithm:

1. **Identify the Set of Symmetries**: Begin by identifying all possible symmetries of the object in question. These symmetries could include reflections, rotations, translations, or any other transformation that preserves some aspect of the object. For example, in the case of a square, the symmetries include four rotations (including the identity, or do-nothing transformation) and four reflections.

2. **Define the Transformations**: Each symmetry is represented as a transformation. In mathematical terms, a transformation is a function that maps the object to itself while preserving some structure. These transformations are the elements of your set.

3. **Verify Closure Under Composition**: To form a group, the set of transformations must be closed under composition. This means that the composition (sequential application) of any two transformations in the set must also be a transformation in the set. For example, the composition of two rotations of a square is another rotation of the square.

4. **Check for an Identity Element**: Ensure that there is an identity transformation in your set, which leaves the object unchanged. In group theory, this is the element that, when composed with any other element, leaves the other element unchanged.

5. **Ensure the Existence of Inverses**: For each transformation in the set, there must be an inverse transformation that, when composed, results in the identity transformation. For example, the inverse of a 90-degree rotation is a 270-degree rotation.

6. **Confirm Associativity**: Ensure that the composition of transformations is associative. In mathematical terms, this means for any three transformations $a, b,$ and $c$, the equation $(a \circ b) \circ c = a \circ (b \circ c)$ always holds.

7. **Define the Group**: Once these properties are verified, the set of transformations, together with the operation of composition, forms a group. This group is often referred to as a symmetry group, reflecting the symmetrical properties of the object.

8. **Optional - Determine Group Properties**: Once you have established that the set forms a group, you might analyze its properties further. Is it abelian (commutative)? What is its order (the number of elements)? Does it have any subgroups or normal subgroups?

This process is foundational in abstract algebra and has wide applications in various fields of mathematics, physics, and beyond, as it captures the essence of symmetry in a rigorous, algebraic framework.

# Uses in Chemistry
- Rotations of molecules
- crystallography

# Frieze Patterns and Frieze Groups
Frieze patterns and frieze groups are fascinating concepts in the field of mathematics, particularly within the study of symmetry and crystallography. These concepts encapsulate the artistic and the mathematical, merging aesthetics with the precision of algebra and geometry.

### Frieze Patterns

A frieze pattern is an infinite strip that exhibits a specific type of symmetry. These patterns extend infinitely in one direction, and they are periodic, meaning they repeat at regular intervals. You can imagine them as decorative borders that could extend infinitely along a wall, ceiling, or floor.

### Frieze Groups

There are exactly seven types of frieze groups, each representing a different kind of symmetry that a frieze pattern can have. These symmetries include translations, rotations, reflections, and glide reflections. The classification into seven groups is based on the presence or absence of these symmetries.

Let's describe each group using mathematical symbols:

1. **Translation only ($p1$):** The simplest type. The pattern repeats by translation alone.
   
   $$ T(x) = x + n\lambda, \quad n \in \mathbb{Z} $$
   
   where $\lambda$ is the repeat distance, and $T$ is the translation function.

2. **Translation and horizontal reflection ($p11m$):** Reflection across a horizontal axis.
   
   $$ R_y(x, y) = (x, -y) $$

3. **Translation and vertical reflection ($p11g$):** Reflection across a vertical axis.
   
   $$ R_x(x, y) = (-x, y) $$

4. **Translation and glide reflection ($p1m1$):** A glide reflection combines a reflection and a translation parallel to the axis of reflection.
   
   $$ G(x, y) = (-x, y + n\lambda) $$

5. **Translation and 180-degree rotation ($p2$):** Involves a half-turn rotation.
   
   $$ R_{180}(x, y) = (-x, -y) $$

6. **Translation, horizontal reflection, and 180-degree rotation ($p2mm$):** A combination of reflections and rotations.
   
   $$ R_{y, 180}(x, y) = R_y(R_{180}(x, y)) $$

7. **Translation, glide reflection, and 180-degree rotation ($p2mg$):** This incorporates glide reflection and rotation.
   
   $$ G_{180}(x, y) = G(R_{180}(x, y)) $$

Each group encapsulates a unique symmetry, and understanding these symmetries allows for a deeper appreciation of both the mathematical and the aesthetic qualities of frieze patterns.

