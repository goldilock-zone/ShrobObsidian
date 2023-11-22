
### Categorical Equivalences

^e347f7

1. Commutative Diagram:

![[Pasted image 20231029154110.png]]
### Spatial Intelligence
#toread 

### Stages in Classrooms
- Stages in classrooms, might be a convenience in the exposition of a lecture, but it is a spatial structure that creates a placement in the mind of all involved about a hierarchy of being, by virtue of placement. Impermanence of the classroom as an environment of learning, and by extension, a safe one, is propagated by the commodification of education. Permanence and safety must be in all classroom environments. Permanence here, would refer to the juxtaposition of belief, one where learning is subject to the temporality of ad infinitum, and other where, one's temporality of being isn't ad infinitum. 
- It creates an effect like a rubber band, where the band is always of finite length, but can be stretched in between, almost by the novelty of ideas. 
- Ongoing conversation about this: https://chat.openai.com/share/2a3c1f2d-8ce3-453b-9fb1-e156d1bcc363

### Strange Loops

^e892b8

A "strange loop" is a concept in mathematics, computer science, and philosophy, particularly associated with the work of Douglas Hofstadter. It refers to a self-referential and paradoxical situation where something recursively refers to itself in a way that creates a never-ending, often perplexing loop. This concept is often used to explore issues related to self-reference, consciousness, and perception.

One of the most famous examples of a strange loop comes from Hofstadter's book "Gödel, Escher, Bach: An Eternal Golden Braid," where he discusses the works of mathematician Kurt Gödel, artist M.C. Escher, and composer Johann Sebastian Bach. In this book, Hofstadter illustrates how these three seemingly unrelated domains contain examples of self-reference and recursion, leading to a sense of "strange loops."

A classic example from the book is Escher's drawing of two hands drawing each other, creating an infinite loop of self-reference. This visual representation exemplifies the idea of a strange loop.

The concept of strange loops is used to explore complex, interconnected systems and the way they can lead to unexpected and often paradoxical outcomes. It has also been applied in discussions about artificial intelligence, cognitive science, and the nature of consciousness, as it can help in understanding the complexity of self-awareness and self-reference in such systems.


### Quines
A quine is a specific type of "strange loop" in the context of computer programming and linguistics. It is a program or script that takes no input and produces its own source code as its output. In other words, a quine is a self-replicating program that, when run, generates a copy of its own source code.

Here's a simple example of a quine in Python:

```python
s = 's = {!r}; print(s.format(s))'; print(s.format(s))
```

When you run this Python code, it will produce the exact same code as its output. The `{!r}` inside the string formatting is used to insert the string representation of the `s` variable, which contains the source code of the program itself.

Here's how it works:

1. The variable `s` contains the source code as a string.
2. The `print(s.format(s))` statement prints the value of `s` with the placeholder `{!r}` replaced by the value of `s`.

This creates a loop where the program prints its own source code when executed, making it a quine.

Quines are often seen as intriguing and challenging programming exercises and are used to explore self-reference and the concept of strange loops in the context of computer programs. They demonstrate the ability of a program to introspect and generate its own code, leading to a kind of self-replication.

### Jean Racine:
Jean Racine (1639-1699) was a French dramatist and playwright. He is best known for his tragedies, which include works like "Phèdre," "Andromaque," and "Britannicus." Racine's plays are considered classics of French literature and are still performed and studied today.

### Commutative Diagram

A commutative diagram is a graphical representation used in category theory and various branches of mathematics, such as algebra, topology, and geometry, to illustrate the relationships and mappings between objects and morphisms (arrows) in a category. The key feature of a commutative diagram is that it indicates that a specific sequence of mappings or transformations leads to the same result, regardless of the path taken within the diagram. In other words, it expresses that certain compositions of morphisms yield the same result, which is a fundamental concept in category theory.

Here's a simple example to illustrate the idea of a commutative diagram:

Consider two sets A and B, along with two functions f: A -> B and g: A -> B. The commutative diagram representing this scenario would look like this:

```
     A
    / \
   /   \
  f     g
   \   /
    \ /
     B
```

In this diagram:

- The objects are represented by the sets A and B.
- The arrows (morphisms) f and g represent the functions from set A to set B.

The diagram is commutative in this case because it illustrates that the result of going from A to B through two different paths (f or g) yields the same result. Mathematically, this means that for any element a in set A, the following equation holds:

f(a) = g(a)

