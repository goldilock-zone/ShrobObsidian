
Functional programming often encourages the use of recursion as an alternative to traditional loops for iterating over data structures. Here's a simple example in both imperative (loop-based) and functional (recursive) styles in Python to demonstrate this difference:

**Imperative (Loop-Based) Example:**
```python
# Sum of numbers from 1 to N using a loop
def sum_with_loop(n):
    result = 0
    for i in range(1, n + 1):
        result += i
    return result

print(sum_with_loop(5))  # Output: 15
```

In the above code, we use a `for` loop to iterate from 1 to `n`, accumulating the sum of numbers.

**Functional (Recursive) Example:**
```python
# Sum of numbers from 1 to N using recursion
def sum_with_recursion(n):
    if n == 1:
        return 1
    else:
        return n + sum_with_recursion(n - 1)

print(sum_with_recursion(5))  # Output: 15
```

In the functional example, we define a recursive function `sum_with_recursion`. Instead of using a loop, we express the sum in terms of the problem's mathematical recurrence relation: "the sum of numbers from 1 to N is equal to N plus the sum of numbers from 1 to N-1." This recursive approach breaks the problem into smaller subproblems until it reaches the base case (in this case, `n == 1`) and then combines the results to calculate the final sum.

Functional programming languages and paradigms often encourage recursive solutions like this, as they can be more concise and expressive for certain types of problems. However, it's important to note that recursion can lead to stack overflow errors for very large values of `n`, and some functional languages provide optimizations (like tail recursion optimization) to mitigate this issue.

## Demonstration in Haskell

```haskell
-- Sum of numbers from 1 to N using recursion in Haskell
sumWithRecursion :: Int -> Int
sumWithRecursion 1 = 1
sumWithRecursion n = n + sumWithRecursion (n - 1)

main :: IO ()
main = do
  putStrLn $ "Sum of numbers from 1 to 5: " ++ show (sumWithRecursion 5)
```

In Haskell, we define a function `sumWithRecursion` with a type declaration that specifies it takes an integer and returns an integer. The function is defined using pattern matching:

- When `n` is 1, the result is 1 (the base case).
- For other values of `n`, it recursively calls itself with `n - 1` and adds `n` to the result.

In the `main` function, we print the result of `sumWithRecursion` for `n = 5`. When you run this Haskell program, it will output:

```
Sum of numbers from 1 to 5: 15
```

This demonstrates how Haskell, a functional programming language, uses recursion to solve the problem of summing numbers in a declarative and mathematical way.

