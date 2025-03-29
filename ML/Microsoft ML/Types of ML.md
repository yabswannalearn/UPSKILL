# Types of machine learning[^1]


There are multiple types of machine learning, and you must apply the appropriate type depending on what you're trying to predict. A breakdown of common types of machine learning is shown in the following diagram.

![Diagram showing supervised machine learning (regression and classification) and unsupervised machine learning (clustering).](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/machine-learning-types.png)

## Supervised machine learning

_Supervised_ machine learning is a general term for machine learning algorithms in which the training data includes both _feature_ values and known _label_ values. Supervised machine learning is used to train models by determining a relationship between the features and labels in past observations, so that unknown labels can be predicted for features in future cases.

### Regression

_Regression_ is a form of supervised machine learning in which the label predicted by the model is a numeric value. For example:

- The number of ice creams sold on a given day, based on the temperature, rainfall, and windspeed.
- The selling price of a property based on its size in square feet, the number of bedrooms it contains, and socio-economic metrics for its location.
- The fuel efficiency (in miles-per-gallon) of a car based on its engine size, weight, width, height, and length.

### Classification

_Classification_ is a form of supervised machine learning in which the label represents a categorization, or _class_. There are two common classification scenarios.

#### Binary classification

In _binary classification_, the label determines whether the observed item _is_ (or _isn't_) an instance of a specific class. Or put another way, binary classification models predict one of two mutually exclusive outcomes. For example:

- Whether a patient is at risk for diabetes based on clinical metrics like weight, age, blood glucose level, and so on.
- Whether a bank customer will default on a loan based on income, credit history, age, and other factors.
- Whether a mailing list customer will respond positively to a marketing offer based on demographic attributes and past purchases.

In all of these examples, the model predicts a binary _true_/_false_ or _positive/negative_ prediction for a single possible class.

#### Multiclass classification

_Multiclass classification_ extends binary classification to predict a label that represents one of multiple possible classes. For example,

- The species of a penguin (_Adelie_, _Gentoo_, or _Chinstrap_) based on its physical measurements.
- The genre of a movie (_comedy_, _horror_, _romance_, _adventure_, or _science fiction_) based on its cast, director, and budget.

In most scenarios that involve a known set of multiple classes, multiclass classification is used to predict mutually exclusive labels. For example, a penguin can't be both a _Gentoo_ and an _Adelie_. However, there are also some algorithms that you can use to train _multilabel_ classification models, in which there may be more than one valid label for a single observation. For example, a movie could potentially be categorized as both _science fiction_ and _comedy_.

## Unsupervised machine learning

_Unsupervised_ machine learning involves training models using data that consists only of _feature_ values without any known labels. Unsupervised machine learning algorithms determine relationships between the features of the observations in the training data.

### Clustering

The most common form of unsupervised machine learning is _clustering_. A clustering algorithm identifies similarities between observations based on their features, and groups them into discrete clusters. For example:

- Group similar flowers based on their size, number of leaves, and number of petals.
- Identify groups of similar customers based on demographic attributes and purchasing behavior.

In some ways, clustering is similar to multiclass classification; in that it categorizes observations into discrete groups. The difference is that when using classification, you already know the classes to which the observations in the training data belong; so the algorithm works by determining the relationship between the features and the known classification label. In clustering, there's no previously known cluster label and the algorithm groups the data observations based purely on similarity of features.

In some cases, clustering is used to determine the set of classes that exist before training a classification model. For example, you might use clustering to segment your customers into groups, and then analyze those groups to identify and categorize different classes of customer (_high value - low volume_, _frequent small purchaser_, and so on). You could then use your categorizations to label the observations in your clustering results and use the labeled data to train a classification model that predicts to which customer category a new customer might belong.












































___

[^1]: **1. Supervised Learning: Learning with Answers**
	
	- **Concept:** Think of it like studying with a textbook that has all the answers. The machine learns from examples where it knows the "right" answer.
	- **Types:**
	    - **Regression (Predicting Numbers):**
	        - **Example:** Predicting the price of a house based on its size. You give the computer examples of houses with their sizes and prices, and it learns the relationship. Then, you give it the size of a new house, and it predicts the price.
	    - **Classification (Predicting Categories):**
	        - **Binary Classification (Yes/No):**
	            - **Example:** Deciding if an email is spam or not spam. You give the computer examples of emails labeled "spam" or "not spam," and it learns to tell the difference.
	        - **Multiclass Classification (Multiple Categories):**
	            - **Example:** Identifying the type of fruit in a picture (apple, banana, orange). You give the computer pictures of fruits labeled with their names, and it learns to recognize them.
	
	**2. Unsupervised Learning: Learning Without Answers**
	
	- **Concept:** Think of it like exploring a new place without a map. The machine looks for patterns and groups things together on its own.
	- **Clustering (Grouping Similar Things):**
	    - **Example:** Imagine you have a bunch of photos of different animals, but you don't know their names. The computer looks at the pictures and groups them based on how similar they look. It might create groups like "animals with fur," "animals with feathers," and "animals with scales" without you telling it what those groups are.
	
	**In a Nutshell:**
	
	- **Supervised:** You teach the computer with examples that have "answers."
	- **Unsupervised:** The computer finds patterns on its own, without "answers."
	