# Binary classification[^1]


Classification, like regression, is a _supervised_ machine learning technique; and therefore follows the same iterative process of training, validating, and evaluating models. Instead of calculating numeric values like a regression model, the algorithms used to train classification models calculate _probability_ values for class assignment and the evaluation metrics used to assess model performance compare the predicted classes to the actual classes.

_Binary classification_ algorithms are used to train a model that predicts one of two possible labels for a single class. Essentially, predicting _**true**_ or _**false**_. In most real scenarios, the data observations used to train and validate the model consist of multiple feature (_**x**_) values and a _**y**_ value that is either **1** or **0**.

## Example - binary classification

To understand how binary classification works, let's look at a simplified example that uses a single feature (_**x**_) to predict whether the label _**y**_ is 1 or 0. In this example, we'll use the blood glucose level of a patient to predict whether or not the patient has diabetes. Here's the data with which we'll train the model:

Expand table

|![Diagram of a syringe.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/blood-glucose.png)|![Diagram of a diabetic and non-diabetic person.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/diabetes.png)|
|---|---|
|**Blood glucose (x)**|**Diabetic? (y)**|
|67|0|
|103|1|
|114|1|
|72|0|
|116|1|
|65|0|

### Training a binary classification model

To train the model, we'll use an algorithm to fit the training data to a function that calculates the _probability_ of the class label being _true_ (in other words, that the patient has diabetes). Probability is measured as a value between 0.0 and 1.0, such that the _total_ probability for _all_ possible classes is 1.0. So for example, if the probability of a patient having diabetes is 0.7, then there's a corresponding probability of 0.3 that the patient isn't diabetic.

There are many algorithms that can be used for binary classification, such as _logistic regression_, which derives a _sigmoid_ (S-shaped) function with values between 0.0 and 1.0, like this:

![Diagram of a logistic function.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/sigmoid-plot.png)

 Note

Despite its name, in machine learning _logistic regression_ is used for classification, not regression. The important point is the _logistic_ nature of the function it produces, which describes an S-shaped curve between a lower and upper value (0.0 and 1.0 when used for binary classification).

The function produced by the algorithm describes the probability of _**y**_ being true (_y_=1) for a given value of _**x**_. Mathematically, you can express the function like this:

_**f(x) = P(y=1 | x)**_

For three of the six observations in the training data, we know that _**y**_ is definitely _true_, so the probability for those observations that _y_=1 is **1.0** and for the other three, we know that _**y**_ is definitely _false_, so the probability that _y_=1 is **0.0**. The S-shaped curve describes the probability distribution so that plotting a value of _**x**_ on the line identifies the corresponding probability that _**y**_ is **1**.

The diagram also includes a horizontal line to indicate the _threshold_ at which a model based on this function will predict _true_ (**1**) or _false_ (**0**). The threshold lies at the mid-point for _**y**_ (_P(y) = 0.5_). For any values at this point or above, the model will predict _true_ (**1**); while for any values below this point it will predict _false_ (**0**). For example, for a patient with a blood glucose level of 90, the function would result in a probability value of 0.9. Since 0.9 is higher than the threshold of 0.5, the model would predict _true_ (**1**) - in other words, the patient is predicted to have diabetes.

### Evaluating a binary classification model

As with regression, when training a binary classification model you hold back a random subset of data with which to validate the trained model. Let's assume we held back the following data to validate our diabetes classifier:

Expand table

|Blood glucose (x)|Diabetic? (y)|
|---|---|
|66|0|
|107|1|
|112|1|
|71|0|
|87|1|
|89|1|

Applying the logistic function we derived previously to the _**x**_ values results in the following plot.

![Diagram of predicted labels on a sigmoid curve.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/classification-predictions.png)

Based on whether the probability calculated by the function is above or below the threshold, the model generates a predicted label of 1 or 0 for each observation. We can then compare the _predicted_ class labels (_**ŷ**_) to the _actual_ class labels (_**y**_), as shown here:

Expand table

