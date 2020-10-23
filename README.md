# King County Housing Price Prediction
![seattle](https://cdn.britannica.com/41/41341-050-1C78C21D/Seattle-background-Mount-Rainier.jpg)

## Overview
This project will utilize multiple regression analysis to predict housing prices in King County, Seattle, WA. The training data will be explored for feature building and the final model will be built and trained by SciKit python library. The data and project scope was provide by Flatiron School for Data Science Immersive program phase 2 final project. 

## Repository Structure
    .
    ├── data                                # data folder
    │   ├── zipcode_shape                   # shapefile for plotting with zipcode
    ├── reference                           # project reference files
    ├── images                              # project image/graph files
    ├── models                              # final regression models
    ├── results                             # model predicted file location
    ├── housing_price_prediction.ipynb      # project notebook with EDA and model creation
    ├── king_county_prediciton.ipynb        # final prediciton notebook, model implementation
    └── README.md


## Business Problem
A Seattle real estate company seeks to increase porfolio in King County Seattle and wants to accurately predict the sales price of a property. Having an accurate sales prediction will aid in strategizing the investment options to maximize their profit. A multiple linaer regression model will be built base on provided property data for this task. 

During the exploratory phase following questions will also be focused on:
1. What location in the county has the highest property value?
2. What aspects of the property brings value?
3. Do renovations have effect on property value?

## Approach
1. Check for data completeness and integrity
2. Perform EDA with statistical analysis to determine statistically significant features
3. Visualize statistically significant features
4. Engineer new features based on stastistical findings
5. Model Linear Regression models and evaluate each model for final implementation
6. Implement feature engineering and final model to the data set. 

## Analysis
The location of the property was one of the most important factor when determining the property value. It was found that the property price of top 5 neighborhood, ranked by mean property price, doubled the average property price of King County.<br>
![rich neighborhoods](https://github.com/yunghanjeong/King_County_Housing_Price_Prediction/blob/main/images/high_price_neighborhood.png?raw=true)<br>

Mapping the chrolopeth around the these neighborhood shows clear dominance in property price in the area. <br>
![rich neighborhoods map](https://github.com/yunghanjeong/King_County_Housing_Price_Prediction/blob/main/images/zipcode_price_heatmap.png?raw=true)<br>

It was also determined that having a renovated property significantly raised the property price. Basement was a significant feature as well, but not as much as renovation. <br>
![house_features](https://github.com/yunghanjeong/King_County_Housing_Price_Prediction/blob/main/images/basement_renovation_value.png?raw=true)<br>

Surprisingly, property within condition 4/5 had lower average price than properties with conditions 3/5. This could be due to presence in apartments/coops in the data set, which tend to be well maintained, but have lower price per unit compared to private homes. <br>
![conditions](https://github.com/yunghanjeong/King_County_Housing_Price_Prediction/blob/main/images/condition_value.png?raw=true)<br>

If the company wants to expand their porfolio, it is recommended to look for properties in Medina, Belleve, Mercer Island, Madison Park, and Capitol Hill area. The company should also investigate for renovation potential and purchase any property that may require renovation under $125,000. They should also focus on properties with basement and with properties in condition between 3-4. 

## Modeling
Using Scikit-learn package 3 linear regression models were crated.
- Linear Regression
- Linear Regression with Recursive Feature Eliminiation
- Linear Regression with Recursive Feature Elminiation and Cross Valdiation

It was determined that the Linear Regression with Recursive Feature Eliminiation model perfromed the best and was utilized for the final implementation. 

## Summary

The King County Housing prices data was analyzed, tested, and modeled. Some of the significant factors of the housing prices were determined as the zipcode/neighborhood, the property condition, renovation, and basement. The baseline of the model was created with LinearRegression method from statsmodel library. Applying Scikit-learn libraries linear regression models showed ~25% reduction in root mean squared errors. Some of the features that had the largest impact in the linear regression were dummy variables of zipcode and renovation age.

When modeling, the basic and RFECV linear model performed the best in root mean sqaured error values. However, when the model coefficients were analyzed it was shown that RFE had the best balance of coefficient. The basic linear model seemed to trend in negative direction and RFECV had abnormally high coefficients.

## Future Work 
- Create additional features using interaction. 
- Create boundaries for neighborhoods or larger area than just utilizing zipcode. 
- Categorize property type with sqft_living, sqft_lot, sqft_basement, and bedrooms. 