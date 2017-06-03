## Lec 1
	
- Is driving more like a conversation or a chess game?

- It's still unclear what the various layers of neural networks do. For tasks like image classification, we are able to somewhat visualize that,
but for others like driving, it's still a mystery

- *Ponder*: When should a neural network be able to add more layers?

- Deep learning is representation learning. In traditional machine learning, we generally provide good representations!

- Various learning paradigms
	- Rule based systems : hand designed programs
	- Classical ML: hand designed features + Mapping from features
	- Repn learning: learnt features + mapping from features
		- Deep learning: learnt  features + additional layers of more abstract learnt features + mapping from features

- Applications:

	- Image colorization dataset: take new movies, and grayscale them to get labeled examples

	- Image caption generation: detect words -> generate sentences -> re-rank sentences

- Moravec's paradox: the 'easy' problems are hard walking for robots (something which we take for granted)

	- Encoded in the large, highly evolved sensory and motor portions of the human brain is a billion years of experience about the nature of the world and how to survive in it

	- *Visual perception*: 540 million years of data (when did life start for us??)
	- *Bipedal movement*: 230+ million years of data
	- *Abstract thought*: 100 thousand years of data

	- Abstract thought is what we consider to be reasoning. It is a new trick, perhaps less than thousand years old. We have not yet mastered it. It is not all that intrinsically difficult, it just seems so when we do it. (simply: we have basically had more experience (data) and training for visual and motor tasks than abstract thinking, so we don't think them to be as difficult than the later)

- Walking is hard. How hard is driving?

	- Human performance: 1 fatality per 100,000,000 miles
	- Error rate for AI to improve upon : 0.000001%

	*(While for something like Imagenet, we are happy with an error rate of 3-4%)*

	- Challenges such as snow, heavy rain, any pedestrian behaving irresponsibly or unpredictably, parking lots, merging
		into high speed stream of oncoming traffic. 

- Robustness:
	- Neural nets can be fooled by a little distortion
		- Example: Adding a particular noise to an image of bus, causes the neural net to declare it as an ostrich, while perceivably there has been no change!

- What's Connectionism?

- What's next for Deep Learning?

	- Ilya Sutskever (OpenAI): Deeper models, models that need fewer examples for training






