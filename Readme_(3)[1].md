# Business Understanding
The selling price of a home is a critical factor in the real estate market, as it directly influences the financial outcome for both buyers and sellers. For homeowners, the selling price represents the return on their investment and can significantly impact their financial well-being. Potential buyers, on the other hand, rely on the selling price to make informed decisions about purchasing a property within their budget and assessing its value relative to similar properties in the market.
House price is influenced by a multitude of factors, which can be broadly categorized into three main categories: property-specific factors, market factors, and external factors. Property-specific factors encompass attributes such as location, size, condition, amenities, architectural style, and age of the property. Market factors include supply and demand dynamics, interest rates, mortgage availability, and prevailing economic conditions. External factors can range from neighborhood characteristics, such as school quality and crime rates, to broader influences like government policies, infrastructure development, and demographic trends.
Understanding the factors that influence the selling price of residential properties is of paramount importance to various stakeholders involved in the real estate industry. Real estate agents need this knowledge to provide accurate pricing recommendations and effective marketing strategies for their clients. Homeowners can benefit from understanding these factors to make informed decisions when pricing their properties. Investors and developers can leverage this knowledge to identify promising investment opportunities and maximize their returns. 
## Problem Statement
The real estate agency faces a significant challenge in providing comprehensive guidance to homeowners regarding home renovations and their potential impact on the estimated value of their properties. Given the intricate nature of the real estate market and varying trends in buyer preferences, there is a pressing need to develop a systematic approach to assess the potential increase in property value resulting from specific renovation projects. Additionally, determining the optimal balance between renovation costs and potential value appreciation poses a critical dilemma for homeowners seeking to maximize their investment returns. Thus, the primary objective of this project is to devise a robust framework or tool that enables the agency to offer tailored advice to homeowners, elucidating the potential financial benefits of various renovation options and empowering them to make informed decisions about enhancing their property value effectively.
###Objectives
1. To understand factors that affect price of a house
2. To develop a model that can predict housing price based on various features. 
3. To make recommendations on how home owners can optimize selling price of a house



 ## Modelling 
Baseline model is with variable with the highest correlation with price which was sqft_living
 ## Model evaluation approach 
Adjusted R-squared to show variation explained
Durbin-Watson test to detect autocorrelation in residuals, ensuring the validity of regression analysis. 
Durbin-Watson test value between 1.5 and 2.5 indicates no significant autocorrelation 
##  Model comparison approach 
Adjusted R-squared to show variation explained. Higher Adjusted R-squared indicates better model
AIC (Akaike Information Criterion) and BIC (Bayesian Information Criterion) to compare goodness-of-fit and complexity of the models. Lower AIC and BIC values indicate a better model 
## Baseline model interpretation
With an F-statistic p-value below 0.05, the overall model is statistically significant.The results show that sqft_living explains 41.8% variation in price of houses.The model coefficients (const and sqft_living) are both statistically significant, with t-statistic p-values below 0.05.For 0 sqft_living, the estimated price is estimated to be -43490. An increase of 1 square foot in the living area leads to a price increase of approximately $283.4564.
 for the bathroom model, the F-statistic p-value below 0.05, the overall model is statistically significant.The results show that bathrooms explains 29% variation in price of houses.The model coefficients (const and sqft_living) are both statistically significant, with t-statistic p-values below 0.05.For 0 sqft_living, the estimated price is estimated to be 12.2218. An increase of 1 square foot in the living area leads to a price increase of approximately $0.3935.

## Evaluating Model Performance using Durbin-Watson.
The sqft_living model has a Durbin-Watson of 1.986 which shows that there is no significant autocorrelation.
The bathrooms model has a Durbin-Watson of 1.968 which shows that there is no significant autocorrelation.

## Second Model Interpretation( Multiple_Linear_Regression )
The first regression model shows that approximately 59.4% of the variability in house prices can be explained by the independent variables included in the model. These variables include features such as bedrooms, bathrooms, square footage, waterfront status, and others.

The second regression model with an R-squared of 0.594 indicates that approximately 59.4% of the variability in house prices can be explained by the included independent variables. These variables, such as bedrooms, bathrooms, square footage, and others, collectively contribute to predicting house prices, as evidenced by significant coefficients and low p-values.

The third regression model ( which has variables with the highest correlation with price ) has an R-squared of 0.511 suggests that approximately 51.1% of the variability in house prices can be explained by the included independent variables.

## polynomial regression
The first polynomial regression with a degree of 2 on the dataset, scaling the features and splitting the data into train and test sets, resulting in a root mean squared error (RMSE) of approximately 0.35 when predicting the target variable on the test data.

The second polynomial regression with a degree of 3 on the dataset, achieving an RMSE of approximately 0.34 as the evaluation metric.


The third polynomial regression with a degree of 4 on the dataset, achieving an RMSE of approximately 0.34 when predicting the target variable on the scaled test data.

