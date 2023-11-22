Georg Cantor indeed made significant contributions to set theory, and one of his most famous results is related to the concept of the power set and the comparison of cardinalities. Cantor's theorem states that for any set A, the cardinality of the power set of A (denoted as P(A)) is strictly greater than the cardinality of A itself. In other words, there is no one-to-one correspondence (bijection) between a set and its power set.

Here's a proof sketch of Cantor's theorem:

1. Suppose you have a set A.
2. To show that |A| < |P(A)|, we assume for the sake of contradiction that there exists a bijection (one-to-one correspondence) f: A → P(A).
3. We will now construct a subset B of A that is not in the range of f, leading to a contradiction.

For each element x in A, we define a subset B_x of A as follows:

B_x = {y ∈ A : y ∉ f(x)}

In other words, B_x contains all elements of A that are not in the image of x under the function f. Now, we define the subset B of A as the union of all these subsets B_x:

B = ⋃{B_x : x ∈ A}

Now, let's consider an element a in A. Is a in the subset B_a? Well, it depends on whether a is in the set f(a) or not. If a is in f(a), then a ∉ B_a because B_a contains elements not in f(a). On the other hand, if a is not in f(a), then a ∈ B_a because B_a contains elements that are not in f(a). So, no matter what, a ∈ B if and only if a ∉ f(a). This means that a is not in the range of f.

Now, we have shown that for every element a in A, a is not in the range of f. This means that B contains elements from A that are not in the image of f, which implies that B is not in P(A) because P(A) consists of all subsets of A. Therefore, B cannot be in the range of f.

This leads to a contradiction because we assumed that f was a bijection from A to P(A), but we have found an element B in A that is not in the range of f. This contradiction shows that our initial assumption of the existence of such a bijection f is false.

Therefore, we conclude that |A| < |P(A)|, meaning the cardinality of the power set of A is strictly greater than the cardinality of A. This is the essence of Cantor's theorem, which has profound implications in set theory and the study of different sizes of infinite sets.