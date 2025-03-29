# Multiclass classification[^1]

_Multiclass classification_ is used to predict to which of multiple possible classes an observation belongs. As a supervised machine learning technique, it follows the same iterative _train, validate, and evaluate_ process as regression and binary classification in which a subset of the training data is held back to validate the trained model.

## Example - multiclass classification

Multiclass classification algorithms are used to calculate probability values for multiple class labels, enabling a model to predict the _most probable_ class for a given observation.

Let's explore an example in which we have some observations of penguins, in which the flipper length (_**x**_) of each penguin is recorded. For each observation, the data includes the penguin species (_**y**_), which is encoded as follows:

- 0: Adelie
- 1: Gentoo
- 2: Chinstrap

 Note

As with previous examples in this module, a real scenario would include multiple feature (_**x**_) values. We'll use a single feature to keep things simple.

Expand table

|![Diagram of a measuring ruler.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/ruler.png)|![Diagram of three penguins.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/penguins.png)|
|---|---|
|**Flipper length (x)**|**Species (y)**|
|167|0|
|172|0|
|225|2|
|197|1|
|189|1|
|232|2|
|158|0|

### Training a multiclass classification model

To train a multiclass classification model, we need to use an algorithm to fit the training data to a function that calculates a probability value for each possible class. There are two kinds of algorithm you can use to do this:

- One-vs-Rest (OvR) algorithms
- Multinomial algorithms

#### One-vs-Rest (OvR) algorithms[^2]

One-vs-Rest algorithms train a binary classification function for each class, each calculating the probability that the observation is an example of the target class. Each function calculates the probability of the observation being a specific class compared to _any_ other class. For our penguin species classification model, the algorithm would essentially create three binary classification functions:

- _**f0(x) = P(y=0 | x)**_
- _**f1(x) = P(y=1 | x)**_
- _**f2(x) = P(y=2 | x)**_

Each algorithm produces a sigmoid function that calculates a probability value between 0.0 and 1.0. A model trained using this kind of algorithm predicts the class for the function that produces the highest probability output.

#### Multinomial algorithms[^3]

As an alternative approach is to use a multinomial algorithm, which creates a single function that returns a multi-valued output. The output is a _vector_ (an array of values) that contains the _probability distribution_ for all possible classes - with a probability score for each class which when totaled add up to 1.0:

_**f(x) =[P(y=0|x), P(y=1|x), P(y=2|x)]**_

An example of this kind of function is a _softmax_ function, which could produce an output like the following example:

[0.2, 0.3, 0.5]

The elements in the vector represent the probabilities for classes 0, 1, and 2 respectively; so in this case, the class with the highest probability is **2**.

Regardless of which type of algorithm is used, the model uses the resulting function to determine the most probable class for a given set of features (_**x**_) and predicts the corresponding class label (_**y**_).

### Evaluating a multiclass classification model [^4]

You can evaluate a multiclass classifier by calculating binary classification metrics for each individual class. Alternatively, you can calculate aggregate metrics that take all classes into account.

Let's assume that we've validated our multiclass classifier, and obtained the following results:

Expand table

|Flipper length (x)|Actual species (y)|Predicted species (ŷ)|
|---|---|---|
|165|0|0|
|171|0|0|
|205|2|1|
|195|1|1|
|183|1|1|
|221|2|2|
|214|2|2|

The confusion matrix for a multiclass classifier is similar to that of a binary classifier, except that it shows the number of predictions for each combination of _predicted_ (_**ŷ**_) and _actual_ class labels (_**y**_):

![Diagram of a multiclass confusion matrix.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/multiclass-confusion-matrix.png)

From this confusion matrix, we can determine the metrics for each individual class as follows:

Expand table

|Class|TP|TN|FP|FN|Accuracy|Recall|Precision|F1-Score|
|---|---|---|---|---|---|---|---|---|
|**0**|2|5|0|0|1.0|1.0|1.0|1.0|
|**1**|2|4|1|0|0.86|1.0|0.67|0.8|
|**2**|2|4|0|1|0.86|0.67|1.0|0.8|

To calculate the overall accuracy, recall, and precision metrics, you use the total of the _TP_, _TN_, _FP_, and _FN_ metrics:

- **Overall accuracy** = (13+6)÷(13+6+1+1) = **0.90**
- **Overall recall** = 6÷(6+1) = **0.86**
- **Overall precision** = 6÷(6+1) = **0.86**

