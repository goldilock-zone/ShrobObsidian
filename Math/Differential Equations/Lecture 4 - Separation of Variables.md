Separation of variables is a method often employed in solving ordinary differential equations (ODEs) where the equation can be rewritten in a form that allows each variable to appear on different sides of the equation. This method is particularly useful for first-order differential equations but can be applied to some higher-order equations under certain conditions.

Consider a first-order ODE of the form:

$$
\frac{dy}{dx} = g(x)h(y)
$$

The goal of separation of variables is to manipulate this equation so that all terms involving \( y \) are on one side of the equation, and all terms involving \( x \) are on the other side. To achieve this, we rearrange the equation as follows:

$$
\frac{1}{h(y)} \, dy = g(x) \, dx
$$

Now, we integrate both sides of the equation:

$$
\int \frac{1}{h(y)} \, dy = \int g(x) \, dx
$$

After performing the integrals, we often obtain an implicit solution involving \( y \) and \( x \), or in some cases, it may be possible to solve explicitly for \( y \) as a function of \( x \).

As an illustrative example, consider the differential equation:

$$
\frac{dy}{dx} = xy
$$

Applying separation of variables, we first rearrange the equation:

$$
\frac{1}{y} \, dy = x \, dx
$$

Then we integrate both sides:

$$
\int \frac{1}{y} \, dy = \int x \, dx
$$

Which yields:

$$
\ln|y| = \frac{1}{2} x^2 + C
$$

Where \( C \) is the constant of integration. This is an implicit solution to the original differential equation. Further manipulation can express \( y \) explicitly, assuming \( y > 0 \):

$$
y = e^{\frac{1}{2} x^2 + C} = e^C \cdot e^{\frac{1}{2} x^2}
$$

In this example, the separation of variables method provides a straightforward approach to solving a first-order ODE.

- We can get a general and a particular solution
- Exponential growth and exponential decay
- Decay to a limiting value