|Blood glucose (x)|Actual diabetes diagnosis (y)|Predicted diabetes diagnosis (ŷ)|
|---|---|---|
|66|0|0|
|107|1|1|
|112|1|1|
|71|0|0|
|87|1|0|
|89|1|1|

### Binary classification evaluation metrics

The first step in calculating evaluation metrics for a binary classification model is usually to create a matrix of the number of correct and incorrect predictions for each possible class label:

![Diagram of a confusion matrix.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/binary-confusion-matrix.png)

This visualization is called a _confusion matrix_, and it shows the prediction totals where:

- ŷ=0 and y=0: _True negatives_ (TN)
- ŷ=1 and y=0: _False positives_ (FP)
- ŷ=0 and y=1: _False negatives_ (FN)
- ŷ=1 and y=1: _True positives_ (TP)

The arrangement of the confusion matrix is such that correct (_true_) predictions are shown in a diagonal line from top-left to bottom-right. Often, color-intensity is used to indicate the number of predictions in each cell, so a quick glance at a model that predicts well should reveal a deeply shaded diagonal trend.

#### Accuracy

The simplest metric you can calculate from the confusion matrix is _accuracy_ - the proportion of predictions that the model got right. Accuracy is calculated as:

_**(TN+TP) ÷ (TN+FN+FP+TP)**_

In the case of our diabetes example, the calculation is:

(2+3) ÷ (2+1+0+3)

= 5 ÷ 6

= **0.83**

So for our validation data, the diabetes classification model produced correct predictions 83% of the time.

Accuracy might initially seem like a good metric to evaluate a model, but consider this. Suppose 11% of the population has diabetes. You could create a model that always predicts **0**, and it would achieve an accuracy of 89%, even though it makes no real attempt to differentiate between patients by evaluating their features. What we really need is a deeper understanding of how the model performs at predicting **1** for positive cases and **0** for negative cases.

#### Recall

_Recall_ is a metric that measures the proportion of positive cases that the model identified correctly. In other words, compared to the number of patients who _have_ diabetes, how many did the model _predict_ to have diabetes?

The formula for recall is:

_**TP ÷ (TP+FN)**_

For our diabetes example:

3 ÷ (3+1)

= 3 ÷ 4

= **0.75**

So our model correctly identified 75% of patients who have diabetes as having diabetes.

#### Precision

_Precision_ is a similar metric to recall, but measures the proportion of predicted positive cases where the true label is actually positive. In other words, what proportion of the patients _predicted_ by the model to have diabetes actually _have_ diabetes?

The formula for precision is:

_**TP ÷ (TP+FP)**_

For our diabetes example:

3 ÷ (3+0)

= 3 ÷ 3

= **1.0**

So 100% of the patients predicted by our model to have diabetes do in fact have diabetes.

#### F1-score

_F1-score_ is an overall metric that combined recall and precision. The formula for F1-score is:

_**(2 x Precision x Recall) ÷ (Precision + Recall)**_

For our diabetes example:

(2 x 1.0 x 0.75) ÷ (1.0 + 0.75)

= 1.5 ÷ 1.75

**= 0.86**

#### Area Under the Curve (AUC)[^2]

Another name for recall is the _true positive rate_ (TPR), and there's an equivalent metric called the _false positive rate_ (FPR) that is calculated as **FP÷(FP+TN)**. We already know that the TPR for our model when using a threshold of 0.5 is 0.75, and we can use the formula for FPR to calculate a value of 0÷2 = 0.

Of course, if we were to change the threshold above which the model predicts _true_ (**1**), it would affect the number of positive and negative predictions; and therefore change the TPR and FPR metrics. These metrics are often used to evaluate a model by plotting a _received operator characteristic_ (ROC) curve that compares the TPR and FPR for every possible threshold value between 0.0 and 1.0:

![Diagram of a ROC curve.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/roc-chart.png)

