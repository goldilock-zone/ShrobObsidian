The Gini coefficient is a useful, and simple tool to measure the effective inequality that emerges out of the setting of the game. Other measures, such as the Theil Index, would add to the computational complexity of the algorithm, running the game. The structure of the code used to build the simulations ran a loop for all objects on the gameboard, and using this structure, it would be trivially easy to calculate the required coefficient at the end of each simulation. 
The calculation of the value of the coefficient does not follow the theoretical definition as a probability density function [^1], that involves integration, again to reduce computation. It attempts to build a Lorenz curve, and calculate the value explicitly. 

[^1]: [Approximate Bayesian computation for Lorenz curves from grouped data | SpringerLink](https://link.springer.com/article/10.1007/s00180-018-0831-x#citeas)

