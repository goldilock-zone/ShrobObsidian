#### Truth Functional Sentential Connectives
1. Precedence of logical operatives: not, and, or
2. We can use these to form tautologies: sentences which are always true
#### Atomic sentences

^3ae539

1. Lowest units of logic. They themselves are tautologies
2. Eg. "The Sky is blue"

#### Truth Tables
1. Combinatorics of logical connectives and atomic sentences
2. We can demonstrate the "tautological-ness" of a tautology using a truth table
3. Is there a more elegant way of showing that a tautology is a tautology? #toread
4. Tautologies are tautologies if they are true *in all occurrences* 
5. Truth tables will eventually become very tedious. Well obviously. The number of rows increases as 2^n

#### Tautology
1. Sentence that is always true
2. You can replace a statement with a more complex statement to make it a tautology
3. Factor logics?
4. The infinite branching tree that we can create in logics
5. Tautological Implication: Tautology with an implies in it
6. Tautologically equivalent: I can see equivalences at the heart of mathematics. This is similar to equivalence classes in categorical equivalences. [[2 Daily Scribbles 29-10-2023#^e347f7]] 
7. 

#### Sentential Theory of Inference
1. **Main Criterion**: ^b96d31
	1. Criterion 1: Conclusions logically follow from the premises, and nothing else
	2. Criterion 2: If a set of premises  (or rule of logic) gives us a false statement, we reject it
2. a implies a, is invalid rule of logic, because it violates criterion 2.
3. A rule of logic is a fundamental principle or guideline that governs the structure and validity of arguments and reasoning. Logic is the study of valid reasoning, and these rules help ensure that conclusions drawn from premises are sound and free from fallacies. Some common rules of logic include:

	1. Law of Non-Contradiction: This law states that contradictory statements cannot both be true in the same sense and at the same time. In other words, a statement and its negation cannot both be true simultaneously.
	
	2. Law of Excluded Middle: This law asserts that for any statement, it must either be true or false; there is no middle ground or third option. (Except in ternary logic system) Ternary logic: [[Multivalued Logic]]
	
	3. Modus Ponens: If you have a conditional statement "If A, then B," and you know that "A" is true, you can logically conclude that "B" is also true.
	
	4. Modus Tollens: If you have a conditional statement "If A, then B," and you know that "B" is false, you can logically conclude that "A" is false.
	
	5. Syllogism: Syllogisms are logical arguments with two premises and a conclusion. A classic example is "All men are mortal. Socrates is a man. Therefore, Socrates is mortal." Triangular logic.
	
	6. Law of Identity: This law states that a thing is what it is; a statement is true if it asserts what is true and false if it asserts what is false.
	
	7. Law of Contraposition: If you have a conditional statement "If A, then B," the contrapositive statement is "If not B, then not A." This is logically equivalent to the original statement.
	
	8. Law of Transitivity: If A is related to B, and B is related to C, then A is related to C. This is often used in syllogistic reasoning.
	
	9. Principle of Induction: This principle is used to reason from a set of specific observations or cases to a general conclusion. Induction is commonly used in scientific and everyday reasoning.
	
	10. Principle of Abduction: Abduction is used to infer the best or most likely explanation for a set of observations or evidence. It is a common form of reasoning in detective work and scientific hypothesis generation.

These are just a few examples of the many rules and principles of logic. Logic provides a framework for evaluating arguments, drawing valid conclusions, and ensuring that reasoning is based on sound principles.
4. The concept of "logically follows" at the heart of mathematical reasoning
5. Sentential Interpretation: A sentence P is a sentential interpretation of Q if Q can be obtained by a string of "logically follows" from P. Q
6. Important thing to note about sentential interpretation: [[Logic Lecture 3 - Common Tautologies and Indirect Proofs#^b561a5]]

#### Three rules of sentential derivation

^c7138c

	1. We may introduce a premise at a point in our derivation
	2. We may introduce S in a derivation if it is tautologically implied by the conjunction of preceding sentences in our derivation
	3. If we can derive S from R and a set of premises, then we can derive R->S from the premises above. This is sort of like vector addition.
1. Deduce a conclusion, through going through the premises logically. Emphasize on _deduce_. '
2. Any sentence can be dissolved into atomic sentences, and sentential connectives, and deducing conclusions can be made using **valid rules of logic**.
3. Logically following, at each stage of a proof can be tracked using a graph (tree). It's funny that a proof of graph theory can be proved by a theory of logic that inherently is a graph. Strange Loop indeed. [[2 Daily Scribbles 29-10-2023#^e892b8]]
4. Every premise depends on itself for its validity

#### Non Truth Functional Connective
A "non-truth functional connective" (also known as a "non-truth-functional operator" or "non-truth-functional connective") is a logical connective that doesn't operate solely on the truth values (true or false) of the propositions it connects. In contrast, truth-functional connectives, like "and" (conjunction), "or" (disjunction), "not" (negation), etc., combine truth values in a way that depends only on the truth values of the component propositions. Non-truth functional connectives, on the other hand, introduce a level of complexity beyond simple truth values.

Some common examples of non-truth functional connectives include:

1. **Material Conditional (If-Then):** In natural language, "if-then" doesn't always correspond to the material conditional in formal logic. The material conditional is defined as true in all cases except when the antecedent (the "if" part) is true, and the consequent (the "then" part) is false. This is not necessarily how "if-then" is used in everyday language.

2. **Biconditional (If and Only If):** The biconditional operator, ↔, is not always equivalent to "if and only if" in natural language. In logic, it's only true when both sides have the same truth value.

3. **Necessity and Possibility (Modal Logic):** In modal logic, operators like "necessarily" (□) and "possibly" (◇) are non-truth functional. They deal with the necessity and possibility of propositions and don't have a simple truth table.

4. **Quantifiers (Existential (∃) and Universal (∀)):** Quantifiers in first-order logic, such as "there exists" (∃) and "for all" (∀), are non-truth functional. They indicate the scope and quantification of variables in logical statements.

Non-truth functional connectives are often used in more advanced branches of logic and philosophy, such as modal logic, epistemic logic, and deontic logic, where the relationships between propositions and their truth values become more complex. These connectives introduce nuances that go beyond simple true or false evaluations.

#### Contrapositive
Original Statement: If P, then Q.
Contrapositive: If not Q, then not P.

In other words, the contrapositive statement is formed by negating both the consequent (Q) and the antecedent (P) of the original conditional statement and switching their positions.

The contrapositive has the same truth value as the original statement. If the original statement is true, its contrapositive is also true, and if the original statement is false, the contrapositive is also false. This property is useful in logical proofs and arguments because it provides an equivalent statement that can sometimes be easier to work with or analyze.

For example, consider the original statement "If it is raining (P), then the ground is wet (Q)." The contrapositive of this statement is "If the ground is not wet (not Q), then it is not raining (not P)."

The contrapositive can be helpful in various mathematical and logical contexts, including proof by contradiction and implications in deductive reasoning.

### NAND
NAND is a logical operator that stands for "NOT-AND." It is one of the basic logic gates used in digital electronics and computer science. The NAND gate performs the logical operation of negating the conjunction (AND) of two propositions. In other words, it produces the opposite result of an AND gate. 

Here's the truth table for the NAND operator:

| A | B | A NAND B |
|---|---|---------|
| 0 | 0 |   1     |
| 0 | 1 |   1     |
| 1 | 0 |   1     |
| 1 | 1 |   0     |

The output (A NAND B) is true (1) only when both inputs (A and B) are not both true (0 and 1 or 1 and 0). In all other cases, the output is false (1 or 0).

NAND gates are considered universal gates in digital logic, which means that you can use them to implement any other type of logical operation, including NOT, OR, AND, and more. This property makes them fundamental in the design of digital circuits and computers. They are often used as building blocks for more complex logic functions and are widely used in modern electronics and computer architecture.
#### 

#### Note: Ongoing conversation: 
https://chat.openai.com/share/25db5eff-0853-461a-a0c5-25ac87295b96