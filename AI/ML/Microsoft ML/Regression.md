# REGRESSION[^1]

Regression models are trained to predict numeric label values based on training data that includes both features and known labels. The process for training a regression model (or indeed, any supervised machine learning model) involves multiple iterations in which you use an appropriate algorithm (usually with some parameterized settings) to train a model, evaluate the model's predictive performance, and refine the model by repeating the training process with different algorithms and parameters until you achieve an acceptable level of predictive accuracy.

![Diagram showing the process of training an evaluating a supervised model.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/supervised-training.png)

The diagram shows four key elements of the training process for supervised machine learning models:

1. Split the training data (randomly) to create a dataset with which to train the model while holding back a subset of the data that you'll use to validate the trained model.
2. Use an algorithm to fit the training data to a model. In the case of a regression model, use a regression algorithm such as _linear regression_.
3. Use the validation data you held back to test the model by predicting labels for the features.
4. Compare the known _actual_ labels in the validation dataset to the labels that the model predicted. Then aggregate the differences between the _predicted_ and _actual_ label values to calculate a metric that indicates how accurately the model predicted for the validation data.

After each train, validate, and evaluate iteration, you can repeat the process with different algorithms and parameters until an acceptable evaluation metric is achieved.

## Example - regression

Let's explore regression with a simplified example in which we'll train a model to predict a numeric label (_**y**_) based on a single feature value (_**x**_). Most real scenarios involve multiple feature values, which adds some complexity; but the principle is the same.

