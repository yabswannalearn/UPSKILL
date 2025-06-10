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

[[Classification]] [[UPSKILL/AI/ML/Microsoft ML/Binary Classification]] [[UPSKILL/AI/ML/Microsoft ML/Multiclass classification]]
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

Conversational AI - technology that can participate in conversations with humans
Responsible AI - focuses on ethical, transparent, accountable use of AI technologies
- Fairness -  should treat all people fairly
- Reliability and Safety - should perform reliably and safely
- Privacy and Security - should be secure and respect privacy
- Inclusiveness - should empower everyone and engage people
- Transparency - should be understandable
- Accountability - people should be accountable for AI systems

Azure Cognitive Services - a comprehensive family of AI services
	- Decision
		- anomaly detector - identify potential problems early on
		- content moderator - detect potentially offensive or unwanted content
		- personaliser - create rich, personalised experiences for every user
	- Language
		- language understanding - build natural language understanding into apps, bots and IoT devices
		- QnA maker - create a conversational question and answer layer over your data
		- text analytics - detect sentiment, key phrases and named entities
		- translator - detect and translate more than 90 supported languages
	- Speech
		- speech to text - transcribe audible speech into readable, searchable text
		- text to speech - convert text to lifelike speech for more natural interfaces
		- speech translation
		- speaker recognition
	- Vision
		- Computer vision
		- Custom vision
		- Face
API
![[Pasted image 20250604193549.png]]

Knowledge Mining - discipling in AI that uses a combination of intelligent services to quickly learn from vast amounts of information
![[Pasted image 20250604193731.png]]
![[Pasted image 20250604193801.png]]
![[Pasted image 20250604193827.png]]
![[Pasted image 20250604193907.png]]

Azure Face service - provides AI algorithms that detect, recognize and analyze human faces in images
- 27 pre defined face landmarks
- can check accessories
- age
- blur
- emotion
- exposure
- facial hair
- gender
- glasses
- hair
- head pose
- make up
- mask
- noise
- occlusion - blocking or not
- smile

Speech and translate service - translation service
- 90 languages and dialects
- even klingon
- it uses neural machine translation
- custom translator - allows you to extend the service for translation based on your business and domain use

Azure Speech service - speech synthesis service stt, tts, and speech translation

Text Analytics
![[Pasted image 20250606235452.png]]
![[Pasted image 20250606235755.png]]

optical character recognition (OCR) - extracting printed or handwritten text into a digital and editable format
- photos of street signs
- products
- documents
- invoices
- bills
- financial reports
- articles

OCR api and Read api
![[Pasted image 20250607000020.png]]
performed by computer vision SDK

Azure Form Recognizer - specialize OCR service that translates printed text into a digital and editable content and preserves that structure and relationship of form like data
- custom models - allows you to extract text, key/value pairs, selection marks and table data from forms
	- unsupervised learning
	- supervised learning

LUIS - language understanding - no code ml service to build natural language into apps, bots and IOT service
NLU - natural language understanding - the ability to transform a linguistic statement to a representation that enables you to understand your users naturally
![[Pasted image 20250607001412.png]]
![[Pasted image 20250607001436.png]]

QnAMaker - cloud based NLP service that allows you to create natural conversational layer

Azure Bot Service - intelligent, serverless bot service that scales on demand. Used for creating publishing and managing bots