The ROC curve for a perfect model would go straight up the TPR axis on the left and then across the FPR axis at the top. Since the plot area for the curve measures 1x1, the area under this perfect curve would be 1.0 (meaning that the model is correct 100% of the time). In contrast, a diagonal line from the bottom-left to the top-right represents the results that would be achieved by randomly guessing a binary label; producing an area under the curve of 0.5. In other words, given two possible class labels, you could reasonably expect to guess correctly 50% of the time.

In the case of our diabetes model, the curve above is produced, and the **area under the curve** (AUC) metric is 0.875. Since the AUC is higher than 0.5, we can conclude the model performs better at predicting whether or not a patient has diabetes than randomly guessing.
___


[^1]: **Binary Classification: Yes or No Decisions**
	
	- **Concept:**
	    - It's supervised learning where you want to predict one of two outcomes (e.g., "spam" or "not spam," "yes" or "no").
	    - The machine learns to categorize things into two groups.
	    - It calculates the probability of something belonging to a specific category.
	- **How it Works (Simplified):**
	    1. **Data:** You provide examples with features (like blood glucose levels) and labels (like "diabetic" or "not diabetic").
	    2. **Training:** The computer uses an algorithm (like logistic regression) to find a way to separate the two categories. It creates a curve that shows the probability of something being in one category.
	    3. **Prediction:** You give the computer new features (a new blood glucose level), and it calculates the probability of it being in a category. If the probability is above a certain threshold (usually 0.5), it predicts "yes"; otherwise, it predicts "no."
	    4. **Evaluation:** You check how well the model predicted by comparing its predictions to the actual labels.
	**Key Evaluation Metrics for Binary Classification (In Detail):**
