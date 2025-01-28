# Dynamic-Pricing-with-Markov-Decision-Process-MDP-
This repository demonstrates a solution to a Dynamic Pricing Problem using a Markov Decision Process (MDP). The goal is to determine the optimal pricing strategy for a product over multiple time periods while considering customer demand levels and price impact.

PROBLEM OVERVIEW

Dynamic pricing involves adjusting the price of a product or service based on factors like demand, inventory levels, or market conditions. This example models the problem as an MDP where:
States (S) represent different demand levels.
Actions (A) correspond to different price levels.
Rewards (R[s, a]) denote the expected revenue when taking a specific action at a given state.
Transition Probabilities (P[s, a, s']) define the likelihood of moving from state s to s' after taking action a.
The objective is to maximize the expected revenue over a defined time horizon (N), leveraging the principles of dynamic programming.

CODE EXPLANATION

1. Parameters
The code initializes key parameters:
N: Number of time periods (e.g., 12 months).
S: Number of demand states (e.g., 5 levels of demand).
A: Number of pricing levels (e.g., low, medium, high).
gamma: Discount factor, used for adjusting future rewards. Here, gamma = 1 assumes no discounting.

2. Transition Probabilities (P) and Rewards (R)
P: A 3D array where P[s, a, s'] represents the probability of transitioning from state s to state s' after action a.
R: A 2D array where R[s, a] is the expected revenue for taking action a in state s.
For simplicity, both P and R are randomly generated in this example. In real-world applications, they should be derived from historical data or domain-specific insights.

3. Value Function (V) and Policy Initialization
V: A matrix storing the maximum expected revenue at each time period and state.
policy: A matrix that stores the optimal action for each time period and state.

4. Dynamic Programming Algorithm
The dynamic programming algorithm iterates backward in time (t = N-1 to t = 0) to solve the Bellman equation:
![image](https://github.com/user-attachments/assets/cd6e2eb7-4a70-484e-b1c7-1bf6a91b5fff)
For each state s at time t, the algorithm:
Computes the action-value function Q for all possible actions.
Selects the action that maximizes Q and updates the value function (V[t, s]).
Records the optimal action in the policy matrix (policy[t, s]).

OUTPUT 

Optimal Policy (Price levels per State and Time):
[[1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [1 1 0 1 1]
 [0 1 0 2 1]
 [0 1 1 2 1]]

Optimal Policy Matrix: The policy matrix provides the optimal price level (a) for each combination of time (t) and demand state (s).
Rows: Correspond to time periods (e.g., 0 to 11).
Columns: Represent demand levels.
Values: Indicate the price levels (e.g., 0 = low, 1 = medium, 2 = high).



