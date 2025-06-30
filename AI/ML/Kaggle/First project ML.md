steps for my first ML project

# Input the necessary libraries
pandas
scikitliearn
numpy

# import the file
put it in a path variable
then use pd.read_csv()

# EDA (explaratory data analysis)
 checking the columns of the dataset with df.columns

# making the predictive features
put it inside a variable like this
`feature_names = home_data[['LotArea', 'YearBuilt', '1stFlrSF', '2ndFlrSF', 'FullBath', 'BedroomAbvGr', 'TotRmsAbvGrd']]
`
and put it in the variable X (standard)

# reviewing of data
description of data = .describe()
first 5 rows of data = .head()

# specifying the model
import from scikit learn and put it inside a variable, when calling the model you put a random_state 

# training the model
use the .fit(X, y) 
X - the features of the dataset (the factors the ML needs to predict an outcome)
y - the one we are trying to predict

# predictions 
call the model then use .predict()

# splitting the data for validation data
use the train_test_split function from scikitlearn
it looks like this:
`train_X, val_X, train_y, val_y = train_test_split(X, y, random_state=1)`

differences of data used in ML:
- **Training Data:** This is the **textbook and homework**. The student studies this material over and over to learn the concepts. This is the bulk of their learning.
    
- **Validation Data:** These are the **practice exams**. The student takes these _during_ the study period to check their progress and to "tune" their study habits (e.g., "I'm weak on this chapter, I'll review it more"). You can use many practice exams to decide when the student is ready.
    
- **Test Data:** This is the **final, official exam**. The student only sees it once at the very end. Their score on this test is the final, honest measure of how well they actually learned the material. You can't let them study from it.

training data vs validation data
- **Training predictions are high because the model has already seen the answers.** It's a measure of how well the model **memorized** the past.
    
- **Validation predictions are lower (and more realistic) because the model is seeing new data for the first time.** It's a measure of how well the model can **generalize** its knowledge to predict the future.
# Calculating the error
MAE - If your model predicts house prices, the Mean Absolute Error tells you, "On average, my predictions are off by $X".
import the mean_absolute_error in sklearn

# Calculating the accuracy
use .score() function

# overfitting and underfitting
overfitting - model is excellent in training data and a noob at new data
underfitting - noob in all aspects

tldr: 
- **Overfitting:** The model is a student who **memorized the textbook** perfectly, including the typos. It gets 100% on the homework (training data) but fails the final exam (new data) because it didn't learn the actual concepts.
    
- **Underfitting:** The model is a student who **didn't study at all**. It fails the homework (training data) and also fails the final exam (new data). The model is too simple and didn't learn anything useful.

# decision tree model
A decision tree is a flowchart of yes/no questions for your data. It keeps splitting the data into smaller groups to make a final prediction.
Here are its parts:
- **Root Node:** The very first question at the top (e.g., "Is the house bigger than 1500 sq ft?").
- **Decision Node:** Any question in the middle that splits the data further.
- **Leaf Node:** The final answer at the end of a branch (e.g., "Predict price: $300,000").
- **Branches:** The "yes" or "no" arrows connecting the questions.

# editing the leaf nodes
`from sklearn.metrics import mean_absolute_error
from sklearn.tree import DecisionTreeRegressor

def get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y):
    model = DecisionTreeRegressor(max_leaf_nodes=max_leaf_nodes, random_state=0)
    model.fit(train_X, train_y)
    preds_val = model.predict(val_X)
    mae = mean_absolute_error(val_y, preds_val)
    return(mae)`
## and using a for loop to check with different numbers of leaves

`for max_leaf_nodes in [5, 50, 500, 5000]:
    my_mae = get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y)
    print("Max leaf nodes: %d  \t\t Mean Absolute Error:  %d" %(max_leaf_nodes, my_mae))`

# Tuning a model via leaf nodes

```
best_tree_size = 100
final_model = DecisionTreeRegressor(max_leaf_nodes = best_tree_size)
final_model.fit(X, y)
```

# [[Random Forest]]
