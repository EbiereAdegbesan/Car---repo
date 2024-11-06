!# Car Manufacturer Dataset Analysis for Fuel Efficiency

## Project Overview

A car manufacturer specializing in large vehicles is facing declining sales due to the lower fuel efficiency of its cars. The goal of this project is to analyze and identify key vehicle attributes that contribute to higher gas mileage (miles per gallon, or MPG). The ultimate objective is to recommend features that will help the company design a more fuel-efficient automobile.

This analysis is divided into three main parts:
1. **Data Cleaning**: Ensuring high-quality data for accurate modeling.
2. **Linear Regression Model**: Building a predictive model for MPG.
3. **Model Optimization**: Using feature selection techniques to improve model performance.

---

## Part 1: Data Cleaning

The initial dataset provided contained various attributes related to the vehicle's design, engine, and weight. Data cleansing was crucial to improve data quality and ensure reliability in the analysis.

### Data Cleansing Steps
1. **Handling Missing Values**: Missing values were assessed across attributes. Imputation techniques were used based on attribute types:
   - **Numeric Attributes**: Missing values were filled using the median value for numeric features, as median imputation minimizes the influence of outliers.
   - **Categorical Attributes**: For categorical features with missing values, the mode (most frequent value) was used as a replacement.

2. **Removing Outliers**: To maintain data integrity, we identified outliers in key numerical columns (such as engine size, weight, horsepower, and MPG) using the Interquartile Range (IQR) method. Outliers were either removed or capped to the nearest value within the acceptable range.

3. **Standardizing Units**: Attributes were standardized where necessary (e.g., engine displacement in liters and horsepower) to maintain consistency. 

4. **Encoding Categorical Variables**: Certain features were categorical, such as vehicle type or fuel type. These were converted to numerical representations using one-hot encoding.

5. **Scaling**: All numerical features were scaled using StandardScaler to standardize feature ranges, improving model performance and convergence.

By performing these steps, we ensured a high-quality dataset, free from inconsistencies, which would be critical for accurate model building in Part 2.

---

## Part 2: Linear Regression Model

### Model Overview

To predict MPG, we used a linear regression model, as it is interpretable and provides insights into the relationship between various car attributes and fuel efficiency.

### Significant Attributes

The following attributes were found to be significant predictors of MPG:
- **Vehicle Weight**: There was a strong negative correlation between vehicle weight and MPG. Heavier vehicles generally had lower fuel efficiency.
- **Engine Size (Displacement)**: Larger engines tended to consume more fuel, negatively impacting MPG.
- **Horsepower**: Higher horsepower was associated with lower MPG, likely due to higher energy demands.
- **Vehicle Type**: Smaller and more compact vehicle types showed better fuel efficiency than larger vehicles.

### Model Performance

The initial linear regression model achieved a reasonable performance, with an R-squared value indicating that a substantial portion of MPG variance could be explained by the selected attributes. However, further optimization was necessary to refine the model.

---

## Part 3: Model Optimization

To improve the model’s accuracy, we applied feature selection techniques to retain only the most impactful variables. This also reduced multicollinearity, improving interpretability and model performance.

### Feature Selection Techniques

1. **Correlation Analysis**: Highly correlated variables were identified and removed to reduce redundancy and potential multicollinearity.
2. **Recursive Feature Elimination (RFE)**: RFE was used to select the top features that contributed most significantly to MPG prediction, simplifying the model without compromising accuracy.
3. **Regularization (Lasso)**: Lasso regularization was employed to penalize less impactful features, leading to a more concise model.

### Final Model and Key Findings

The optimized model highlighted the following attributes as primary contributors to higher MPG:
- **Vehicle Weight**: Reducing weight emerged as one of the most effective ways to improve fuel efficiency.
- **Engine Displacement**: Using smaller, more efficient engines contributed positively to MPG.
- **Aerodynamics**: Although not directly measured in this dataset, vehicles with streamlined designs tended to have higher MPG, suggesting that future models should account for this.
- **Transmission Type**: Vehicles with more efficient transmissions (e.g., automatic vs. manual) generally exhibited higher MPG.

### Model Performance Evaluation

The optimized linear regression model met the requirements for accurate MPG prediction and provided insights that can guide the design of more fuel-efficient vehicles.

---

## Conclusion

This analysis demonstrates that vehicle weight, engine size, and aerodynamics are critical factors for improving fuel efficiency. By focusing on these areas, the manufacturer can create a more energy-efficient vehicle design that meets consumer demands for lower fuel consumption.

---

## Future Work

- **Additional Data Collection**: Including features such as tire resistance, aerodynamic drag coefficient, and advanced transmission types could further enhance the model.
- **Alternative Models**: Exploring nonlinear models, such as decision trees or ensemble methods, may improve prediction accuracy and uncover complex relationships among attributes.

This project highlights the importance of data-driven decisions in automotive design, particularly in the context of fuel efficiency. The findings and recommendations here can serve as a foundation for the manufacturer's next-generation vehicle models.
