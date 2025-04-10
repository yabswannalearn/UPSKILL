# Deep learning[^1]

_Deep learning_ is an advanced form of machine learning that tries to emulate the way the human brain learns. The key to deep learning is the creation of an artificial _neural network_ that simulates electrochemical activity in biological neurons by using mathematical functions, as shown here.

| Biological neural network                                                                                                                                         | Artificial neural network                                                                                                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![Diagram of a natural neural network.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/biological-neural-network.png) | ![Diagram of an artificial neural network.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/artificial-neural-network.png)                            |
| Neurons fire in response to electrochemical stimuli. When fired, the signal is passed to connected neurons.                                                       | Each neuron is a function that operates on an input value (_**x**_) and a _weight_ (_**w**_). The function is wrapped in an _activation_ function that determines whether to pass the output on. |

Artificial neural networks are made up of multiple _layers_ of neurons - essentially defining a deeply nested function. This architecture is the reason the technique is referred to as _deep learning_ and the models produced by it are often referred to as _deep neural networks_ (DNNs). You can use deep neural networks for many kinds of machine learning problem, including regression and classification, as well as more specialized models for natural language processing and computer vision.

Just like other machine learning techniques discussed in this module, deep learning involves fitting training data to a function that can predict a label (_**y**_) based on the value of one or more features (_**x**_). The function (_**f(x)**_) is the outer layer of a nested function in which each layer of the neural network encapsulates functions that operate on _**x**_ and the weight (_**w**_) values associated with them. The algorithm used to train the model involves iteratively feeding the feature values (_**x**_) in the training data forward through the layers to calculate output values for _**ŷ**_, validating the model to evaluate how far off the calculated _**ŷ**_ values are from the known _**y**_ values (which quantifies the level of error, or _loss_, in the model), and then modifying the weights (_**w**_) to reduce the loss. The trained model includes the final weight values that result in the most accurate predictions.

## Example - Using deep learning for classification

To better understand how a deep neural network model works, let's explore an example in which a neural network is used to define a classification model for penguin species.

![Diagram of a neural network used to classify a penguin species.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/deep-classification.png)

The feature data (_**x**_) consists of some measurements of a penguin. Specifically, the measurements are:

- The length of the penguin's bill.
- The depth of the penguin's bill.
- The length of the penguin's flippers.
- The penguin's weight.

In this case, _**x**_ is a vector of four values, or mathematically, _**x=[x1,x2,x3,x4]**_.

The label we're trying to predict (_**y**_) is the species of the penguin, and that there are three possible species it could be:

- Adelie
- Gentoo
- Chinstrap

This is an example of a classification problem, in which the machine learning model must predict the most probable class to which an observation belongs. A classification model accomplishes this by predicting a label that consists of the probability for each class. In other words, y is a vector of three probability values; one for each of the possible classes: _**[P(y=0|x), P(y=1|x), P(y=2|x)]**_.

The process for inferencing a predicted penguin class using this network is:

1. The feature vector for a penguin observation is fed into the input layer of the neural network, which consists of a neuron for each _**x**_ value. In this example, the following _**x**_ vector is used as the input: _**[37.3, 16.8, 19.2, 30.0]**_
2. The functions for the first layer of neurons each calculate a weighted sum by combining the _**x**_ value and _**w**_ weight, and pass it to an activation function that determines if it meets the threshold to be passed on to the next layer.
3. Each neuron in a layer is connected to all of the neurons in the next layer (an architecture sometimes called a _fully connected network_) so the results of each layer are fed forward through the network until they reach the output layer.
4. The output layer produces a vector of values; in this case, using a _softmax_ or similar function to calculate the probability distribution for the three possible classes of penguin. In this example, the output vector is: _**[0.2, 0.7, 0.1]**_
5. The elements of the vector represent the probabilities for classes 0, 1, and 2. The second value is the highest, so the model predicts that the species of the penguin is **1** (Gentoo).

