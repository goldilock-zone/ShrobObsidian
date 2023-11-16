- Proportion/Rate
- Investment differential equation
- Non continuous compounding isn't a step function
- f' = rf
	- The differential equation you've provided, f' = rf, is a first-order ordinary differential equation (ODE) known as an exponential growth or decay equation. It's a simple yet important differential equation that arises in various fields of science and engineering. Let's discuss some information, theorems, and examples related to this type of ODE:
	
	1. General Form:
	   The equation f' = rf can be written more explicitly as:
	   df/dt = rf
	   where f is a function of a single variable t, and r is a constant.
	
	2. Solutions:
	   The general solution to this ODE can be found by separation of variables and integration:
	   ∫(1/f) df = ∫r dt
	   This leads to the following solution:
	   ln|f| = rt + C
	   Where C is an arbitrary constant of integration. Solving for f, we get:
	   f(t) = Ce^(rt)
	   Where C is an integration constant, and e is the base of the natural logarithm (approximately 2.71828).
	
	3. Exponential Growth and Decay:
	   Depending on the value of the constant r, the solution describes either exponential growth or exponential decay.
	   - If r > 0, the solution represents exponential growth. The function f(t) increases without bound as t increases.
	   - If r < 0, the solution represents exponential decay. The function f(t) approaches zero as t increases.
	
	4. Time Constants:
	   The parameter 1/|r| is often referred to as the "time constant" of the solution. In the context of exponential growth or decay, it indicates how quickly the quantity represented by f(t) changes over time.
	
	5. Examples:
	   a. Population Growth: The exponential growth equation is often used to model population growth, where r represents the growth rate, and f(t) represents the population at time t.
	   
	   b. Radioactive Decay: The exponential decay equation is commonly used to model the decay of radioactive materials, where r represents the decay constant, and f(t) represents the remaining amount of a radioactive substance at time t.
	
	   c. Financial Investments: This equation can also model the growth or decay of financial investments, where r represents the annual interest rate, and f(t) represents the value of the investment at time t.
	
	6. Theorems and Applications:
	   - This type of ODE is a fundamental building block for more complex differential equations used in various scientific and engineering applications.
	   - It is closely related to the concept of exponential functions, which have wide-ranging applications in mathematics and the natural sciences.
	   - In control theory and signal processing, solutions to this ODE play a crucial role in understanding the behavior of systems with exponential response characteristics.
	
	In summary, the differential equation f' = rf is a simple but important equation that describes exponential growth or decay processes. Its solutions have applications in various fields, including biology, physics, finance, and engineering, and it serves as a foundational concept in the study of differential equations.

- Decay just means that the constant before the equation is negative
- Differences may be modelled by this system as well
- Steady States
	- In the realm of mathematics, particularly in differential equations and dynamical systems, the concept of "steady states" plays a pivotal role. A steady state refers to a condition in a dynamical system where the system does not change over time. In mathematical terms, this is characterized by the state variables remaining constant. 
	
	To illuminate this concept, consider a general ordinary differential equation (ODE):
	
	$$ \frac{dx}{dt} = f(x) $$
	
	Here, \( x \) is the state variable, and \( f(x) \) is a function describing the rate of change of \( x \). A steady state \( x_s \) is reached when the rate of change is zero:
	
	$$ f(x_s) = 0 $$
	
	This condition implies that at the steady state, the system is in equilibrium; there's no net change in the state variable \( x \). 
	
	The nature of these steady states—whether they are stable, unstable, or neutrally stable—depends on the specific dynamics of the system, often analyzed using techniques like linearization or phase plane analysis. 
	
	In various scientific fields, steady states are foundational. For instance, in ecology, they represent population levels that remain constant over time. In chemistry, they denote concentrations that don't change in a reaction. And in economics, they symbolize equilibrium points where factors like supply and demand balance out.

