- The idea of linear approximations
- Can we approximate a diffy eqns, using the ideas we had in single variable calculus
- Readjustment, based on hitting some threshold wrt the error allowed. 
![[Pasted image 20231116121750.png]]

- We can use a certain step size, to get better approximants
- A sequence of linear approximations
- A robot is an analogue to the "head" of an automata


Euler's Method is a fundamental numerical technique used to approximate solutions of ordinary differential equations (ODEs). It is particularly useful when an analytic solution is difficult or impossible to find. Let's delve into the method before illustrating it with an example.

### The Method

Given a first-order differential equation of the form:

$$
\frac{dy}{dx} = f(x, y), \quad y(x_0) = y_0
$$

where \( y_0 \) is the initial condition at \( x_0 \), Euler's Method provides a means to approximate \( y \) at subsequent points.

The method works by using the slope of the tangent line at known points to estimate the value of \( y \) at the next point. Mathematically, it's expressed as:

$$
y_{n+1} = y_n + f(x_n, y_n) \cdot \Delta x
$$

where \( \Delta x \) is a small step size and \( n \) indexes the iteration.

### Example

Let's consider the differential equation:

$$
\frac{dy}{dx} = x + y, \quad y(0) = 1
$$

We want to approximate \( y \) at \( x = 0.1 \) using Euler's Method with a step size \( \Delta x = 0.1 \).

#### Step-by-Step Procedure:

1. **Initial Condition:** \( x_0 = 0, y_0 = 1 \).
2. **Function:** \( f(x, y) = x + y \).
3. **First Iteration:**
   - Calculate \( y_1 = y_0 + f(x_0, y_0) \cdot \Delta x \).
   - Substitute the values: \( y_1 = 1 + (0 + 1) \cdot 0.1 \).

Let's compute this using Python:

For the first iteration, using Euler's Method, we find that \( y_1 \) at \( x = 0.1 \) is approximately \( 1.1 \).

This simple iteration exemplifies the essence of Euler's Method: using the slope at a known point to estimate the value at the next point. For more accurate results, smaller step sizes or more sophisticated methods like Runge-Kutta can be employed.

Extend the previous example by computing several iterations using Euler's Method. We'll continue with the differential equation:

$$
\frac{dy}{dx} = x + y, \quad y(0) = 1
$$

and use a step size \( \Delta x = 0.1 \). We'll compute the values of \( y \) at \( x = 0.2, 0.3, \) and \( 0.4 \), each time using the value from the previous step.

#### Iterative Procedure:

1. **Iteration for \( x = 0.1 \):** (Already computed)
   - \( y_1 = 1.1 \)
2. **Iteration for \( x = 0.2 \):**
   - Calculate \( y_2 = y_1 + f(x_1, y_1) \cdot \Delta x \)
3. **Iteration for \( x = 0.3 \):**
   - Calculate \( y_3 = y_2 + f(x_2, y_2) \cdot \Delta x \)
4. **Iteration for \( x = 0.4 \):**
   - Calculate \( y_4 = y_3 + f(x_3, y_3) \cdot \Delta x \)

Let's compute these using Python:

After performing the iterative calculations using Euler's Method, the approximated values of \( y \) at different points are as follows:

- \( y(0.1) \approx 1.1 \)
- \( y(0.2) \approx 1.22 \)
- \( y(0.3) \approx 1.362 \)
- \( y(0.4) \) (which would be the next step in the sequence)

These values represent the estimated solutions of the differential equation \( \frac{dy}{dx} = x + y \) at the respective \( x \) values, using a step size of \( 0.1 \). The method's simplicity makes it attractive for initial approximations, though, for more accuracy, smaller step sizes or advanced methods might be necessary.

Let's take another example to demonstrate Euler's Method with all calculations shown in detail. Consider the differential equation:

$$
\frac{dy}{dx} = 3e^{-x} - 0.4y, \quad y(0) = 5
$$

Our goal is to approximate the values of \( y \) at several points using Euler's Method with a step size \( \Delta x = 0.1 \). We'll compute the values of \( y \) at \( x = 0.1, 0.2, \) and \( 0.3 \).

#### Detailed Calculations:

1. **Initial Condition:**
   - \( x_0 = 0, y_0 = 5 \)
2. **Function:**
   - \( f(x, y) = 3e^{-x} - 0.4y \)
3. **Iteration for \( x = 0.1 \):**
   - \( y_1 = y_0 + f(x_0, y_0) \cdot \Delta x \)
   - \( y_1 = 5 + (3e^{-0} - 0.4 \cdot 5) \cdot 0.1 \)
4. **Iteration for \( x = 0.2 \):**
   - \( y_2 = y_1 + f(x_1, y_1) \cdot \Delta x \)
   - \( y_2 = y_1 + (3e^{-0.1} - 0.4 \cdot y_1) \cdot 0.1 \)
5. **Iteration for \( x = 0.3 \):**
   - \( y_3 = y_2 + f(x_2, y_2) \cdot \Delta x \)
   - \( y_3 = y_2 + (3e^{-0.2} - 0.4 \cdot y_2) \cdot 0.1 \)

Let's perform these calculations using Python:

For the differential equation \( \frac{dy}{dx} = 3e^{-x} - 0.4y \) with the initial condition \( y(0) = 5 \), using Euler's Method with a step size \( \Delta x = 0.1 \), the calculated values of \( y \) at various points are as follows:

- \( y(0.1) \approx 5.1 \)
- \( y(0.2) \approx 5.167 \)
- \( y(0.3) \approx 5.206 \)