### How does a neural network learn?

The weights in a neural network are central to how it calculates predicted values for labels. During the training process, the model _learns_ the weights that will result in the most accurate predictions. Let's explore the training process in a little more detail to understand how this learning takes place.

![Diagram of a neural network being trained, evaluated, and optimized.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/neural-network-training.png)

1. The training and validation datasets are defined, and the training features are fed into the input layer.
2. The neurons in each layer of the network apply their weights (which are initially assigned randomly) and feed the data through the network.
3. The output layer produces a vector containing the calculated values for _**ŷ**_. For example, an output for a penguin class prediction might be _**[0.3. 0.1. 0.6]**_.
4. A _loss function_ is used to compare the predicted _**ŷ**_ values to the known _**y**_ values and aggregate the difference (which is known as the _loss_). For example, if the known class for the case that returned the output in the previous step is _Chinstrap_, then the _**y**_ value should be _**[0.0, 0.0, 1.0]**_. The absolute difference between this and the _**ŷ**_ vector is _**[0.3, 0.1, 0.4]**_. In reality, the loss function calculates the aggregate variance for multiple cases and summarizes it as a single _loss_ value.
5. Since the entire network is essentially one large nested function, an optimization function can use differential calculus to evaluate the influence of each weight in the network on the loss, and determine how they could be adjusted (up or down) to reduce the amount of overall loss. The specific optimization technique can vary, but usually involves a _gradient descent_ approach in which each weight is increased or decreased to minimize the loss.
6. The changes to the weights are _backpropagated_ to the layers in the network, replacing the previously used values.
7. The process is repeated over multiple iterations (known as _epochs_) until the loss is minimized and the model predicts acceptably accurately.

 Note

While it's easier to think of each case in the training data being passed through the network one at a time, in reality the data is batched into matrices and processed using linear algebraic calculations. For this reason, neural network training is best performed on computers with graphical processing units (GPUs) that are optimized for vector and matrix manipulation.

[^1]: Deep learning is a fancy type of machine learning that tries to learn like our brains. It uses artificial "brain cells" called neurons in many layers, forming a "deep" network.
	
	**Think of it like this:** Imagine a team of people passing information down a line. Each person does a little calculation and decides if the message is important enough to pass on. The final person gives the answer.
	
	**How it works:**
	
	- **Artificial Neural Networks:** These networks have layers of connected neurons. Each neuron takes in numbers, does some math (using "weights"), and decides whether to send a signal to the next layer.
	- **Deeply Nested Functions:** Because there are many layers, the whole network is like one big, complex math problem built from smaller ones.
	- **Learning from Data:** Just like other machine learning, you feed the network examples (like pictures of penguins with their species).
	- **Adjusting the "Brain":** The network starts with random "weights" (the numbers in the math). It makes a guess, sees if it's wrong, and then slightly adjusts the weights to try to be more correct next time. This process repeats many times until the network gets good at making predictions.
	
	**Example - Identifying Penguins:**
	
	Imagine you want to teach a computer to tell different types of penguins apart based on their beak length, beak depth, flipper length, and weight.
	
	1. You feed these measurements into the first layer of the network.
	2. Each neuron in the layers does its calculations using its weights.
	3. The final layer gives you a probability for each penguin type (like 80% Gentoo, 15% Adelie, 5% Chinstrap). The computer guesses the type with the highest probability.
	
	**How the Network Learns to Identify Penguins:**
	
	- Initially, the network's guesses are probably bad because its weights are random.
	- You tell the network the _correct_ penguin type for each example you showed it.
	- The network compares its guess to the correct answer and calculates an "error."
	- Then, it goes back through the network and slightly changes the weights in each neuron to reduce this error.
	- It does this over and over with many penguin examples until its guesses become accurate.
	
	**Key takeaway:** Deep learning uses many layers of artificial neurons to learn complex patterns from data by constantly adjusting the "strength" (weights) of the connections between these neurons.
	