The overall F1-score is calculated using the overall recall and precision metrics:

- **Overall F1-score** = (2x0.86x0.86)÷(0.86+0.86) = **0.86**
___


[^1]: **Multiclass Classification: Choosing from Many Options**
	
	- **Concept:**
	    - It's supervised learning where you want to predict which of _multiple_ categories something belongs to (e.g., "apple," "banana," or "orange").
	    - The machine learns to categorize things into more than two groups.
	    - It calculates the probability of something belonging to each category.
	- **How it Works (Simplified):**
	    1. **Data:** You provide examples with features (like penguin flipper length) and labels (like penguin species: Adelie, Gentoo, Chinstrap).
	    2. **Training:** The computer uses an algorithm to learn how the features relate to each category. It might use:
	        - **One-vs-Rest (OvR):** It creates a separate binary classification model for each category (e.g., "Is it an Adelie?" "Is it a Gentoo?" "Is it a Chinstrap?").
	        - **Multinomial:** It creates a single model that outputs the probability of each category (e.g., "20% Adelie, 30% Gentoo, 50% Chinstrap").
	    3. **Prediction:** You give the computer new features (a new penguin flipper length), and it calculates the probabilities for each category. It predicts the category with the highest probability.
	    4. **Evaluation:** You check how well the model predicted by comparing its predictions to the actual labels.
	- **Key Evaluation Metrics:**
	    - **Confusion Matrix:** A table that shows how many predictions were correct and incorrect for each category.
	    - **Accuracy:** The overall percentage of correct predictions.
	    - **Recall (for each category):** How well the model finds all the items in that specific category.
	    - **Precision (for each category):** How often the model is correct when it predicts that specific category.
	    - **F1-Score (for each category):** A balance between recall and precision for that category.
	    - **Overall Metrics:** You can also calculate overall accuracy, recall, precision, and F1-score by combining the results from all categories.
	- **Example (Penguin Species):**
	    - You want to predict the species of a penguin based on its flipper length.
	    - You give the computer data:
	        - Flipper length: 200 mm, Species: Gentoo
	        - Flipper length: 170 mm, Species: Adelie
	        - Flipper length: 220 mm, Species: Chinstrap
	    - The computer learns how flipper length relates to each species.
	    - If a penguin's flipper length is 210 mm, the computer predicts the most likely species.
	    - Then we use the evaluation metrics to see how well the model predicted the species.
	- **In Simple Terms:**
	    - Multiclass classification is like teaching a computer to sort things into many different boxes and then checking how often it puts things in the right boxes.
	    -

[^2]: **OvR (One-vs-Rest):**
	
	- **Think:** "One at a time."
	- **How:** Makes a separate "yes/no" test for each category.
	- **Example:** For apples, bananas, and oranges, it asks: "Is it an apple?" then "Is it a banana?" then "Is it an orange?"
	- **Result:** Chooses the category with the highest "yes" score.

[^3]: **Multinomial:**
	
	- **Think:** "All at once."
	- **How:** Makes one test that gives a score for _each_ category.
	- **Example:** For apples, bananas, and oranges, it gives scores like "30% apple, 50% banana, 20% orange."
	- **Result:** Chooses the category with the highest score.

[^4]: - **Confusion Matrix:**
	    
	    - **Think:** "Where did I get it right or wrong, for each category?"
	    - **What:** A table showing how many times each category was predicted correctly or incorrectly.
	- **Accuracy:**
	    
	    - **Think:** "How often was I right, overall?"
	    - **What:** The percentage of correct guesses.
	- **Recall (per category):**
	    
	    - **Think:** "Of all the things that _were_ this category, how many did I find?"
	    - **What:** How good you are at finding _all_ of a specific category.
	- **Precision (per category):**
	    
	    - **Think:** "When I said it was this category, how often was I correct?"
	    - **What:** How good you are at being _right_ when you predict a specific category.
	- **F1-Score (per category):**
	    
	    - **Think:** "A balance between finding everything and being right."
	    - **What:** A single score that combines recall and precision.
	- **Overall Metrics (Macro/Micro):**
	    
	    - **Think:** "How did I do, across all categories?"
	    - **What:** A way to combine the metrics from each category into one overall score.
	        - **Macro:** Every category counts equally.
	        - **Micro:** Bigger categories count more.