In category theory, commutative diagrams are used to study and describe various algebraic structures, relationships between objects, and transformations within categories. They help mathematicians express and visualize the principles of universal properties, functors, and other categorical concepts, making them a valuable tool for abstraction and generalization in mathematics.

### Categorical Equivalences

"Categorical equivalence" is a concept in category theory, a branch of mathematics that studies abstract structures and their relationships. In category theory, a categorical equivalence is a relationship between two categories that captures the idea that these categories are essentially the same in terms of their structure and properties, despite potentially having different objects and morphisms.

More formally, two categories, C and D, are said to be categorically equivalent if there exist functors F: C -> D and G: D -> C such that the compositions FG and GF are naturally isomorphic to the identity functors on C and D, respectively. In simpler terms, this means that you can map back and forth between the categories C and D using these functors, and the resulting mappings preserve the category structure in a way that's consistent and invertible.

When two categories are categorically equivalent, it means that you can translate statements and theorems from one category to the other while preserving the essential structure and properties of interest. This concept is particularly useful for recognizing and establishing correspondences between different mathematical structures, which can lead to insights, simplifications, and a deeper understanding of mathematical concepts.

Categorical equivalence can be a powerful tool in mathematics for showing that seemingly different mathematical objects or structures are fundamentally the same, which can simplify proofs and promote a better understanding of the relationships between various mathematical concepts. It's a fundamental concept in category theory and plays a crucial role in many areas of mathematics and theoretical computer science.

### Origins of Categorical Equivalence

The concept of categorical equivalence originates from category theory, a branch of mathematics that was developed in the mid-20th century. It's challenging to attribute the concept of categorical equivalence to a single originator because category theory itself is a collaborative endeavor that involved contributions from multiple mathematicians. However, here are some key figures and developments in the history of categorical equivalence:

1. **Samuel Eilenberg and Saunders Mac Lane:** These two mathematicians are often credited with pioneering category theory. Their work in the early 1940s laid the foundation for many of the concepts in category theory, including the notion of a category, functors, and natural transformations.

2. **Category Theory's Development:** The development of category theory was a collective effort by several mathematicians. Eilenberg and Mac Lane, along with other prominent mathematicians like J.W. Gray and Daniel Kan, made significant contributions to the development of the theory.

3. **Emergence of Categorical Equivalence:** Categorical equivalence emerged as a fundamental concept within category theory as mathematicians explored the relationships between categories and the mappings between them. It became a central idea for identifying when two categories are structurally equivalent.

4. **Category Theory's Impact:** Category theory has had a profound influence on various areas of mathematics, including algebra, topology, and mathematical logic. The idea of categorical equivalence, as well as related concepts such as functors and natural transformations, has been widely used in these fields to provide a more abstract and unifying perspective on mathematical structures.

While the specific originator of categorical equivalence is challenging to pinpoint, the development of category theory and its concepts has been a collaborative effort among many mathematicians over several decades. This theory has greatly impacted the way mathematicians think about and study mathematical structures and relationships.

### Natural Source of Logic

^cc0dc7

Logic, as a discipline, is not derived from a specific natural source in the same way that, for example, our understanding of physics is derived from observations of the natural world. Instead, logic is a product of human thought and reason. It is a formal system of principles and rules for sound reasoning and making valid inferences.

However, you can argue that the foundation for logic has its roots in human cognition and our capacity for abstract thought. Humans have developed logic as a way to structure and formalize the way we think and reason about the world. This development of logic is a result of the way our brains process information, our ability to recognize patterns, and our inclination to seek coherence and consistency in our thoughts.

In that sense, you could say that the natural source of logic is the human mind and its cognitive processes. Logic is a tool we've created to systematize and make explicit the principles of valid reasoning that underlie our thought processes. It allows us to analyze arguments, identify fallacies, and draw conclusions based on evidence and sound principles. While logic itself is a product of human intellectual development, its roots are in our natural capacity for abstract thinking and reasoning.

###  What Are Neural Networks Even Doing? (Manifold Hypothesis)
https://youtu.be/pdNYw6qwuNc
1. Weighted sum with bias is sent to a non linear function
2. Non linear function can be ReLU or Hyperbolic tangent, or even leaky non-ReLU
3. Training happens with backpropagation 
4. The transformation to tanh is very cool, taking a plane into a box
5. Last layer is a linear classifier, to make a boundary between the points, after the initial transformations
6. We can't "tear" a space. But what does it mean to actually tear a space? #toread 
7. Manifold hypothesis: High dimensional data actually exist on some hypothetical low dimensional manifold. #toread
8. 

