AI
Artificial Intelligence - machines that perform jobs that mimic human behavior
Machine Learning - Machines that get better at a task without explicit programming
Deep Learning - Machines that have an artificial neural network inspired by the human brain to solve complex problems
Data Scientist - a person with mutli disciplinary skills in math, statistics, predictive modeling, machine learning to make future predictions

KEY ELEMENTS according to microsoft/azure
machine learning - the foundation of an AI system, learn and predict like a human
anomaly detection - detect outliers or things out of place like a human
computer vision - be able to see like a human
natural language processing - be able to process human languages with context
conversational AI - be able to hold a conversation with a human

DATASET
dataset - logical groupings of units of data that are closely related and share the same data structure
MNIST database - handwritten digits used to test classification
Common Object In Context (COCO) dataset - a dataset which contains many common imagaes using a JSON file that identify objects or segments within an image
![[Pasted image 20250603135601.png]]features
:![[Pasted image 20250603135615.png]]

ML
data labeling - process of identifying raw data and adding one or more meaningful and informative labels to provide context
 - in supervised learning a data will be labeled by a human
- in unsupervised learning a machine will be labeled by a human
ground truth - a properly labeled dataset that you use as the objective standard to train and asses a given model
supervised learning - data has been labeled for training
- task driven - make a prediction
- [[Classification]], [[UPSKILL/AI/ML/Microsoft ML/Regression|Regression]]
unsupervised learning - data has not been labeled, the ML model needs to its own labeling
- data drive - recognize a structure or a pattern
- [[UPSKILL/AI/ML/Microsoft ML/Clustering|Clustering]], [[Association]], [[Dimensionality Reduction]]
reinforcement learning - there is no data, there is an environment and an ML model that generates data any many attempt to reach a goal
- decisions driven - game AI, learning tasks, robot navigation

NEURAL NETWORK
neural network - a neuron/node represents an algorithm 
![[Pasted image 20250603140417.png]]
[[UPSKILL/AI/ML/Microsoft ML/Deep Learning|Deep Learning]] - a neural network that has 3 or more hidden layers
feed forward - a neural network where connections between nodes do not form a cycle
backpropagation - moves backwards through the neural network adjusting weights to improve outcome on next iteration. this is how neural net learns
loss (how bad the network performed)
activation functions - an algorithm applied to a hidden layer node that affects connected output
dense - when the next layer increases the amounts of nodes
sparse - when the next layer decreases the amount of nodes

GPU
GPU - designed to quickly render high resolution images and video concurrently
- can perform high parallel operations on multiple sets of data, and so they are commonly used for non graphical tasks such as machine learning and scientific computation

CUDA (Compute Unified Device Architecture)
NVIDIA - company that manufactures GPU
CUDA deep neural network library (cuDNN) - library from nvidia for deep learning

ML pipeline
![[Pasted image 20250603141550.png]]

Forecast vs Prediction
Forecast - makes a future prediction with relevant data
- not guessing
Prediction - makes a future prediction without relevant data 
- guessing

performance /  [[Evaluating]]
classification metrics 
- accuracy
- precision
- recall
- f1-score
- ROC
- AUC
regression metrics
- MSE
- RMSE
- MAE
ranking metrics
- MRR
- DCG
- NDCG
statistical metrics
- correlation
computer vision
- PSNR
- SSIM
- IoU
nlp metrics
- perplexity
- BLEU
- METEOR
- ROUGE
deep learning
- inception
- frechet inception distance
internal evaluation - metrics used to evaluate the internals of the ML model
- accuracy
- f1 score
- precision
- recall
external evaluation - metrics used to evaluate the final prediction of the ML model

Jupyter Notebooks - a web based application for authoring documents that combine live code, narrative text, equations, visualizations
JupyterLab - IDE for jupyter notebooks

[[UPSKILL/AI/ML/Microsoft ML/Regression|Regression]]/[[UPSKILL/AI/ML/Datacamp/Supervised Learning/Regression|Regression]] 
![[Pasted image 20250603144228.png]]

[[Classification]] [[Binary Classification]] [[Multiclass classification]]
![[Pasted image 20250603153247.png]]

[[UPSKILL/AI/ML/Microsoft ML/Clustering|Clustering]]/[[UPSKILL/AI/ML/Datacamp/Unsupervised Learning/Clustering|Clustering]]
![[Pasted image 20250603154715.png]]

confusion matrix - a table to visualize the model predictions (predicted) vs ground truth labels (actual), also known as error matrix
![[Pasted image 20250603154915.png]]

[[Anomaly Detection]]
- anomaly - an abnormal thing; marked deviation from the norm or a standard; outlier
- anomaly detection - is the process of finding outliers within a dataset
	- use case for anomaly detection:
		- data cleaning
		- intrusion detection
		- fraud detection
		- systems health monitoring
		- event detection in sensor networks
		- ecosystem disturbances
		- detection of critical and cascading flaws
using machine learning for anomaly detection is more efficient and accurate

[[Computer Vision]]  - using machine learning neural networks to gain high level understanding from digital images or video
- computer vision algorithms
	- convlotuinal neural network (CNN) - image and video recognition
	- recurrent neural network (RNN) - handwriting recognition or speech recognition
- types of computer vision
	- image classification - look at an image or video and classify the (places it in a category)
	- object detection - identify objects within an image or video and apply labels and location boundaries
	- semantic segmentation - identify segments or objects by drawing pixel mask (great for objects in movement)
	- image analysis - analyze an image or video to apply descriptive and context labels
	- optical character recognition (OCR) - find text in images or videos and extract them into digital text for editing
	- facial detection - detect faces in a photo or video, draw location boundary, label their expression
![[Pasted image 20250603160148.png]]

[[UPSKILL/AI/ML/Datacamp/Large Language Models/Natural Language Processing|Natural Language Processing]]/[[UPSKILL/AI/ML/Datacamp/Deep Learning/Natural Language Processing|Natural Language Processing]] - machine learning can understand the context of a corpus (a body of related text)
![[Pasted image 20250603164033.png]]
![[Pasted image 20250603164117.png]]