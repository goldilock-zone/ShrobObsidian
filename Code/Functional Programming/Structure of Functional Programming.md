While recursion is a significant and common technique in functional programming, it would be an oversimplification to say that "all of functional programming is just recursion." Functional programming is a programming paradigm that encompasses a broader set of principles and techniques, of which recursion is one important aspect.

Here are some key principles and techniques in functional programming:

1. **First-Class and Higher-Order Functions:** Functional programming languages treat functions as first-class citizens, which means they can be assigned to variables, passed as arguments to other functions, and returned as results from functions. This enables higher-order functions, which are functions that take other functions as arguments or return them as results. Higher-order functions are a powerful tool in functional programming for abstraction and composition.

2. **Immutability:** Functional programming encourages the use of immutable data structures and values. Once a data structure or value is created, it cannot be modified; instead, new values are created through transformations. Immutability helps in reasoning about code and avoiding unexpected side effects.

3. **Pure Functions:** Functional programming emphasizes the use of pure functions. A pure function is a function that, given the same input, always produces the same output and has no side effects. Pure functions make code more predictable and testable.

4. **Recursion:** Recursion is a natural fit for functional programming due to its emphasis on functions and immutability. Recursive functions are often used to process data structures like lists, trees, and graphs. Tail recursion is a specific form of recursion that functional programming languages often optimize to avoid stack overflow errors.

5. **Pattern Matching:** Many functional programming languages provide pattern matching, which is a powerful way to destructure and match data structures and make decisions based on their shape.

6. **Lambdas and Closures:** Functional programming languages often support anonymous functions (lambdas) and closures, which enable concise and expressive code.

7. **Referential Transparency:** Referential transparency means that an expression can be replaced with its value without changing the program's behavior. This property is closely related to the use of pure functions.

8. **Lazy Evaluation:** Some functional programming languages support lazy evaluation, where expressions are not evaluated until their values are actually needed. This can lead to more efficient and concise code.

Functional programming is a versatile paradigm that encourages these principles and techniques to varying degrees. Not all functional programs are purely recursive; they may also use a combination of these principles to achieve their goals. Functional programming languages provide a toolbox of features and patterns for developers to use as needed, depending on the specific problem they are trying to solve.

# Lambdas and Closures
Lambdas and closures are important concepts in programming, particularly in functional programming and languages that support functional programming features. They both deal with anonymous functions, but they have distinct characteristics and use cases.

**Lambda Expressions:**

1. **Definition:** A lambda expression, also known as a lambda function or anonymous function, is a nameless, inline function that can be defined and used at the point where it's needed without the need for a separate function declaration.

2. **Syntax:** Lambda expressions are typically written in a compact syntax. In many programming languages, a lambda starts with the keyword `lambda` or `fun`, followed by a list of parameters, an arrow (=> or `->`), and an expression or block of code.

3. **Use Cases:** Lambdas are often used for short, simple operations that can be passed as arguments to higher-order functions or used in situations where a full function declaration would be cumbersome or unnecessary. They are especially useful for tasks like filtering, mapping, and reducing data.

4. **Example (Python):**
   ```python
   # Lambda expression to double a number
   double = lambda x: x * 2
   print(double(5))  # Output: 10
   ```

**Closures:**

1. **Definition:** A closure is a function that "closes over" its lexical scope, meaning it retains access to the variables and parameters of the outer (enclosing) function even after the outer function has finished executing.

2. **Characteristics:** Closures capture the environment in which they were created, including all the variables that were in scope at that time. This allows closures to maintain state between invocations.

3. **Use Cases:** Closures are particularly useful for creating functions with persistent state. They can be used to encapsulate data and behavior, creating objects or modules in a more functional style.

4. **Example (JavaScript):**
   ```javascript
   function createCounter() {
     let count = 0;
     return function () {
       return ++count;
     };
   }

   const counter = createCounter();
   console.log(counter());  // Output: 1
   console.log(counter());  // Output: 2
   ```

In this JavaScript example, `createCounter` returns a closure, which is an inner function that maintains access to the `count` variable even after `createCounter` has completed execution. Each time the closure is called, it increments the `count` variable.

To summarize, lambdas are anonymous functions often used for short, one-off operations, while closures are functions that "remember" their surrounding context, allowing them to maintain state and capture variables from their enclosing scope. Both lambdas and closures are valuable tools in functional programming and modern programming languages for creating more concise and expressive code.