These approximations are derived by sequentially applying Euler's Method, using the slope at each step to estimate the value of \( y \) at the next point. Each step's result depends on the previous step, demonstrating the iterative nature of the method.

- We can sort of ascertain where the graph is going, and where the equation tends to.


# Rigorous Explanation:

Certainly, let's reformulate Euler's Method adhering to the prescribed format, with distinct separation of mathematical expressions and text for clarity and precision.

### Definitions

1. **Ordinary Differential Equation (ODE):**
   An ODE involves a function of one independent variable and its derivatives. It is typically written as 
   $$
   F(x, y, y', y'', \dots, y^{(n)}) = 0,
   $$
   where \( y = y(x) \) is the unknown function, and \( y', y'', \dots, y^{(n)} \) are its derivatives.

2. **Initial Value Problem (IVP):**
   An IVP is composed of an ODE coupled with a specified value, called the initial condition, of the unknown function at a particular point. Formally, it is expressed as:
   $$
   \frac{dy}{dx} = f(x, y), \quad y(x_0) = y_0
   $$

3. **Step Size (\( \Delta x \)):**
   This is the interval over which we progress the approximation in each iteration. Defined as a positive real number, it is crucial for determining the granularity of the approximation.

### Euler's Method Formulation

Given the IVP:
$$
\frac{dy}{dx} = f(x, y), \quad y(x_0) = y_0
$$

Euler's Method approximates \( y(x) \) at discrete points \( x_0, x_1, x_2, \dots \) using the following iterative process:

#### Iterative Process:

1. **Initialization:**
   Start with \( y_n = y_0 \), where \( y_n \) represents the approximation of \( y \) at \( x_n \).

2. **Iteration:**
   For each step \( n = 0, 1, 2, \dots, N-1 \):
   $$
   y_{n+1} = y_n + f(x_n, y_n) \cdot \Delta x
   $$
   and
   $$
   x_{n+1} = x_n + \Delta x.
   $$

### Lemmas and Properties

1. **Local Truncation Error:**
   This is the error in a single step of the method. For Euler's Method, it is proportional to \( \Delta x^2 \).

2. **Global Truncation Error:**
   This represents the cumulative error over all steps. In Euler's Method, it is proportional to \( \Delta x \).

3. **Convergence:**
   Euler's Method converges to the actual solution as \( \Delta x \rightarrow 0 \), assuming that \( f(x, y) \) satisfies certain conditions, like being Lipschitz continuous in \( y \) and continuous in \( x \).

4. **Stability:**
   The stability of Euler's Method is contingent upon the choice of \( \Delta x \) and the properties of \( f(x, y) \). It can be unstable for certain ODEs, particularly stiff equations, unless \( \Delta x \) is adequately small.

### Application Context

Euler's Method is a fundamental tool for initial approximations in solving ODEs, especially when analytic solutions are elusive. However, for higher precision or complex differential equations, advanced methods like Runge-Kutta are often preferred due to their superior stability and reduced error margins.

# Runge Kutta Method:

### Definitions

1. **Runge-Kutta Methods:**
   A family of iterative methods for approximating solutions to ordinary differential equations (ODEs). These methods are more accurate than Euler's Method and are widely used due to their balance between complexity and efficiency.

2. **Fourth-Order Runge-Kutta Method (RK4):**
   The most commonly used Runge-Kutta method, offering a good balance between computational effort and accuracy. It is particularly effective for solving initial value problems (IVPs) of the form:
   $$
   \frac{dy}{dx} = f(x, y), \quad y(x_0) = y_0
   $$

### RK4 Formulation

Given the IVP:
$$
\frac{dy}{dx} = f(x, y), \quad y(x_0) = y_0
$$

RK4 approximates \( y(x) \) at discrete points using the following iterative process:

#### Iterative Process:

1. **Initialization:**
   Begin with \( y_n = y_0 \) and \( x_n = x_0 \).

2. **Iteration:**
   For each step \( n = 0, 1, 2, \dots, N-1 \):
   
   Compute four "slopes":
   $$
   k_1 = f(x_n, y_n)
   $$
   $$
   k_2 = f\left(x_n + \frac{\Delta x}{2}, y_n + \frac{\Delta x}{2} \cdot k_1\right)
   $$
   $$
   k_3 = f\left(x_n + \frac{\Delta x}{2}, y_n + \frac{\Delta x}{2} \cdot k_2\right)
   $$
   $$
   k_4 = f(x_n + \Delta x, y_n + \Delta x \cdot k_3)
   $$

   Update \( y \) for the next step:
   $$
   y_{n+1} = y_n + \frac{\Delta x}{6} \cdot (k_1 + 2k_2 + 2k_3 + k_4)
   $$
   $$
   x_{n+1} = x_n + \Delta x
   $$

### Lemmas and Properties

1. **Local Truncation Error:**
   In RK4, the local truncation error per step is of the order of \( \Delta x^5 \), making it significantly more accurate per step than Euler's Method.

2. **Global Truncation Error:**
   The global error, which accumulates over multiple steps, is of the order of \( \Delta x^4 \), which is usually acceptable for many practical applications.

3. **Stability:**
   The RK4 method is generally more stable than Euler's Method, particularly for problems where higher accuracy is required. However, like all numerical methods, it can still be subject to stability issues depending on the problem and the chosen step size.

### Application Context

The fourth-order Runge-Kutta method is widely used due to its efficiency and accuracy, making it suitable for a broad range of applications. It is particularly favored when a good balance between computational cost and solution accuracy is required. Despite its increased complexity compared to Euler's Method, RK4 is often the method of choice for solving ODEs in practical scenarios.

