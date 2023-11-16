-  Convincing someone of a proof, without revealing any information about it
- Used for Private data stuff. An encoding based verification.
- There's usually a single solution to a ZKP
- Set up phase happens at the same time. 
- Proving phase.
- Show that your solution contains the right elements in the right position as that of the initial question
- Verification, do the algorithm, shuffle, and check for invariant. Check for validity of solution, rather than finding the solution
- The above proof depends on the acceptance of the fact that ZKP's have a unique solution
- SNARK: Succinct Non Interactive Argument of Knoweldge
	- Succinct: Small and tractable
	- Non Interactive: Each party doesn't really need to talk to each other
	- Argument: Relaxing what we really mean by a proof. Both parties have to accept the axioms. Check to High Probability, instead of perfectness. This is called soundness. 
	- Knowledge: The statement that is being proven shows not just the proof but the knowledge of the proof. 
Steps of SNARK:
	- Arithmetization: Encoding the statement in artithmeic of any kind. We can build an arithmetic circuit out of this. #toread 
	- Commitment scheme: Making some steps of the puzzle public. Without exposing too much.
	- Interactive Oracle Proof: Each side asks the other questions, until the other side is satisfied that the original user obeys the rules. Sudoku is not interactive though.
	- Exhaustive checks sometimes are not required, we just need to reduce probability of error
	- Fiat Shamir Transformation: Random number generator, such that commitments aren't overfit

- Schawrtz - Zippel Lemma: 
	The Schwartz-Zippel Lemma provides a probabilistic method for testing if a polynomial is identically zero. Here's the rigorous statement of the lemma:

	**Lemma (Schwartz-Zippel)**: Let \( P(x_1, x_2, \ldots, x_n) \) be a non-zero polynomial of degree \( d \) over a field \( F \). Suppose each variable \( x_i \) is independently set to a value chosen uniformly at random from a finite subset \( S \subseteq F \). Then the probability that \( P \) evaluates to zero is at most \( \frac{d}{|S|} \), where \( |S| \) is the size of set \( S \).
	
	In simpler terms, if you have a non-zero polynomial of degree \( d \), and you randomly choose values for its variables from a set with \( |S| \) elements, the probability that the polynomial evaluates to zero is no more than \( \frac{d}{|S|} \).
	
	**Corollaries and Applications**:
	
	1. **Polynomial Identity Testing**: One immediate application is in polynomial identity testing. Given two polynomials \( P \) and \( Q \), to check if they are identical, it suffices to check if \( P - Q \) is the zero polynomial. Using the Schwartz-Zippel Lemma, this can be done by evaluating \( P - Q \) at a random point and checking if it equals zero, which is a much more efficient process than comparing coefficients.
	
	2. **Algorithmic Complexity Reduction**: In algorithms, especially in randomized algorithms, the Schwartz-Zippel Lemma is used to reduce the complexity of problems that can be reduced to polynomial identity testing. This has applications in computational geometry, graph theory, and other areas of computer science.
	
	3. **Non-zero Determinant Verification**: For matrices with polynomial entries, the Schwartz-Zippel Lemma can be used to efficiently verify if the determinant is non-zero. This is particularly useful in computational linear algebra.
	
	4. **Graph Property Testing**: In graph theory, the lemma is used in property testing algorithms. For example, it can be used to test if a graph has a certain property (like being Hamiltonian) by encoding the property into a polynomial and then applying the lemma.
	
	These corollaries highlight the lemma's importance in various computational and algorithmic contexts, offering efficient solutions to problems that would otherwise require more computationally intensive approaches.

- Trusted set up: S is used to encrypt and then deleted
- Additively homomorphic encryption keys
- "Special Multiplication"
- Pairing Functions in Elliptic Curves


# GPT Notes
Delving deeper into each topic requires exploring the mathematical and cryptographic intricacies underlying these concepts. Let's break down each area further:

### 1. Zero-Knowledge Proofs (ZKPs)

- **Principles**: ZKPs are based on complex mathematical constructs that allow a prover to demonstrate knowledge of a secret without revealing the secret itself. This is achieved through interactive protocols where the prover sends 'proofs' to the verifier, who checks these proofs for validity. 

- **Types of ZKPs**:
  - **Interactive ZKPs**: Require multiple rounds of interaction between prover and verifier.
  - **Non-Interactive ZKPs**: Require no interaction after the initial setup phase.

- **Applications**: ZKPs are widely used in secure voting systems, authentication processes, and blockchain technologies, ensuring privacy and security without compromising on verification.

### 2. SNARK (Succinct Non-Interactive Argument of Knowledge)

- **Arithmetization**: This step involves converting a computation into a polynomial equation. For instance, a computational problem can be represented as an arithmetic circuit, which is then expressed as a polynomial equation.

- **Commitment Schemes**: These are cryptographic protocols that allow one to commit to a chosen value (or chosen statement) while keeping it hidden to others, with the ability to reveal the committed value later.

- **Interactive Oracle Proofs**: These proofs are part of the original construction of SNARKs, where the prover and verifier engage in a Q&A session. The Fiat-Shamir heuristic is used to convert this interactive proof into a non-interactive one.

- **Fiat-Shamir Transformation**: This technique is used to convert an interactive proof system into a non-interactive one by replacing the verifier's challenges with values generated by a hash function, essentially using "randomness" from a predetermined hash function.

### 3. Schwartz-Zippel Lemma

- **Mathematical Foundation**: The lemma is based on the principle that a polynomial of degree \( d \) over a finite field \( F \) can have at most \( d \) roots unless it is the zero polynomial. Thus, when evaluating the polynomial at random points in the field, the chances of hitting a root by accident (if the polynomial is non-zero) are limited by the degree of the polynomial.

- **Complexity Analysis**: The significance of the lemma in algorithm design lies in its ability to reduce the complexity of problems that can be expressed in terms of polynomial equations.

### 4. Cryptographic Concepts

- **Trusted Setup in Cryptography**: This is a critical phase in some cryptographic protocols, especially in ZKPs like zk-SNARKs. The setup phase generates public parameters for the cryptographic scheme. However, if the setup is compromised (e.g., the secret used in the setup is leaked), the entire system's security can be jeopardized.

- **Homomorphic Encryption**: This allows computations to be carried out on ciphertexts, generating an encrypted result that, when decrypted, matches the result of operations performed on the plaintexts. This is pivotal in secure data analysis and secure voting systems.

- **Elliptic Curve Pairings**: These are mathematical operations on points of elliptic curves used in cryptography. They are fundamental in constructing protocols that require complex interactions between different cryptographic elements, such as in certain advanced ZKP systems.

- **Special Multiplication and Pairing Functions**: In the context of elliptic curve cryptography, 'special multiplication' could refer to operations like the elliptic curve point multiplication, which is the basis of elliptic curve cryptography. Pairing functions are used to link elements of different elliptic curves, enabling advanced cryptographic constructs.

Each of these areas is a significant field of study in its own right, combining elements of number theory, algebra, and computational complexity. They are essential to the current state and future development of secure digital communications, privacy-preserving computation, and cryptographic currency systems like those used in blockchain technologies.
