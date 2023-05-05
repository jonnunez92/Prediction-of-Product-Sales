# Prediction-of-Product-Sales

by Jonathan Nunez |  jon.nunez92@gmail.com
-------------------------------------------
[Link to the Data (.csv)](https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view)\
[Source of the Data](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/)

### With these graphs and models, we can predict future product sales for our clients.

## Data Dictionary
Explanation of the various columns in the Dataset
![Data Dictionary](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Data%20Dictionary%20(80%25).png)

## Item MRP by Outlet Sales
- Here we can see that as the price of the item goes up, the total return goes up as well
  - Less of those products are sold, but the higher price makes up the difference
![Item MRP by Outlet Sales](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Item%20MRP%20by%20Outlet%20Sales.png)

## Sales by Item Type
- We can see that 'Fruits and Vegetables' has the most sales followed closely by 'Snack Foods'
![Sales by Item Type](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Sales%20by%20Item%20Type.png)

## Comparing Outlet Type, Size, and Location Type by Sales
- This plot is broken up into the 3 Tiers of Outlet_Location_Type with a hue of Outlet_Size
- It shows the Outlet_Type by Item_Outlet_Sales
- We can see that there are much more Medium stores
- We can also see that Tier 3 stores have the most variety of Outlet_Type
- We can then see that Supermarket Type1 is in every Tier and has all Outlet_Sizes including the Missing ones
![Outlet Type, Size, and Location Type by Sales](https://github.com/jonnunez92/Prediction-of-Product-Sales/blob/main/Comparing%20Outlet%20Type%2C%20Size%2C%20and%20Location%20Type%20by%20Sales.png)

## Model Evaluation
The Decision Tree is the better model to use when predicting Item Sales.

From the Metrics Score, we can see that the Mean Absolute Error for the Decision Tree is lower by about 70 rupees. The Root Mean Squared Error is also lower for the Decision Tree, meaning that there are less outliers throwing off the weight of our model.

Looking at the Percentage of Error, we can also see that the Linear Regression model will be off, on average, by 36.87% while the Decision Tree will be off by 33.85%. We'll have less error with the Decision Tree.