- Newton's Law of Cooling
	- The scenario of a coffee cup cooling to ambient temperature provides an excellent illustration of a real-world application of differential equations and steady states. This situation can be modeled using Newton's Law of Cooling, which states that the rate of change of the temperature of an object is proportional to the difference between its own temperature and the ambient temperature.
	
	Let's denote:
	- \( T(t) \) as the temperature of the coffee at time \( t \),
	- \( T_a \) as the constant ambient temperature, and
	- \( k \) as a positive constant that depends on the properties of the coffee and the cup.
	
	Newton's Law of Cooling is then represented by the following ordinary differential equation (ODE):
	
	$$ \frac{dT}{dt} = -k(T - T_a) $$
	
	This equation expresses that the rate of change of the coffee's temperature over time is proportional to the difference between the coffee's temperature and the room temperature. The negative sign indicates that the coffee's temperature decreases over time (assuming \( T > T_a \)).
	
	To solve this equation, we separate variables and integrate. The general solution will be of the form:
	
	$$ T(t) = T_a + (T_0 - T_a)e^{-kt} $$
	
	Here, \( T_0 \) is the initial temperature of the coffee.
	
	As \( t \) approaches infinity, the exponential term \( e^{-kt} \) approaches zero, indicating that the coffee's temperature approaches the ambient temperature. This is the steady state of the system, where the temperature of the coffee remains constant and equal to the ambient temperature \( T_a \).
	
	This model simplifies the real-world scenario by assuming that the ambient temperature remains constant and that the heat transfer coefficient \( k \) does not change with temperature. In more complex models, these factors can also vary, leading to more complex differential equations.

- Graphing Steady states in newton's law of cooling
	- ![[Pasted image 20231116074427.png]]
	- The graph illustrates the cooling of coffee over time, modeled using Newton's Law of Cooling. Here, the coffee starts at an initial temperature of 90°C and cools down towards the ambient temperature, which is set at 20°C.
	
	The brown curve represents the temperature of the coffee as a function of time. It shows a rapid decrease initially, which gradually slows down as the coffee's temperature approaches the ambient temperature. The blue dashed line represents the constant ambient temperature.
	
	As time progresses, the temperature of the coffee asymptotically approaches the ambient temperature, illustrating the steady state of the system. In this state, the coffee's temperature remains constant and equal to the ambient temperature, signifying that it has reached thermal equilibrium with its surroundings.
	
	This graph effectively demonstrates how differential equations can model real-world phenomena, providing insights into how systems evolve over time towards steady states.

- Steady State: Constant
- Examples:
	  Limiting steady states in mathematical models often describe the long-term behavior of a system as time progresses towards infinity. These steady states are particularly significant in various fields, including biology, chemistry, physics, and economics. Let's explore a few examples across different disciplines:
	
	1. **Population Dynamics (Biology)**:
	   - **Logistic Growth Model**: Consider a population with limited resources. The logistic growth model, given by the differential equation
	     $$ \frac{dP}{dt} = rP\left(1 - \frac{P}{K}\right) $$
	     where \( P \) is the population size, \( r \) is the growth rate, and \( K \) is the carrying capacity, has two steady states: \( P = 0 \) and \( P = K \). The latter, \( P = K \), is a limiting steady state representing the maximum population that the environment can sustain indefinitely.
	
	2. **Chemical Reactions (Chemistry)**:
	   - **Equilibrium State**: In a reversible chemical reaction, the system eventually reaches a state where the forward and reverse reaction rates are equal, and the concentrations of reactants and products remain constant. This steady state is described by the equilibrium constant, and it represents the limiting condition of the reaction.
	
	3. **Heat Transfer (Physics)**:
	   - **Thermal Equilibrium**: As discussed earlier with the coffee cooling example, an object in a thermal environment eventually reaches a steady state where its temperature equals the ambient temperature. This thermal equilibrium is a limiting steady state.
	
	4. **Economic Growth (Economics)**:
	   - **Solow Growth Model**: In this macroeconomic model, an economy's output eventually stabilizes at a steady state where capital accumulation is balanced by depreciation and population growth. This limiting steady state represents a situation where per capita output and capital remain constant over time.
	
	In each of these examples, the limiting steady state represents a long-term equilibrium or balance point of the system. Whether it's a population reaching its carrying capacity, a chemical reaction achieving equilibrium, an object reaching ambient temperature, or an economy stabilizing its growth, these states are fundamental in understanding the long-term behavior of dynamic systems. 
