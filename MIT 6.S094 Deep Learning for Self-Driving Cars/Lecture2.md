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

### Reinforcement Learning

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
	- *Policy*:agent's behavior function (for any given state, knowledge of what action will I take with some probabilty)
	- *Value function*: How good each state/action are?
	- *Model*: agent's representation of the environment

- Actions can be non-deterministic (as human life is. Where when you turn right, you sometimes go up)

- The Agent can take a longer detour as the punishment goes down.

- But like the Coast-runner example, don't go around in circles and have fun taking so many points, while forgetting the ultimate goal (of winning the race).

- The reward is discounted because the world/environment is stochastic. We can't expect the reward to come along to us in the way we hope based on the policy.     

[!Discounted Reward Formulation](https://raw.githubusercontent.com/sidak/ML-Course-Notes/master/MIT%206.S094%20Deep%20Learning%20for%20Self-Driving%20Cars/img/DiscountedRewardFormulation.png)

- 


