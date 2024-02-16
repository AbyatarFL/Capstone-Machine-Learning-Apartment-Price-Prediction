## Project Synopsis
The aim of this project is to create a predictive model using Machine Learning Algorithms to determine the appropriate selling price for an apartment based on the characteristics of the apartment itself (land area, distance to the station, year built, etc.). This model is expected to help stakeholders make the right decisions regarding prices, investment and property development. The tools used to build Machine Learning models are Python and use the Scikit-Learn library.

## Problem Statement
Some real estate agents and property owners have **difficulty determining the optimal price for the apartment they want to sell**. This is because there are many factors that must be considered in determining the right price, such as investing in areas where development factors are favorable, such as subway stations that pass through popular areas, land value, floor area ratio, etc. **Accuracy** in determining prices is very important to maintain a balance between profits and market attractiveness.

## **Analytical Approach**
This research will involve several features in an apartment and will look at their relationship with the price of the apartment itself. Because the target of this research is **numerically continuous apartment prices, a regression analysis approach will be used**. This model will use apartment features as predictors to estimate the selling price.

## **Evaluation Metrics**

Regression Models can be evaluated using Mean Absolute Error (MAE), Mean Absolute Percentage Error (MAPE) and Root Mean Squared Error (RMSE). This metric focuses on errors and provides insight into the accuracy of predictions, with lower evaluation values indicating a more accurate model. Apart from these metrics, the regression model can also be measured using R-Squared to see the proportion of variance explained by the model.

| Metrics | What | Why | When| Example |
|:-----:|:-----:|:-----:|:-----:|:-----:|
| MAE | Average absolute difference between estimated and actual values. | Less sensitive to outliers. | With many outliers or non-normal residuals. | in house pricing, if you’re off by 20.000 or 40.000, MAE treats these errors linearly (without considering their direction). |
| MAPE | Percentage error between estimated and actual values. | Easy interpretation as a percentage. | For forecasting and percentage-based error analysis. | For instance, if a house is worth 200.000 and your predict 180.000, the error is 10%. |
| RMSE | Square root of MSE, in same units as response variable. | Easier interpretation of errors. | When error scale should match target scale. | if RMSE is 20.000 it means the typical prediction error of the price is about 20.000. |
| R-Squared | Proportion of variance explained by the model. | Indicates model’s explanatory power. | To evaluate linear regression models’ fit. | in predicting house prices, a high R-Squared would indicate that your model captures most of the variability in house prices. |

## **Limitation**
- This model can only predict apartment prices in Daegu city, and cannot be used as a benchmark for prices in other areas.
- This model only uses data at one time, it cannot forecast prices in the future, because there could be changes in trends at times in the future.
- This model only considers the features in the dataset and cannot capture phenomena outside of the existing features, especially social, cultural and governmental factors.

## Data
Data Source:
- Main Dataset
  - Daegu Apartment: Can be downloaded in this GitHub repository file.
![Data_Dict](https://github.com/AbyatarFL/Capstone-Machine-Learning-Apartment-Price-Prediction/assets/109770559/522fc00a-566b-4c96-9016-b1d3d6535c8d)

## Result Summary
| Metrics | Random Forest RandomizedSearchCV |
|:-----:|:-----:|
| R^2 |0.819379|
| MAE |34966.132851|
| MAPE |0.193297|
| RMSE |42977.042072|

These are metrics used to evaluate the performance of Random Forest Regressor model in predicting apartment prices in Korean Won (₩). Here's how to interpret them:

1. **R^2 (Coefficient of Determination)**: This is 0.819379, which means that approximately **`81.94%`** of the variability in the apartment prices can be explained by the features in the model. This is a relatively high R^2, suggesting that the model explains a large portion of the variation in apartment prices & the model provides a reasonably good fit to the data.

2. **MAE (Mean Absolute Error)**: This is **`34,966.132851`**, which means that on average, your model's predictions are about ₩34,966.13 off from the actual apartment prices. This gives you an idea of the magnitude of the errors the model is making.

3. **MAPE (Mean Absolute Percentage Error)**: This is 0.193297, or **`19.33%`**. This means that on average, your model's predictions are about 19.33% off from the actual apartment prices. This gives you a relative measure of the errors the model is making.

4. **RMSE (Root Mean Square Error)**: This is **`42,977.042072`**, which is a measure of the differences between the values predicted by the model and the values actually observed. It's more sensitive to large errors (Outliers) than MAE because it squares the differences before averaging them. The RMSE being larger than the MAE suggests that your model is occasionally making large errors.

**Notes:**
- The MAE and the RMSE can be used together to diagnose the variation in the errors in a set of forecasts. The RMSE will always be larger or equal to the MAE; the greater difference between them, the greater the variance in the individual errors in the sample. If the RMSE=MAE, then all the errors are of the same magnitude **`(₩42,977.04 - ₩34,966.13 = ₩8,010.91 => The difference between MAE and RMSE is not too big, meaning that it can be said that the variance error in the prediction results is not too big.)`**
- Overall, these metrics suggest that the model is doing a reasonably good job of predicting apartment prices in Korean Won, but there is still room for improvement, particularly in reducing the size of the errors.

## **Conclusion**

- After rigorous analysis and hyperparameter tuning, the Random Forest model emerged as the most suitable algorithm for predicting apartment prices in Daegu city, achieving an impressive R^2 value of 0.819379. This indicates that approximately 81.94% of the variability in apartment prices can be explained by the features included in the model. While both Random Forest and Decision Tree models experienced enhancements post-tuning, the former exhibited slightly superior performance.

- However, it's important to acknowledge the limitations of the model. Predictions are constrained by the range and categories of features within the training dataset. Notably, the model's accuracy is bounded by the minimum and maximum values of features like apartment area, and it can only predict within the confines of the studied categories (e.g., hallway types, subway stations). Thus, while the model offers valuable insights for pricing apartments in Daegu, it cannot be extrapolated to other regions or forecast future price trends.

## **Recommendations For Further Analysis**

- **Data Expansion**: To enhance predictive accuracy, augment the dataset with additional features that significantly influence apartment prices, such as property amenities, neighborhood characteristics, and economic indicators.

- **Feature Engineering**: Develop new features or transformations that capture nuanced relationships between existing variables. For instance, consider creating composite features like the ratio of apartment size to the number of parking lots to better capture value propositions.

- **Continued Model Refinement**: Persist in refining the model through ongoing hyperparameter tuning, experimenting with alternative algorithms, and exploring ensemble techniques to further enhance predictive performance.

## **Measurable Implementation:**

To measure the success of these recommendations, you could track metrics such as:

- **Model Performance**: Monitor the model's R^2, MAE, MAPE, and RMSE over time. The goal is to increase the R^2 and decrease the error metrics. If the model's performance decreases, it may be necessary to retrain the model with new data.
- **User Satisfaction**: Conduct surveys to gauge user satisfaction with the price predictions. The goal is to increase user satisfaction scores.
- **Data-Driven Development**: Property builders and developers can use model data to determine which features should be prioritized in development projects, based on current market preferences & also formulate marketing strategies targeting property features that significantly influence the sales price.
- **Business Impact**: Track the impact of the model on business outcomes, such as the number of properties sold and the average selling price. The goal is to increase the number of properties sold and the average selling price.
