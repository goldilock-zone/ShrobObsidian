Recap of three rules of derivation 
[[Logic Lecture 2- Tautologies and Theories of Inference#^c7138c]]

Recap of the Criterion for Sentential Inference 
[[Logic Lecture 2- Tautologies and Theories of Inference#^b96d31]]

Note: 
1. Each step of a derivation should ideally talk about which premises it refers to. It's a nice heuristic we have to ensure that every step logically follows from the premises. 
2. Tautological implications are the primary tools for deduction
3. You can also use premises themselves (implicit implication), and conditional proofs  (if...then)
4. **Sentential Interpretation** Preserves sentence structure. We can add substructure, but it must be of the same structure.  ^b561a5
5. System of problem solving: Chain of implications with categorical equivalence
	1. The picture this evokes is that of a flower:
	   F̵̻͉͑̒̕l̴͙̪͔͛̾̈́o̸͎͎̺̿̿̓w̴̫͔͖͊͝e̸͖̞̘̾̓͑r̴̼͓͌̈́
#### Exhaustive List of Common tautologies

A tautology is a statement or formula in propositional logic that is always true, regardless of the truth values of its individual propositions. Tautologies are a fundamental concept in logic and are essential in various applications, including proof theory and computer science. Here's a list of some common tautologies:

1. **Law of Identity (Idempotent Law):** A = A
2. **Law of Excluded Middle:** A ∨ ¬A
3. **Law of Non-Contradiction:** ¬(A ∧ ¬A)
4. **Double Negation:** ¬(¬A) ↔ A
5. **De Morgan's Laws:**
   - ¬(A ∧ B) ↔ ¬A ∨ ¬B
   - ¬(A ∨ B) ↔ ¬A ∧ ¬B
6. **Commutative Laws:**
   - A ∧ B ↔ B ∧ A
   - A ∨ B ↔ B ∨ A
7. **Associative Laws:**
   - (A ∧ B) ∧ C ↔ A ∧ (B ∧ C)
   - (A ∨ B) ∨ C ↔ A ∨ (B ∨ C)
8. **Distributive Laws:**
   - A ∧ (B ∨ C) ↔ (A ∧ B) ∨ (A ∧ C)
   - A ∨ (B ∧ C) ↔ (A ∨ B) ∧ (A ∨ C)
9. **Implication and Conjunction:**
   - A → (B → A)
   - (A ∧ B) → A
10. **Implication and Disjunction:**
    - A → (A ∨ B)
11. **Contrapositive:**
    - (A → B) ↔ (¬B → ¬A)
12. **Modus Ponens:**
    - (A → B) ∧ A → B
13. **Modus Tollens:**
    - (A → B) ∧ ¬B → ¬A
14. **Hypothetical Syllogism:**
    - (A → B) ∧ (B → C) → (A → C)
15. **Tautology:**
    - A ∨ ¬A (Principle of Explosion)
    - (A → B) ∨ (B → A)
16. **Absorption Laws:**
    - A ∨ (A ∧ B) ↔ A
    - A ∧ (A ∨ B) ↔ A
17. **Redundancy Law:**
    - A ∨ A ↔ A
    - A ∧ A ↔ A
18. P ∧ (P → Q) → Q
19. Q ∧ (P → Q) → ¬P
20. P ∧ (P ∨ Q) → Q
21. P ∧ (P ∧ Q) → Q
**Contrapositive**
23.  (P → Q) ↔ (¬Q → ¬P) 
24. P ∧ Q → R ↔ P → (Q → R)
25. P → Q↔ ¬P ∨ Q

Note: Iff denotes a logical equivalence
→¬∧↔∨


These are some of the most commonly used tautologies in classical propositional logic. They are used as the basis for constructing logical arguments, proving theorems, and simplifying logical expressions. Tautologies are also a central concept in predicate logic and other branches of formal logic.

Note the Strange Loops all over math's. Algebra of logic is used to prove algebra. [[Daily Scribbles 29-10-2023#^e892b8]]
#### Conditional proofs
Conditional Proof (CP) is a proof technique used in formal logic to establish a conditional statement (an "if-then" statement) by assuming the antecedent (the "if" part) and then deriving the consequent (the "then" part) under that assumption. Conditional Proof is a useful method for demonstrating the validity of an implication. Here's how to use Conditional Proof:

**Step 1: State your goal.** Begin by identifying the conditional statement you want to prove. It typically has the form "If P, then Q," where P is the antecedent and Q is the consequent.

**Step 2: Begin the conditional proof.** Start by assuming the antecedent (P) as a temporary assumption. You'll write this assumption as a line in your proof.

**Step 3: Prove the consequent.** Under your assumption of P, use logical deductions and previously established rules to prove the consequent Q. You'll want to derive Q from your assumption of P.

**Step 4: Conclude the conditional proof.** Once you have successfully derived the consequent Q from the assumption P, you can conclude the conditional proof. Write the statement "If P, then Q" or "P → Q" and mark it as derived under the assumption.

**Step 5: Discharge the assumption.** In most formal systems of logic, you need to indicate that your assumption of P has been discharged. You do this by ending the section or line where you made the assumption.

Here's a simple example of Conditional Proof:

Goal: Prove "If A, then B."

1. Assume A (Conditional Proof)
2. [Proof steps showing how A leads to B]
3. B (Conclusion under the assumption A)
4. A → B (Conditional Proof is complete; assumption of A is discharged)

In this example, you assume A and then use logic and deductions to show that A implies B. Once you've done that, you can conclude that "If A, then B" is a valid statement.

Conditional Proof is a powerful tool for proving conditional statements in logic, and it's commonly used in formal logic and mathematical proofs.

#### Invalid Argument
If antecedent is true, then the conclusion is false

#### Vacuous Truth

I did need to think about this a little bit. Read the existential quantifier for this.  

In propositional logic, "vacuously true" statements can be represented using the logical connectives and quantifiers of the language. Here are examples in propositional logic notation:

1. **Universal Quantification:** ∀x (Fx → Px)
   - Here, ∀x represents "for all x," Fx represents "x is a flying pig," and Px represents "x is pink."
   - The statement asserts that all flying pigs are pink. Since there are no flying pigs, this statement is vacuously true.

2. **Existential Quantification:** ∃x (Cx ∧ ~Ex)
   - Here, ∃x represents "there exists an x," Cx represents "x is a square circle," and ~Ex represents "x does not exist."
   - The statement asserts that there exists a square circle, but it is also noted that such a thing doesn't exist. Therefore, the statement is vacuously true.

3. **Implication:** (G → Q) → (M → E)
   - Here, G represents "the Moon is made of green cheese," Q represents "I am the Queen of England," M represents "the Moon is made of green cheese," and E represents "I am the Queen of England."
   - The statement asserts that if the Moon is made of green cheese, then I am the Queen of England, but since the Moon is not made of green cheese, the antecedent is false, making the entire implication true (vacuously).

4. **Conjunction:** (C ∧ ~C) ∧ (I ↔ ~I)
   - Here, C represents "the car is in the garage," ~C represents "the car is not in the garage," I represents "the car is in the garage and not in the garage at the same time," and ~I represents "the car is not in the garage and in the garage at the same time."
   - The statement asserts that both parts of the conjunction are true simultaneously, but this is impossible, so the entire conjunction is vacuously true.

These examples in propositional logic demonstrate how vacuously true statements are expressed using logical notation, where the truth of the statements arises from the impossibility or non-existence of the conditions they describe.

#### Modus Ponens and Modus Tollens
**Modus Ponens** and **Modus Tollens** are two fundamental and commonly used forms of deductive reasoning in propositional logic and classical logic. They are used to draw valid conclusions from conditional statements. Here's an explanation of both:

1. **Modus Ponens (Affirming the Antecedent):**

   Modus Ponens is a valid argument form that involves two premises: a conditional statement and the affirmation of its antecedent (the "if" part). It allows you to conclude the consequent (the "then" part) of the conditional statement.

   The form of Modus Ponens is as follows:

   Premise 1: If P, then Q. (P → Q)
   Premise 2: P
   Conclusion: Therefore, Q.

   In Modus Ponens, if you have a conditional statement and you know that the antecedent (P) is true, you can validly infer that the consequent (Q) is true.

   Example:
   Premise 1: If it rains, the ground will be wet. (R → W)
   Premise 2: It is raining. (R)
   Conclusion: Therefore, the ground is wet. (W)

2. **Modus Tollens (Denying the Consequent):**

   Modus Tollens is another valid argument form involving two premises: a conditional statement and the denial of the consequent (the "then" part). It allows you to conclude the denial of the antecedent (the "if" part) of the conditional statement.

   The form of Modus Tollens is as follows:

   Premise 1: If P, then Q. (P → Q)
   Premise 2: ¬Q (not Q)
   Conclusion: Therefore, ¬P (not P).

   In Modus Tollens, if you have a conditional statement and you know that the consequent (Q) is false, you can validly infer that the antecedent (P) is false.

   Example:
   Premise 1: If it rains, the ground will be wet. (R → W)
   Premise 2: The ground is not wet. (¬W)
   Conclusion: Therefore, it is not raining. (¬R)

Both Modus Ponens and Modus Tollens are essential tools in logical reasoning and argumentation. They are frequently used in various fields, including mathematics, philosophy, and computer science, to make valid deductions from conditional statements.

#### Consistency
1. A set of premises is consistent provided that they could all together be true. Otherwise, they are inconsistent. 
2. Logic says that if the premises are true, then the conclusions are true
3. Criterion 1 says we can only derive true conclusions from true premises. Then if we can derive a false conclusion, our premises can't all be true.
4. The test would be to check for all conjunctions of the premises, and check for falsehood
5. To check for the consistency of premises using propositional logic notation, you can follow these steps:

	1. **Identify the Premises:** List your premises using propositional variables (letters or symbols) to represent statements or propositions. For example, you can use A, B, C, and so on to represent different statements.
	
	2. **Check for Explicit Contradictions:** Look for pairs of premises that are direct contradictions. In propositional logic, a contradiction is represented by the logical equivalence of a proposition and its negation (i.e., P and ¬P). If you find such pairs, your premises are inconsistent.
	
	   Example:
	   - Premise 1: A
	   - Premise 2: ¬A
	
	   Here, Premise 1 and Premise 2 are contradictory, leading to inconsistency.
	
	3. **Check for Implicit Contradictions:** Examine the premises to see if combining them would lead to a contradiction. For example, if you have premises that, when combined, result in a known logical contradiction (such as "A ∧ ¬A"), your premises are inconsistent.
	
	   Example:
	   - Premise 1: A → B
	   - Premise 2: ¬B
	
	   When you combine these premises, it leads to "A → B ∧ ¬B," which is inconsistent.
	
	4. **Use Truth Tables:** If the premises involve complex logical relationships, you can create a truth table to evaluate all possible combinations of truth values for the premises. If there is any row in the truth table where all premises are true, the premises are consistent. If no such row exists, the premises are inconsistent.
	
	   Example:
	   - Premise 1: A ∧ B
	   - Premise 2: ¬A ∨ C
	
	   Create a truth table to evaluate all possible combinations of A, B, and C. If you find a row where both premises are true, the premises are consistent.
	
	5. **Consider the Context:** In propositional logic, consistency depends on the logical relationships between the premises. Ensure that you are using consistent interpretations for your propositional variables and logical connectives.
	
	It's important to remember that consistency in propositional logic is determined by whether the premises can all be true at the same time without leading to a logical contradiction. If they can, the premises are consistent; if not, they are inconsistent.
6. Inconsistent premises just means that we can't reason about them together


#### Law of Absurdity
The "Law of Absurdity" is not a well-known or established principle in formal logic or philosophy. However, in certain contexts, the term "absurdity" may be used informally to describe a situation or argument that is so logically flawed or contradictory that it is considered unreasonable or meaningless.

In logic and philosophy, the principle of non-contradiction is a fundamental law, stating that contradictory propositions cannot both be true in the same sense at the same time. This principle is often expressed as "A is not non-A" or "Not both A and non-A." In other words, a statement and its negation cannot both be true simultaneously.

If you have a specific context or application in which you've encountered the term "Law of Absurdity," please provide more details, and I can offer a more precise explanation.

#### Reductio Ad Absurdum - Indirect Proofs
"Reductio ad absurdum" is a Latin term that translates to "reduction to absurdity." It is a method of argumentation and a proof technique used in logic and mathematics to demonstrate the falsity or absurdity of a statement or assumption by showing that it leads to a contradiction with known or accepted truths. The process involves assuming the opposite of what you want to prove (the negation of the statement) and then showing that this assumption leads to a logical inconsistency.

The general steps in a reductio ad absurdum argument are as follows:

1. **Assume the Opposite:** Begin by assuming the opposite (negation) of the statement you want to prove. This assumption is often referred to as the "reductio hypothesis."

2. **Derive a Contradiction:** Use valid reasoning and logical deduction to derive a contradiction or absurdity from the reductio hypothesis. This might involve showing that the assumption contradicts well-established facts, principles, or logical laws.

3. **Conclude the Original Statement:** Once you have shown that the reductio hypothesis leads to an absurdity, you can conclude that the original statement you wanted to prove must be true. This is because if the opposite leads to a contradiction, the original statement must be the correct position.

Here's an example of reductio ad absurdum:

Statement to Prove: "The square root of 2 is an irrational number."

1. **Assume the Opposite:** Assume that the square root of 2 is a rational number.

2. **Derive a Contradiction:** By assuming that √2 is a rational number, you can represent it as a fraction (a/b) where a and b are integers with no common factors. This would mean that 2 = (a^2)/(b^2), but this leads to a contradiction because 2 cannot be expressed as the ratio of two integers with no common factors. This is inconsistent with the assumption of √2 being rational.

3. **Conclude the Original Statement:** Since the assumption that √2 is rational leads to a contradiction, you can conclude that the original statement, "The square root of 2 is an irrational number," is true.

Reductio ad absurdum is a powerful proof technique because it demonstrates the validity of a statement by showing that its opposite leads to a logical inconsistency. It is widely used in mathematics, philosophy, and formal logic to establish the truth of various propositions and to refute arguments based on false premises.

Note: A contradiction actually means that we are adding the opposite of the conclusion ***as a premise***

#### 
####

####

####
#### Takeaway:
The abstract structure of the proof that we see in logic MUST be used in any future math's that I do. That's non trivial in the structure of my mathematical conclusions.