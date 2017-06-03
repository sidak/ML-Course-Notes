## Lec 1
	
- Is driving more like a conversation or a chess game?

- Chess pieces: Self-driving car tasks
	
	- Localization and Mapping: Where am I?
	- Scene Understanding: Where is everyone else?
	- Movement Planning: How do I get from A to B?
	- Driver State: What’s the driver up to?

- If driving is a conversation: How hard it is to pass the Turing test?

	1. *Natural language processing* to enable it to communicate successfully
	2. *Knowledge representation* to store information provided before or during the interrogation
	3. *Automated reasoning* to use the stored information to answer questions and to draw new conclusions

- It's still unclear what the various layers of neural networks do. For tasks like image classification, we are able to somewhat visualize that,
but for others like driving, it's still a mystery

- *Ponder*: When should a neural network be able to add more layers?

- Deep learning is representation learning. In traditional machine learning, we generally provide good representations!

- Various learning paradigms
	
	- Rule based systems : hand designed programs
	- Classical ML: hand designed features + Mapping from features
	- Representation learning: learnt features + mapping from features
		- Deep learning: learnt features + additional layers of more abstract learnt features + mapping from features

- Computer Vision is Hard
	
	- Illumination Visibility
	- Pose variability and occlusions
	- Intra-class variability

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

	- LIDAR (Light Detection and Ranging): A range sensor that gives the 3d point cloud of the objects in the external environment. 
		- Cause of concern (*LIDAR Spoofing*): We are able to successfully do a replay attack where the car can see people and other cars around it, when in reality there is nothing around it. 

- *Doubt*: Connectionism?

- Proceed with caution. Don't overhype and lead to another AI winter!

- What's next for Deep Learning?

	- Ilya Sutskever (OpenAI): Deeper models, models that need fewer examples for training
	- Christian Szegedy (Google): Make them efficient enough to be able to run on cheap mobile devices
	- Pieter Abbeel (UC Berkeley): Deep unsupervised and Deep reinforcement learning
	- Ian Goodfellow (Google): Neural Nets that summarize what happens in a video clip, and be able to generate videos. 
	- Koray Kavukcuoglu & Alex Graves (DeepMind): Multimodal learning, i.e., learning from multiple datasets from different sources.   

- Frameworks:

	- TensorFlow -> Google (Interface: Python)
		- Keras (a layer on the top of TensorFlow to provide a simpler interface)
	- Torch -> Twitter, Facebook (Helpful for researchers doing lower level, Interface: Lua)
	- Theano -> University De Montreal (Also encourages low-level tinkering, Interface: Python)
	- cuDNN -> Nvidia (Library that most frameworks use for doing actual computation, primitive neural net functions)
	- mxnet -> Amazon (Interface: Python, R, Julia, Go)
	- Neon -> Nervana/Intel (Interface: Python, often best on benchmarks, neural net chip)
	- Caffe -> Berkeley (Interface: Python, C++, focus on Computer Vision)
	- Cognitive ToolKit (CNTK) -> Microsoft (Interface: Custom Language (Brainscript), Python, C++)
	- ConvNetJS -> Andrej Karpathy (Interface: Javascript, good for explaining neural net concepts, supports CNN, RNN, Deep Q learning)