[[Programming Paradigms]]
# Example of Better Abstraction:
Functional programming is often considered better at abstraction because it emphasizes the use of pure functions, immutability, and higher-order functions. These concepts enable you to create more abstract and reusable code. Let's illustrate this with pseudocode and a mathematical example:

**Pseudocode Example:**

Suppose we want to calculate the sum of squares of even numbers from a list of integers.

**Imperative (Non-functional) Approach:**

```python
# Imperative pseudocode
function sumOfSquaresOfEvenNumbers(numbers):
    result = 0
    for num in numbers:
        if num % 2 == 0:
            result += num * num
    return result
```

In this imperative approach, we explicitly loop through the list of numbers, check for evenness, and accumulate the square of even numbers. It's not very abstract and involves low-level details.

**Functional Approach:**

```python
# Functional pseudocode
function isEven(n):
    return n % 2 == 0

function square(n):
    return n * n

function sumOfSquaresOfEvenNumbers(numbers):
    evenNumbers = filter(isEven, numbers)
    squaredNumbers = map(square, evenNumbers)
    return reduce(add, squaredNumbers, 0)
```

In the functional approach, we define reusable functions `isEven` and `square`. We then use higher-order functions like `filter`, `map`, and `reduce` to abstract away the details of iteration, filtering, and accumulation. This code is more abstract and declarative, making it easier to understand and reuse.

**Mathematical Example:**

Let's consider a mathematical example using a functional approach.

Suppose we want to find the sum of squares of the first `n` positive even integers using a mathematical formula.

**Imperative (Non-functional) Approach:**

```python
# Imperative pseudocode
function sumOfSquaresOfFirstNEvenNumbers(n):
    result = 0
    count = 0
    num = 2
    while count < n:
        result += num * num
        num += 2
        count += 1
    return result
```

In this imperative approach, we use a loop with mutable variables, making it less abstract and harder to reason about.

**Functional Approach:**

```python
# Functional pseudocode
function square(n):
    return n * n

function sumOfSquaresOfFirstNEvenNumbers(n):
    evenNumbers = map(lambda x: 2 * x, range(n))
    squaredNumbers = map(square, evenNumbers)
    return reduce(add, squaredNumbers, 0)
```

In the functional approach, we use mathematical concepts to generate the first `n` positive even numbers and then use higher-order functions to calculate the sum of their squares. This code is more abstract and mathematical, making it easier to see the underlying pattern and generalize it to other situations.

Functional programming encourages you to think in terms of functions, transformations, and mathematical abstractions, which can lead to more elegant and reusable code.

# More involved examples
Certainly, let's explore a more complicated example involving functional programming and abstraction. We'll use a common example involving a list of people and various data manipulations. In this example, we'll pseudocode and use mathematical functions to find the average age of all adults in a list of people.

**Pseudocode Example:**

Suppose we have a list of people, where each person is represented as a dictionary with attributes like name, age, and whether they are adults.

**Imperative (Non-functional) Approach:**

```python
# Imperative pseudocode
function calculateAverageAgeOfAdults(people):
    totalAge = 0
    adultCount = 0
    for person in people:
        if person["isAdult"]:
            totalAge += person["age"]
            adultCount += 1
    if adultCount > 0:
        averageAge = totalAge / adultCount
    else:
        averageAge = 0
    return averageAge
```

In this imperative approach, we use a loop to iterate through the list of people, maintain a total age and count of adults, and calculate the average age. This approach is not very abstract and involves low-level details.

**Functional Approach:**

```python
# Functional pseudocode
function isAdult(person):
    return person["isAdult"]

function getAge(person):
    return person["age"]

function calculateAverageAgeOfAdults(people):
    adults = filter(isAdult, people)
    adultAges = map(getAge, adults)
    
    if length(adultAges) > 0:
        totalAge = reduce(add, adultAges, 0)
        averageAge = totalAge / length(adultAges)
    else:
        averageAge = 0
    
    return averageAge
```

In the functional approach, we define reusable functions `isAdult` and `getAge` for filtering and extracting age. We then use higher-order functions like `filter`, `map`, and `reduce` to abstract away the details of iteration, filtering, and calculation. This code is more abstract and declarative, making it easier to understand and reuse. It also separates concerns, making the code more modular and maintainable.

**Mathematical Example:**

Let's consider a mathematical example to find the average age of adults.

