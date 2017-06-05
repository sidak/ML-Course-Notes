## Lec 2

- Reinforcement learning is what life is all about. You don't know what's good or bad, you kinda have to just let it and every once a while you find
all that stuff you did last week was a pretty bad idea (or luckily good).

- *Universality*: NAND gates (0 if both inputs are 1s, 1 otherwise) are functionally complete, meaning we can build any logical function by stacking them 
in arbitrary ways.

- We can also implement a NAND gate from a perceptron. (with parameters as w1=-2, w2=-2, b=3)

- Perceptrons are more powerful than NAND gates. Because while a circuit of neurons (or the neural network) can perform the same thing as the circuit of NAND gates, what it can also do is learn. It can learn any arbitrary function but it doesn't require the human designer (to layout gates).

- Drawbacks of the perceptron is that it is not very smooth in its output. As we tweak the weight or the bias a little bit, it's very easy to make the neuron output a 0 instead of a 1. And when we start stacking many of these together, it's hard to control the output of a thing as a whole. 

- The essential step that makes a neural network work, but a circuit of perceptrons doesn't is if the output is made smooth (or continuous) with an activation function. So instead of a *step* function in perceptron, use something like *sigmoid*. 

- Smoothness of activation function means: the change in the output is a linear function of the change in weights and change in the bias.

- Learning is the process of gradually adjusting the weights to achieve any gradual change in the output. 

- Combining Neurons into layers
	- Feed Forward Neural Net
	- Recurrent Neural Net 
		- Have state memory 
		- But hard to train 

- Also, because of the smoothness of the activation functions, backpropogation is a mathematically efficient operation

- Loss function is highly non-linear & high dimensional function, this is why we can't prove much about neural networks.

- There has to be a stochastic element so that it jumps around and ensures that it doesn't get stuck on a local minima.

### Reinforcement Learning (RL)

- *Hope for Reinforcement Learning*: Brute-force propagation of outcomes to knowledge about states and actions. This is kind of brute-force "reasoning". 

- It is a general purpose framework for decision-making
	- An agent operates in an environment 
	- An agent has the capacity to act
	- Each action influences the agent's future state
	- Success is measured by a reward signal
	- Goal is to select actions that maximize the reward

- This can be modeled as a *Markov Decision Process*. It is a mathematically convenient construct that has no memory

`s_0->a_0->r_0->s_1->a_1->r_1.......s_n-1->a_n-1->r_n-1->s_n`

- Components of RL Agent:
	- *Policy*: agent's behavior function (knowledge of how for any given state, what action will I take with some probabilty)
	- *Value function*: How good each state/action are?
	- *Model*: agent's representation of the environment

- Actions can be non-deterministic (as human life is. Where when you turn right, you may sometimes go up)

- The Agent can take a longer detour as the punishment goes down.

- But like the Coast-runner example, don't go around in circles and have fun taking so many points, while forgetting the ultimate goal (of winning the race).

- The reward is discounted because the world/environment is stochastic. We can't expect the reward to come along to us in the way we hope based on the policy.     

![Discounted Reward Formulation](https://raw.githubusercontent.com/sidak/ML-Course-Notes/master/MIT%206.S094%20Deep%20Learning%20for%20Self-Driving%20Cars/img/DiscountedRewardFormulation.png)

- As the reward is farther and farther into the future, gamma discounts that award or diminishes the impact of the future reward in the evaluation of the current state. 

- The goal is to develop a strategy that maximizes the discounted future award. 

- Approaches for coming up with a good (or optimal or near optimal) policy:
	- Try to construct a model that optimizes some estimate of the world
	- Try it in a Monte carlo way, to simulate the world and see how it unrolls, and then compute the optimal policy.
	- Q-learning, which is an off-policy approach where the Q values are estimated as we go along. Through experience (like playing more and more games), it can estimate the optimal Q function. 

#### Q-learning

- State-value function (V): Expected reward/return when starting in s and following policy (pi)

- State-action value function (Q): Expected reward/return when starting in s, performing a and following policy (pi)  

- The reason that Q-learning is off-policy is that it updates its Q-values using the Q-value of the next state s' and the greedy action a'. In other words, it estimates the return (total discounted future reward) for state-action pairs assuming a greedy policy were followed despite the fact that it's not following a greedy policy.

- Keep updating the Q values for each of the (s,a) pair.

![Q update](https://raw.githubusercontent.com/sidak/ML-Course-Notes/master/MIT%206.S094%20Deep%20Learning%20for%20Self-Driving%20Cars/img/QUpdate.png)

- Exploration v/s Exploitation:
	- The basic idea is to try out the various actions in the beginning (explore), and then later settle for a greedy/optimal action (exploit).
	- Thus, key ingredient of RL: **(First explore, then exploit)**
	- Also, use soft polices (where pi(s,a) > 0 for all s, a)

- Formally, follow an epsilon-greedy policy
	- With probability of `1-epsilon`, perform the optimal/greedy action	
	- With probability of `epsilon`, perform a random action
	- Slowly move it towards greedy policy (epsilon = 0)

- Value Iteration ![Value Iteration](https://raw.githubusercontent.com/sidak/ML-Course-Notes/master/MIT%206.S094%20Deep%20Learning%20for%20Self-Driving%20Cars/img/ValueIteration.png)

- In practice, this value iteration method is impractical
	- Take the case of Breakout game, where the model representation is:
	 ![Breakout](https://raw.githubusercontent.com/sidak/ML-Course-Notes/master/MIT%206.S094%20Deep%20Learning%20for%20Self-Driving%20Cars/img/breakout.png)
		- Image size: 84x84
		- Take last 4 images (as per time)
		- Grayscale with 256 gray levels
	- Overall complexity: `256*(84*84*4)` rows in the Q-table

- What does it mean to have a deep RL agent succeed on a game like Breakout