## Conclusions
The study into the dynamics of housing price determinants underscores the complexity and multifaceted nature of real estate markets. The study reveals that a deep and nuanced understanding of regional trends, economic indicators, and a plethora of other variables is essential for crafting accurate and reliable predictive models. The insights gained from this research highlight the importance of adopting comprehensive and sophisticated analytical frameworks that can accommodate the intricate interplay of factors affecting housing prices.

Moreover, the findings underscore the value of continuous refinement and expansion of data collection methodologies, emphasizing the need for high-quality, diverse datasets. Such datasets are crucial for developing models that are not only robust and predictive but also reflective of the real-world variability and diversity of housing markets across different regions.

This research, therefore, not only contributes to the academic discourse on housing price prediction but also provides practical insights for policymakers, urban planners, and investors. By fostering a deeper understanding of market dynamics and improving predictive methodologies, we can better navigate the complexities of the housing market, ultimately contributing to more sustainable and equitable urban development.
## Limitations
The dataset does not include other factors such as location-specific characteristics, neighborhood amenities which determine price of houses
The data is collected over a period of time which encompasses different economic situations, changing market conditions, economic trends, and policy changes which were affect house prices but were not captured in the dataset.
 ## Results
* We conducted simple linear regression analyses on housing price versus two variables: bathrooms and square footage of living space (sqft_living).
* For sqft_living, the analysis showed a significant p-value (below 0.05), indicating a meaningful linear relationship with price. The coefficient estimate suggested a $283.4564 increase in price for each additional unit of living space.
* Similarly, the analysis for bathrooms revealed a significant correlation, with each extra bathroom associated with a $0.3779 increase in price, according to the coefficient estimate.

**Our polynomial regression model** is preferred as it achieved the highest R-squared value of 0.58, surpassing both the multiple linear regression model (0.53) and the simple regression analyses (0.41 and 0.29)

**The cross-validation results** provide valuable insights into the performance of our model. 
The mean R-squared score of 0.510 and the test R-squared score of 0.510 indicate that our model explains approximately 51% of the variance in the target variable. Additionally, the mean MSE of 0.136 and the test MSE of 0.137 suggest that our model's predictions are, on average, off by approximately 0.137 units. 
These consistent scores across cross-validation folds and the test set validate the robustness and generalization capability of our model, indicating its reliability in making accurate predictions on unseen data.
## Key findings
1. Bedrooms: Each additional bedroom is associated with a decrease in the estimated price by 0.0683 units, indicating that more bedrooms lead to lower housing prices in our model.
2. Sqft_lot: For every extra square foot of lot area, the estimated price decreases by $1.214e-05, suggesting that larger lot sizes correlate with lower housing prices.
3. Waterfront: Properties with a waterfront view are estimated to have a price increase of 0.6570 units compared to those without, highlighting the positive impact of waterfront views on housing prices.
4. Sqft_above and Sqft_basement: Each additional square foot of living space above ground and in the basement is associated with an estimated price increase of 0.0006 and 0.0005 units, respectively, underscoring the importance of larger living spaces in boosting housing prices.
5. Yr_built: With each year of construction, the estimated price decreases by 0.0034 units, indicating that newer properties tend to have lower prices compared to older ones.

* In conclusion, waterfront views and larger living spaces contribute positively to housing prices, while newer properties and larger lot sizes are associated with lower prices.

## Conclussion
Based on our analysis, we have uncovered several significant insights into the factors influencing housing prices. 
Firstly, features such as waterfront views, larger living spaces (both above ground and in the basement), and certain construction attributes positively impact housing prices. 
Conversely, newer properties tend to command lower prices compared to older ones, and factors like the number of bedrooms and lot size are associated with decreased prices.
## Limimitations
1. The dataset may lack additional property-specific characteristics that could provide further insights into housing prices.

2. Multicollinearity: The existence of correlated predictors within the dataset can result in multicollinearity problems, complicating the accurate interpretation of the individual impacts of each feature.

3. Overfitting: Polynomial regression models are prone to overfitting. This is where the model tightly conforms to the training data but may struggle to perform well on new, unseen data.
Overall the model was the best fit model for this prediction

## Recommendations
* The shareholder should encourage homeowners to do renovations so as to improve the overall condition and raise the property's grade as this has a great impact on the value of a house.

* For price prediction of the houses, we recommend use of Polynomial regression model as it gives a high R- squared value which means that we can get a better and more accurate price value.

**Further Data Collection:** the dataset could be expanded to include additional property-specific characteristics that may influence housing prices, such as proximity to amenities and neighborhood demographics, and property condition. This can provide a more comprehensive understanding of the housing market dynamics.

**Guard Against Overfitting:** To mitigate the risk of overfitting in polynomial regression models, using techniques such as cross-validation, regularization could be considered, or reducing the complexity of the model by selecting an appropriate degree for the polynomial features.

**Continuous Model Monitoring:** Continuously monitoring the model's performance and validity over time as new data becomes available or market conditions change. Regular updates and recalibration may be necessary to ensure the model remains relevant and accurate.