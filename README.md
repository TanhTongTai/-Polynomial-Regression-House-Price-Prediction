# Polynomial Regression House Price Prediction

This project is a hands-on example of using polynomial regression to predict house prices from real estate data. The idea is simple: if we know a house’s features such as area, number of bedrooms, bathrooms, parking, and other property details, can we estimate its selling price?

The notebook walks through the full process from loading the dataset to training the model and evaluating how well it predicts prices. It is a practical machine learning project that shows how a model can learn patterns in data and use them to make predictions.

## Why this project matters

House prices do not usually change in a completely straight line. For example, adding 100 square feet to a small apartment may not increase the value the same way it would for a larger house. In the same way, an extra bedroom or a parking space may matter more in some homes than in others.

This is where polynomial regression becomes useful. Instead of assuming that the relationship between features and price is purely linear, the model can capture more complex patterns and curves. That makes it a better choice for situations where the relationship between variables is not simple.

## Project goal

The goal of this project is to build a model that can estimate house prices based on property features and to check whether polynomial regression is effective for this task.

The project is designed to:

- explore the dataset and understand what information it contains,
- clean and prepare the data for modeling,
- transform the features to account for non-linear relationships,
- train a regression model,
- evaluate the model’s performance,
- and interpret the results in a meaningful way.

## Dataset

The dataset contains information about different houses and their characteristics. It includes both numerical and categorical features, which means the data has to be prepared carefully before being used in a machine learning model.

Some of the main features in the dataset are:

- price
- area
- bedrooms
- bathrooms
- stories
- mainroad
- guestroom
- basement
- hotwaterheating
- airconditioning
- parking
- prefarea
- furnishingstatus

The target variable is the house price. The model learns from these features and tries to estimate the price of a house based on the values of those attributes.

## Step-by-step workflow

### 1. Loading the dataset

The first step is to import the dataset into a pandas DataFrame. This gives us a structured table where each row represents a house and each column represents a feature.

At this stage, we inspect the dataset to confirm that the data was imported correctly and understand the format of the values.

### 2. Exploring the data

Once the data is loaded, we look at the shape of the dataset, the column names, and the types of values in each column. This helps us understand what we are working with before building the model.

We also check for missing values, unusual entries, and inconsistencies. If the dataset has any problems, they need to be addressed before training a model.

### 3. Cleaning and understanding the features

Some columns in the dataset are categorical, meaning they contain labels such as “yes/no” or “furnished/unfurnished,” instead of numeric values. Machine learning models usually work better with numeric inputs, so these values need to be converted into numbers.

This step is important because the model cannot directly learn from text labels. A category like “furnished” has to be encoded into a numeric representation so that it can be processed mathematically.

### 4. Preparing the data for modeling

Before training the model, we separate the target variable from the input features. In this case, the target is the house price, while the rest of the columns are used as predictors.

This separation is essential because the model is trained to learn how the input features relate to the target variable.

### 5. Applying polynomial transformation

This is the key part of the project. Instead of using the original features only, we generate polynomial features. This means we create higher-degree terms such as squared and cubic forms of the variables.

For example, a feature like area might be transformed into area² or area³. This allows the model to learn more complex patterns. In real estate, the effect of size on price is rarely perfectly linear, so this transformation helps the model capture that nonlinearity.

Polynomial regression is useful when the relationship between independent variables and the target is curved rather than straight.

### 6. Splitting the dataset

After preparing the data, we split it into training and testing sets. The training set is used to teach the model, while the testing set is used to check how well the model performs on unseen data.

This is important because a model that only performs well on the data it was trained on may not generalize to new examples. The train-test split helps us estimate real-world performance.

### 7. Training the regression model

Once the data is ready, the model is trained on the transformed feature set. The goal is for the model to learn a relationship between the input features and the house price.

During training, the model tries to minimize the difference between the predicted price and the actual price in the training data. Over time, it adjusts its internal parameters to improve the prediction accuracy.

### 8. Evaluating the model

After training, the model is tested on the test set. We use evaluation metrics to understand how close the predictions are to the actual prices.

The most common metrics in this project are:

- R-squared (R²): shows how much of the variation in house price is explained by the model.
- Mean Squared Error (MSE): measures the average squared difference between predicted and actual values.
- Root Mean Squared Error (RMSE): gives an error value in the same units as the target variable, which makes it easier to interpret.

These metrics help answer a very important question: How reliable are the predictions?

### 9. Interpreting the results

The final step is to look at whether the model performed well and whether the polynomial transformation improved the result.

If the model predicts prices close to actual values, it means that the learned relationship between the features and the house price is meaningful. If the model performs poorly, it may suggest that more feature engineering, different transformations, or a different model may be needed.

## Why polynomial regression is a good choice here

A simple linear model assumes that price changes at a constant rate as each feature changes. In real life, that is not always true. The value of a house may rise quickly when the property becomes larger, but the increase may not be linear across all ranges.

For example:

- a larger house may add more value than a small increase in square footage,
- a second bathroom may matter more in some homes than in others,
- outdoor features, parking, or furnished status may affect price in a more complex way.

Polynomial regression gives the model more flexibility so it can capture these patterns better than a basic linear model.

## Project structure

The repository contains the main notebook:

- `prediction-multiple-linear-regression.ipynb`

This file includes the full workflow: data loading, exploration, preprocessing, polynomial transformation, model training, and evaluation.

## Requirements

To run this project, you need Python and a few key libraries. You can install them with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## How to run the project

1. Open the project folder in your terminal.
2. Start Jupyter Notebook:

```bash
jupyter notebook
```

3. Open the file `prediction-multiple-linear-regression.ipynb`.
4. Run each cell in order.

This will execute the data analysis and model training workflow from start to finish.

## Key takeaways

This project is a good example of how machine learning can be applied to a real-world prediction problem. It shows how data science goes beyond just coding — it requires understanding the problem, preparing the data, selecting the right model, and interpreting the output.

The biggest lesson from this project is that not all relationships are linear. In real estate, many factors interact with each other, and polynomial regression is one way to model those interactions more effectively.

## Final thoughts

This project demonstrates a practical use of regression in a domain where prediction can be highly valuable. House price estimation is a classic machine learning task because it combines structured data, real-world patterns, and measurable business impact.

By the end of the notebook, the model should be able to estimate a house’s price using available property features and show whether polynomial regression is a reasonable approach for this kind of problem.

## License

This project is intended for educational and demonstration purposes.