For our example, let's stick with the ice cream sales scenario we discussed previously. For our feature, we'll consider the _temperature_ (let's assume the value is the maximum temperature on a given day), and the label we want to train a model to predict is the number of ice creams sold that day. We'll start with some historic data that includes records of daily temperatures (_**x**_) and ice cream sales (_**y**_):

Expand table

|![Diagram of a thermometer.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/temperature.png)|![Diagram of a ice creams.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/ice-creams.png)|
|---|---|
|**Temperature (x)**|**Ice cream sales (y)**|
|51|1|
|52|0|
|67|14|
|65|14|
|70|23|
|69|20|
|72|23|
|75|26|
|73|22|
|81|30|
|78|26|
|83|36|

### Training a regression model

We'll start by splitting the data and using a subset of it to train a model. Here's the training dataset:

Expand table

|Temperature (x)|Ice cream sales (y)|
|---|---|
|51|1|
|65|14|
|69|20|
|72|23|
|75|26|
|81|30|

To get an insight of how these _**x**_ and _**y**_ values might relate to one another, we can plot them as coordinates along two axes, like this:

![Diagram of a scatter plot showing x and y.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/scatter-plot.png)

Now we're ready to apply an algorithm to our training data and fit it to a function that applies an operation to _**x**_ to calculate _**y**_. One such algorithm is _linear regression_, which works by deriving a function that produces a straight line through the intersections of the _**x**_ and _**y**_ values while minimizing the average distance between the line and the plotted points, like this:

![Diagram of the scatter plot with a regression line added.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/regression-line.png)

The line is a visual representation of the function in which the slope of the line describes how to calculate the value of _**y**_ for a given value of _**x**_. The line intercepts the _**x**_ axis at 50, so when _**x**_ is 50, _**y**_ is 0. As you can see from the axis markers in the plot, the line slopes so that every increase of 5 along the _**x**_ axis results in an increase of 5 up the _**y**_ axis; so when _**x**_ is 55, _**y**_ is 5; when _**x**_ is 60, _**y**_ is 10, and so on. To calculate a value of _**y**_ for a given value of _**x**_, the function simply subtracts 50; in other words, the function can be expressed like this:

**_f_(x) = x-50**

You can use this function to predict the number of ice creams sold on a day with any given temperature. For example, suppose the weather forecast tells us that tomorrow it will be 77 degrees. We can apply our model to calculate _77-50_ and predict that we'll sell 27 ice creams tomorrow.

But just how accurate is our model?

### Evaluating a regression model

To validate the model and evaluate how well it predicts, we held back some data for which we know the label (_**y**_) value. Here's the data we held back:

Expand table

|Temperature (x)|Ice cream sales (y)|
|---|---|
|52|0|
|67|14|
|70|23|
|73|22|
|78|26|
|83|36|

We can use the model to predict the label for each of the observations in this dataset based on the feature (_**x**_) value; and then compare the predicted label (_**ŷ**_) to the known actual label value (_**y**_).

Using the model we trained earlier, which encapsulates the function **_f_(x) = x-50**, results in the following predictions:

Expand table

|Temperature (x)|Actual sales (y)|Predicted sales (ŷ)|
|---|---|---|
|52|0|2|
|67|14|17|
|70|23|20|
|73|22|23|
|78|26|28|
|83|36|33|

We can plot both the _predicted_ and _actual_ labels against the feature values like this:

![Diagram of a scatter plot showing predicted and actual values.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/regression-variance.png)

The predicted labels are calculated by the model so they're on the function line, but there's some variance between the _**ŷ**_ values calculated by the function and the actual _**y**_ values from the validation dataset; which is indicated on the plot as a line between the _**ŷ**_ and _**y**_ values that shows how far off the prediction was from the actual value.

### Regression evaluation metrics

Based on the differences between the predicted and actual values, you can calculate some common metrics that are used to evaluate a regression model.

#### Mean Absolute Error (MAE)

The variance in this example indicates by how many ice creams each prediction was wrong. It doesn't matter if the prediction was _over_ or _under_ the actual value (so for example, -3 and +3 both indicate a variance of 3). This metric is known as the _absolute error_ for each prediction, and can be summarized for the whole validation set as the **mean absolute error** (MAE).

In the ice cream example, the mean (average) of the absolute errors (2, 3, 3, 1, 2, and 3) is **2.33**.

#### Mean Squared Error (MSE)

The mean absolute error metric takes all discrepancies between predicted and actual labels into account equally. However, it may be more desirable to have a model that is consistently wrong by a small amount than one that makes fewer, but larger errors. One way to produce a metric that "amplifies" larger errors by _squaring_ the individual errors and calculating the mean of the squared values. This metric is known as the **mean squared error** (MSE).

In our ice cream example, the mean of the squared absolute values (which are 4, 9, 9, 1, 4, and 9) is **6**.

#### Root Mean Squared Error (RMSE)

The mean squared error helps take the magnitude of errors into account, but because it _squares_ the error values, the resulting metric no longer represents the quantity measured by the label. In other words, we can say that the MSE of our model is 6, but that doesn't measure its accuracy in terms of the number of ice creams that were mispredicted; 6 is just a numeric score that indicates the level of error in the validation predictions.

If we want to measure the error in terms of the number of ice creams, we need to calculate the _square root_ of the MSE; which produces a metric called, unsurprisingly, **Root Mean Squared Error**. In this case √6, which is **2.45** (ice creams).

#### Coefficient of determination (R2)

All of the metrics so far compare the discrepancy between the predicted and actual values in order to evaluate the model. However, in reality, there's some natural random variance in the daily sales of ice cream that the model takes into account. In a linear regression model, the training algorithm fits a straight line that minimizes the mean variance between the function and the known label values. The **coefficient of determination** (more commonly referred to as **R2** or **R-Squared**) is a metric that measures the proportion of variance in the validation results that can be explained by the model, as opposed to some anomalous aspect of the validation data (for example, a day with a highly unusual number of ice creams sales because of a local festival).

The calculation for R2 is more complex than for the previous metrics. It compares the sum of squared differences between predicted and actual labels with the sum of squared differences between the actual label values and the mean of actual label values, like this:

_**R2 = 1- ∑(y-ŷ)2 ÷ ∑(y-ȳ)2**_

Don't worry too much if that looks complicated; most machine learning tools can calculate the metric for you. The important point is that the result is a value between 0 and 1 that describes the proportion of variance explained by the model. In simple terms, the closer to 1 this value is, the better the model is fitting the validation data. In the case of the ice cream regression model, the R2 calculated from the validation data is **0.95**.

## Iterative training

The metrics described above are commonly used to evaluate a regression model. In most real-world scenarios, a data scientist will use an iterative process to repeatedly train and evaluate a model, varying:

- Feature selection and preparation (choosing which features to include in the model, and calculations applied to them to help ensure a better fit).
- Algorithm selection (We explored linear regression in the previous example, but there are many other regression algorithms)
- Algorithm parameters (numeric settings to control algorithm behavior, more accurately called _hyperparameters_ to differentiate them from the _**x**_ and _**y**_ parameters).

After multiple iterations, the model that results in the best evaluation metric that's acceptable for the specific scenario is selected.
___


[^1]: **Regression: Predicting Numbers with a Line (or Curve)**
	
	- **Concept:**
	    - Regression is a type of supervised learning where you want to predict a _number_.
	    - It finds a relationship between input features (like temperature) and a numerical output (like ice cream sales).
	    - It's like drawing a line (or a curve) that best fits your data points.
	- **How it Works (Simplified):**
	    1. **Data:** You give the computer a bunch of examples with inputs (x) and outputs (y). In our example x is temperature, and y is ice cream sales.
	    2. **Training:** The computer uses an algorithm (like linear regression) to find the best-fitting line through the data.
	    3. **Prediction:** You give the computer a new input (a new temperature), and it uses the line to predict the output (how many ice creams will be sold).
	    4. **Evaluation:** You check how accurate the predictions are by comparing them to actual values.
	- **Key Evaluation Metrics (How to Know if Your Line is Good):**
	    - **Mean Absolute Error (MAE):** The average difference between predictions and actual values.
	    - **Mean Squared Error (MSE):** The average of the squared differences (penalizes big errors more).
	    - **Root Mean Squared Error (RMSE):** The square root of MSE (gives you the error in the same units as your output).
	    - **R-Squared (R2):** How well the line fits the data (closer to 1 is better).
	- **Example (Ice Cream Sales):**
	    - You want to predict ice cream sales based on temperature.
	    - You give the computer data:
	        - Temperature (x): 70 degrees, Sales (y): 20 ice creams
	        - Temperature (x): 80 degrees, sales (y): 30 ice creams.
	    - The computer finds a line that shows how sales increase with temperature.
	    - If the temperature is 75 degrees, the computer uses the line to predict the sales.
	    - Then you compare the predicted sales to the actual sales to see how well the model performed.
	- **Iterative Training:** To get the best results, you try different algorithms, different ways of preparing the data, and different settings, until you find a model with acceptable accuracy.
	- **In Simple Terms:** Regression is like drawing a line on a graph to predict numbers. You check how good the line is by seeing how close its predictions are to the real numbers.
	
