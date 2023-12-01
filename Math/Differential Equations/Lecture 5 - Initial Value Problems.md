Initial Value Problems (IVPs) in the context of differential equations are scenarios where the equation is accompanied by specific conditions, usually specifying the value of the unknown function at a particular point. These conditions are essential for determining a unique solution to the differential equation.

An IVP typically consists of a differential equation along with an initial condition. For a first-order ordinary differential equation (ODE), the general form is:

$$
\frac{dy}{dx} = f(x, y), \quad y(x_0) = y_0
$$

Here, $$ \frac{dy}{dx} = f(x, y) $$ is the ODE, and \(y(x_0) = y_0\) is the initial condition, which specifies that the solution \(y(x)\) must pass through the point \((x_0, y_0)\).

The process of solving an IVP involves two primary steps:

1. **Solve the Differential Equation:** Find the general solution of the ODE. This involves integrating the differential equation, which may result in one or more arbitrary constants.

2. **Apply the Initial Condition:** Substitute the initial condition into the general solution to find the specific value of the constant(s), thereby obtaining the particular solution that satisfies the initial condition.

To illustrate, consider the first-order ODE:

$$
\frac{dy}{dx} = xy
$$

with the initial condition \(y(0) = 1\).

1. **Solve the ODE:** As previously demonstrated, using separation of variables, the general solution is:

   $$
   y = Ce^{\frac{1}{2} x^2}
   $$

   where \(C\) is an arbitrary constant.

2. **Apply the Initial Condition:** Substituting \(x = 0\) and \(y = 1\) into the general solution gives:

   $$
   1 = Ce^{\frac{1}{2} \cdot 0^2} = C
   $$

   Therefore, \(C = 1\), and the particular solution to the IVP is:

   $$
   y = e^{\frac{1}{2} x^2}
   $$

In this example, the initial condition was crucial in determining the unique solution that satisfies both the differential equation and the condition \(y(0) = 1\). Without this condition, the solution would remain general, encompassing an infinite number of possible solutions represented by different values of \(C\).


### Example 1: Linear First-Order ODE

Consider the linear first-order ODE:

$$
\frac{dy}{dx} + 2y = 4, \quad y(0) = 1
$$

**Solution Steps:**

1. **Solve the ODE:** We use an integrating factor, \( \mu(x) = e^{\int 2 \, dx} = e^{2x} \), to solve. Multiplying the entire differential equation by this factor, we get:

   $$
   e^{2x} \frac{dy}{dx} + 2e^{2x}y = 4e^{2x}
   $$

   This simplifies to:

   $$
   \frac{d}{dx}(e^{2x}y) = 4e^{2x}
   $$

   Integrating both sides:

   $$
   e^{2x}y = 2e^{2x} + C
   $$

   Thus, the general solution is:

   $$
   y = 2 + Ce^{-2x}
   $$

2. **Apply the Initial Condition:** Substituting \( y(0) = 1 \):

   $$
   1 = 2 + C \cdot e^{0} \Rightarrow C = -1
   $$

   Therefore, the particular solution is:

   $$
   y = 2 - e^{-2x}
   $$

### Example 2: Separable First-Order ODE

Consider the separable ODE:

$$
\frac{dy}{dx} = x^2 y, \quad y(1) = 2
$$

**Solution Steps:**

1. **Solve the ODE:** Rearranging and integrating:

   $$
   \frac{1}{y} dy = x^2 dx
   $$

   Integrating both sides:

   $$
   \ln|y| = \frac{1}{3}x^3 + C
   $$

   Thus, the general solution is:

   $$
   y = Ce^{\frac{1}{3}x^3}
   $$

2. **Apply the Initial Condition:** Substituting \( y(1) = 2 \):

   $$
   2 = Ce^{\frac{1}{3}}
   $$

   Solving for \( C \), we find the particular solution:

   $$
   y = 2e^{-\frac{1}{3}}e^{\frac{1}{3}x^3}
   $$

### Example 3: Second-Order Linear Homogeneous ODE

Consider:

$$
\frac{d^2y}{dx^2} - 4\frac{dy}{dx} + 4y = 0, \quad y(0) = 1, \, y'(0) = 0
$$

**Solution Steps:**

1. **Solve the ODE:** The characteristic equation is \( r^2 - 4r + 4 = 0 \) with roots \( r = 2 \) (a repeated root). Thus, the general solution is:

   $$
   y = (C_1 + C_2x)e^{2x}
   $$

2. **Apply the Initial Conditions:**

   - Substituting \( y(0) = 1 \) gives \( C_1 = 1 \).
   - Differentiating and applying \( y'(0) = 0 \), we get \( 2C_1 + C_2 = 0 \), leading to \( C_2 = -2 \).

   Therefore, the particular solution is:

   $$
   y = (1 - 2x)e^{2x}
   $$

In each example, the initial condition(s) were pivotal in determining the unique solution that satisfied both the differential equation and the specified conditions.