1. **Confusion Matrix:**
    
    - This is the foundation. It's a table that summarizes the performance of a classification model.
    - It breaks down predictions into four categories:
        - **True Positives (TP):** The model correctly predicted "yes" when it was actually "yes." (e.g., correctly identified a patient with diabetes).
        - **True Negatives (TN):** The model correctly predicted "no" when it was actually "no." (e.g., correctly identified a patient without diabetes).
        - **False Positives (FP):** The model predicted "yes" when it was actually "no." (e.g., predicted a patient had diabetes when they didn't - a "false alarm").
        - **False Negatives (FN):** The model predicted "no" when it was actually "yes." (e.g., predicted a patient didn't have diabetes when they did - a "missed case").
2. **Accuracy:**
    
    - This is the simplest metric: (TP + TN) / (TP + TN + FP + FN).
    - It tells you the overall percentage of correct predictions.
    - **Problem:** It can be misleading if the classes are imbalanced (e.g., if you're predicting a rare disease, a model that always predicts "no" might have high accuracy, but it's useless).
3. **Recall (Sensitivity or True Positive Rate):**
    
    - This measures how well the model finds all the "yes" cases: TP / (TP + FN).
    - It answers the question: "Of all the actual 'yes' cases, how many did the model catch?"
    - **Why it matters:** In medical diagnoses, recall is crucial. You want to minimize false negatives (missing actual cases).
4. **Precision:**
    
    - This measures how often the model is correct when it predicts "yes": TP / (TP + FP).
    - It answers the question: "Of all the cases the model predicted as 'yes,' how many were actually 'yes'?"
    - **Why it matters:** In spam filtering, precision is important. You want to minimize false positives (marking important emails as spam).
5. **F1-Score:**
    
    - This is a balance between recall and precision: 2 * (Precision * Recall) / (Precision + Recall).
    - It's useful when you want a metric that considers both false positives and false negatives.
    - It gives a harmonic mean of precision and recall.
6. **AUC (Area Under the ROC Curve):**
    
    - ROC (Receiver Operating Characteristic) curve: This plots the true positive rate (recall) against the false positive rate at various threshold settings.
    - AUC: The area under the ROC curve.
    - **Why it matters:**
        - It tells you how well the model can distinguish between the two classes.
        - An AUC of 1.0 is perfect, and 0.5 is no better than random guessing.
        - It is very useful when the cost of false positives and false negatives vary greatly.
    - It shows the models ability to rank results.

**In Simple Terms:**

- Think of it like a test.
    - Accuracy: How many questions did you get right overall?
    - Recall: How many of the actual "correct" answers did you get?
    - Precision: Of the answers you said were "correct," how many were actually correct?
    - F1-Score: A balance of precision and recall.
    - AUC: How well can the test distinguish between those who know the material and those who do not.
	- **Example (Diabetes Prediction):**
	    - You want to predict if someone has diabetes based on their blood glucose level.
	    - You give the computer data:
	        - Glucose level: 120, Diabetic: Yes
	        - Glucose level: 80, Diabetic: No
	    - The computer learns a curve that shows the probability of someone having diabetes based on their glucose level.
	    - If someone's glucose level is 110, the computer calculates the probability and predicts "yes" or "no."
	    - Then we use the evaluation metrics to see how well the model predicted.
	- **In Simple Terms:** Binary classification is like teaching a computer to make "yes" or "no" decisions and then checking how often it gets those decisions right.
	






[^2]: **AUC (Area Under the ROC Curve): A Deeper Dive**
	
	1. **ROC (Receiver Operating Characteristic) Curve:**
	    
	    - Imagine you have a model that assigns a probability (or a score) to each data point, indicating how likely it is to belong to the "positive" class (e.g., "diabetic").  
	        
	    - To make a final "yes" or "no" prediction, you need to set a _threshold_. If the probability is above the threshold, you predict "yes"; otherwise, you predict "no."  
	        
	    - The ROC curve shows how the model's performance changes as you vary this threshold.  
	        
	    - It plots:
	        - **True Positive Rate (TPR) or Recall (Sensitivity):** The proportion of actual positive cases that the model correctly identifies (TP / (TP + FN)).  
	            
	        - **False Positive Rate (FPR):** The proportion of actual negative cases that the model incorrectly identifies as positive (FP / (FP + TN)).  
	            
	    - So, the ROC curve shows the trade-off between TPR and FPR at different threshold values.  
	        
	2. **How the ROC Curve Works:**
	    
	    - If you set a very low threshold, the model will predict "yes" for almost everything, resulting in a high TPR but also a high FPR.  
	        
	    - If you set a very high threshold, the model will predict "yes" only for the most confident cases, resulting in a low FPR but also a low TPR.
	    - The ROC curve connects all the TPR and FPR points you get by varying the threshold.  
	        
	3. **AUC (Area Under the Curve):**
	    
	    - The AUC is the area under the ROC curve.  
	        
	    - It represents the model's ability to distinguish between the positive and negative classes.  
	        
	    - **Interpretation:**
	        - **AUC = 1.0:** The model is perfect. It can perfectly separate the positive and negative cases.  
	            
	        - **AUC = 0.5:** The model is no better than random guessing.  
	            
	        - **AUC > 0.5:** The model is better than random guessing.
	        - The higher the AUC, the better the model's performance.  
	            
	    - AUC is scale invariant. It measures how well predictions are ranked, not their absolute value.  
	        
	    - It's particularly useful when:
	        - You want to compare different models.
	        - You're dealing with imbalanced datasets.
	        - You need to assess the model's overall ability to rank positive cases higher than negative cases.  
	            
	4. **Why AUC is Valuable:**
	    
	    - **Threshold-Independent:** AUC measures the model's performance across all possible thresholds, so you don't have to choose a specific threshold.  
	        
	    - **Robust to Class Imbalance:** Unlike accuracy, AUC is less affected by imbalanced datasets. If you have far more negative cases than positive cases, AUC still provides a reliable measure of performance.  
	        
	    - **Ranking Ability:** AUC focuses on the model's ability to rank positive cases higher than negative cases, which is often more important than just getting the "yes" or "no" predictions right.  
	        
	
	**In Simple Terms:**
	
	- Imagine you're trying to sort a deck of cards into red and black suits.
	- The ROC curve shows how well you can separate the red and black cards as you change your sorting criteria.  
	    
	- The AUC tells you the overall quality of your sorting.
	    
	    A higher AUC means you're better at separating the red and black cards.  
	    