- Decays to carrying capacity
- Logistic Equation: 
	- The Logistic Equation is a classic model in population dynamics, illustrating how a population grows in a limited-resource environment. It provides a more realistic approach compared to the exponential growth model, which assumes unlimited resources. The Logistic Equation is given by:

$$ \frac{dP}{dt} = rP\left(1 - \frac{P}{K}\right) $$

	Here:
	- \( P \) represents the population size.
	- \( r \) is the intrinsic growth rate.
	- \( K \) is the carrying capacity of the environment, the maximum population that can be sustained indefinitely.
	
	### Analysis of the Equation
	
	1. **Growth Dynamics**: 
	   - When \( P \) is small relative to \( K \), the term \( \frac{P}{K} \) is also small, and the equation approximates to \( \frac{dP}{dt} \approx rP \), which is essentially exponential growth.
	   - As \( P \) increases and approaches \( K \), the growth rate decreases. The term \( \left(1 - \frac{P}{K}\right) \) becomes significant, reducing the rate of growth.
	
	2. **Steady States**: 
	   - The steady states occur when \( \frac{dP}{dt} = 0 \), which happens at \( P = 0 \) and \( P = K \). 
	   - The state \( P = 0 \) is usually unstable — if the population has any positive number, it will grow away from zero.
	   - The state \( P = K \) is stable — the population will tend towards this value from either side.
	
	3. **S-Curve or Logistic Curve**:
	   - The solution of this differential equation is an S-shaped curve. Initially, the population grows exponentially, then the growth rate slows down, and finally, it stabilizes at the carrying capacity \( K \).
	
	### Solving the Equation
	
	The general solution to the Logistic Equation, given an initial condition \( P(0) = P_0 \), is:
	
	$$ P(t) = \frac{K}{1 + \left(\frac{K}{P_0} - 1\right)e^{-rt}} $$
	
	This formula represents the population size at any time \( t \). As \( t \) approaches infinity, \( P(t) \) approaches \( K \), reflecting the limiting steady state.

- ![[Pasted image 20231116075349.png]]

- Family of solutions
	The graph above illustrates a family of solution curves for the Logistic Growth Model, each corresponding to a different initial population size. These curves collectively provide a comprehensive view of how the population evolves over time under various initial conditions.
	![[Pasted image 20231116075608.png]]
	Key Aspects:
	
	1. **Diverse Initial Conditions**: The curves represent a range of initial population sizes, from 50 to 1500. This diversity allows us to observe how different starting points affect the population growth trajectory.
	
	2. **Convergence to Carrying Capacity**: Regardless of the initial size, each curve eventually converges to the carrying capacity (marked by the red dashed line at \( K = 1000 \)). This convergence demonstrates the stabilizing effect of the carrying capacity in a resource-limited environment.
	
	3. **Growth Patterns**: For initial populations below the carrying capacity, the growth is initially rapid (similar to exponential growth), then slows down as it approaches \( K \). For populations starting above the carrying capacity, the population decreases until it stabilizes at \( K \).
	
	4. **S-Shaped Curves**: Each curve exhibits the characteristic S-shape of logistic growth, initially steep and then leveling off.
	
	This graphical representation provides a clear and visual understanding of how the Logistic Growth Model behaves under different starting conditions, highlighting the flexibility and applicability of differential equations in modeling real-world phenomena.








