# Prediction-of-Product-Sales

by Jonathan Nunez |  jon.nunez92@gmail.com
-------------------------------------------
[Link to the Data (.csv)](https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view)\
[Source of the Data](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/)

### With these graphs and models, we can predict future product sales for our clients.

## Data Dictionary
Explanation of the various columns in the Dataset
![Data Dictionary](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/Data%20Dictionary%20(80%25).png)

## Item MRP by Outlet Sales
- Here we can see that as the price of the item goes up, the total return goes up as well
  - Less of those products are sold, but the higher price makes up the difference
![Item MRP by Outlet Sales](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/Item%20MRP%20by%20Outlet%20Sales.png)

## Sales by Item Type
- We can see that 'Fruits and Vegetables' has the most sales followed closely by 'Snack Foods'
![Sales by Item Type](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/Sales%20by%20Item%20Type.png)

## Comparing Outlet Type, Size, and Location Type by Sales
- This plot is broken up into the 3 Tiers of Outlet_Location_Type with a hue of Outlet_Size
- It shows the Outlet_Type by Item_Outlet_Sales
- We can see that there are much more Medium stores
- We can also see that Tier 3 stores have the most variety of Outlet_Type
- We can then see that Supermarket Type1 is in every Tier and has all Outlet_Sizes including the Missing ones
![Outlet Type, Size, and Location Type by Sales](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/Comparing%20Outlet%20Type%2C%20Size%2C%20and%20Location%20Type%20by%20Sales.png)

## Model Evaluation
The Decision Tree is the better model to use when predicting Item Sales.

From the Metrics Score, we can see that the Mean Absolute Error for the Decision Tree is lower by about 70 rupees. The Root Mean Squared Error is also lower for the Decision Tree, meaning that there are less outliers throwing off the weight of our model.

Looking at the Percentage of Error, we can also see that the Linear Regression model will be off, on average, by 36.87% while the Decision Tree will be off by 33.85%. We'll have less error with the Decision Tree.
***
# Project 1 - Revisited

## LinearRegression Most Important Coefficients
![linreg_coefficients](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/linreg_coefficients.png)

### Interpret Top 3 Most Impactful Features

- 'Outlet_Type_Supermarket Type1':
    - If the Outlet Type is Supermarket Type 1, increase in target value by 936.702
    
    
- 'Outlet_Identifier_OUT027':
    - If the Outlet Identifier is OUT027, increase in target value by 907.157
    
    
- 'Outlet_Type_Supermarket Type3':
    - If the Outlet Type is Supermarket Type 3, increase in target value by 907.157
    
    
- The most impactful features are object type

## RandomForest Feature Importances

### Default Importances
![rf_default_importances](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/rf_default_importances.png)

#### Top 5 Most Important Default Features
    - 'Item_MRP'
    - 'Outlet_Type_Grocery Store'
    - 'Item_Visibility'
    - 'Item_Weight'
    - 'Outlet_Identifier_OUT027'

### Permutation Importances
![rf_perm_importances](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/rf_perm_importances.png)

#### Top 5 Most Important Permutation Features:
    - 'Item_MRP'
    - 'Outlet_Type_Grocery Store'
    - 'Item_Visibility'
    - 'Item_Weight'
    - 'Outlet_Identifier_OUT027'    

- Same features as Default Importance, but, in this case, the features are valued higher in importance compared to the Default

***
# Project 1 - Revisited Part 2: Explaining Models with SHAP

## Summary Bar Plot RandomForestRegressor
![summary_bar_plot_rf_reg](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/summary_plot_bar_rf_reg.png?raw=true)

### Comparison with RandomForest Regressor Feature Importance

#### Default Feature Importances
![rf_default_importances](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/rf_default_importances.png)

#### Permutation Feature Importances
![rf_perm_importances](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/rf_perm_importances.png)

#### Differences
- Default and Permutation Importances have the same top 5 features

- SHAP Plot Summary differs in that:
    - 'Item_Visibility' is ranked lower (5th instead of 3rd)
    - 'Outlet_Type_Supermarket Type 3' takes the place of 'Item_Weight' (ranked 4th)
    - 'Outlet_Identifier_OUT027' is ranked higher (3rd instead of 5th)

 ## Summary Dot Plot RandomForestRegressor
 ![summary_plot_dot_rf_reg](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data/summary_plot_dot_rf_reg.png?raw=true)

 ### Summary Dot Plot Interpretation

**Interpret Top 3 Features**

- 'Item_MRP':
    - As the value of the item's MRP increases (gets redder), the target value ('Item_Outlet_Sales') increases as well (moves right)


- 'Outlet_Type_Grocery_Store' (true/false):
    - Being a Grocery Store (red/true) will decrease (move left) the target value ('Item_Outlet_Sales')
    - Not being a Grocery Store (blue/false) will increase (move right) the target value ('Item_Outlet_Sales')
    
    
- 'Outlet_Identifier_OUT027' (true/false):
    - Being Outlet OUT027 (red/true) will increase (move right) the target value ('Item_Outlet_Sales')
    - Not being a Outlet OUT027 (blue/false) will only marginally affect (keep center at 0 or slightly move left) the target value ('Item_Outlet_Sales')