```python
# Mathematical pseudocode
function calculateAverageAgeOfAdults(people):
    adultAges = map(getAge, filter(isAdult, people))
    
    if length(adultAges) > 0:
        totalAge = reduce(add, adultAges, 0)
        averageAge = totalAge / length(adultAges)
    else:
        averageAge = 0
    
    return averageAge
```

In this mathematical pseudocode, we directly express the computation in terms of mathematical functions like `map`, `filter`, `reduce`, and division. This makes the code more abstract and emphasizes the functional aspects, making it easier to reason about and generalize to other similar problems.

Functional programming's emphasis on abstraction, modularity, and mathematical operations allows for more complex problems to be expressed in a clear and concise manner, promoting code readability and maintainability.

# Map, Reduce and Filter
`filter`, `map`, and `reduce` are fundamental higher-order functions commonly used in functional programming. They allow you to work with collections (e.g., lists or arrays) in a more functional and declarative way. Here's what each of them does:

1. **`filter`**:
   - `filter` is used to select elements from a collection (e.g., a list) that satisfy a given condition.
   - It takes two arguments: a predicate function and a collection.
   - The predicate function is applied to each element in the collection, and only the elements for which the predicate returns `true` are included in the resulting filtered collection.
   - The original collection remains unchanged.

   Example in Python:
   ```python
   # Filter even numbers from a list
   numbers = [1, 2, 3, 4, 5, 6]
   even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
   # Result: [2, 4, 6]
   ```

2. **`map`**:
   - `map` is used to transform each element of a collection using a given function.
   - It takes two arguments: a transformation function and a collection.
   - The transformation function is applied to each element in the collection, and the results are collected into a new collection of the same size as the original.
   - The original collection remains unchanged.

   Example in Python:
   ```python
   # Square each number in a list
   numbers = [1, 2, 3, 4, 5]
   squared_numbers = list(map(lambda x: x * x, numbers))
   # Result: [1, 4, 9, 16, 25]
   ```

3. **`reduce`**:
   - `reduce` is used to accumulate or combine the elements of a collection into a single value.
   - It takes two arguments: an accumulation function and a collection.
   - The accumulation function is applied successively to pairs of elements from the collection, starting from the left, and the result of each step is used as one of the inputs to the next step.
   - The final result is a single value that represents the accumulation of all elements in the collection.

   Example in Python (calculating the sum of a list of numbers):
   ```python
   from functools import reduce

   numbers = [1, 2, 3, 4, 5]
   total = reduce(lambda x, y: x + y, numbers)
   # Result: 15
   ```

These higher-order functions make it easier to write concise and readable code, especially when dealing with collections and data transformations. They promote a more functional and declarative style of programming, which can lead to code that is easier to understand and reason about.

# Fold
In functional programming, the `fold` (also known as `reduce` in some languages) operation is used to accumulate values in a collection into a single result by applying a specified function iteratively. It's a fundamental concept and is often used to perform operations like summing elements, finding the maximum value, or concatenating strings within a collection. Here's pseudocode demonstrating how `fold` works:

```python
function fold(collection, initialAccumulator, accumulatorFunction):
    accumulator = initialAccumulator
    for element in collection:
        accumulator = accumulatorFunction(accumulator, element)
    return accumulator
```

In the above pseudocode:
- `collection` represents the input collection (e.g., a list or array) over which we want to perform the fold operation.
- `initialAccumulator` is the initial value of the accumulator, which is used as the starting point for the accumulation process.
- `accumulatorFunction` is a binary function (a function that takes two arguments) that defines how the accumulator should be updated at each step. It combines the current accumulator value with an element from the collection.

Here's an example of how you might use `fold` to calculate the sum of elements in a list of numbers:

```python
function sum(numbers):
    accumulatorFunction = function(accumulator, element):
        return accumulator + element

    result = fold(numbers, 0, accumulatorFunction)
    return result
```

In this example:
- `numbers` is a list of numbers.
- `accumulatorFunction` is a function that adds the current accumulator value to the current element.
- `fold` is called with the list of numbers, an initial accumulator value of `0`, and the accumulator function.
- The `fold` operation iterates through the list of numbers, applying the accumulator function at each step to calculate the sum.
- The final result is returned as the sum of the numbers.

You can adapt the `fold` operation and the accumulator function to perform various other operations like finding the maximum element, concatenating strings, or performing custom aggregations on a collection in a functional and declarative way.

