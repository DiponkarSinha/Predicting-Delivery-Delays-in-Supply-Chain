# Late Delivery Risk Prediction

## Summary

This project aimed to predict the risk of late deliveries in a supply chain dataset using machine learning models. It was assumed that accurately predicting late delivery risk rather than no-risk was of highest importance to the business. Therefore, the predictive model was optimized for sensitivity (recall). We applied Logistic Regression, Random Forest, and XGBoost, achieving consistent and high model performance, with accuracies around **97.4%** across all models.

The main focus was to identify key features driving the risk of late delivery, such as shipment timing, payment method, and the variance between scheduled and actual shipping days. The project successfully highlighted how machine learning can help manage supply chain performance and mitigate operational risks.

## Approach

### 1. Exploratory Data Analysis (EDA)
- Conducted an in-depth analysis of the dataset.
- Key insights were drawn regarding delivery delays, including a visualization that showed the **variance in delivery dates** across different shipping modes:
![Delivery Date Variance](https://github.com/PolinaBurova/Predicting-Delivery-Delays-in-Supply-Chain/blob/main/DeliveryDate_Risk.png)
*This chart visualized the variance in shipping days, clearly showing which shipping methods had the highest inconsistency in delivery performance(First and Second Classes).*


### 2. Feature Selection
- **Chi-square test** for categorical variables such as payment methods and shipping modes.
- **Variance threshold** to remove low-variance features.
- **Correlation analysis** to handle multicollinearity between features.
- Applied **Recursive Feature Elimination (RFE)** with Logistic Regression, selecting the top 15 most relevant features to be used out of an initial set of 27.

### 3. Data Preprocessing
- Handled **missing values** and **outliers** effectively.
- Scaled and encoded features, and checked for any class imbalances to ensure a robust model.

### 4. Model Optimization
- **Hyperparameter tuning** using GridSearchCV was performed to fine-tune models and avoid overfitting.
- Emphasized **recall** as the key metric to minimize false negatives.
- **Feature importance** and **coefficients** were analyzed, revealing the most influential features for predicting late deliveries:

![LR Feature Coefficients](https://github.com/PolinaBurova/Predicting-Delivery-Delays-in-Supply-Chain/blob/main/Features_Ranking1.png)

![RF and XGBoost Ranking](https://github.com/PolinaBurova/Predicting-Delivery-Delays-in-Supply-Chain/blob/main/Features_Ranking2.png)

## Results
- The models evaluated (Logistic Regression, Random Forest, and XGBoost) all performed exceptionally well, achieving **97.4% accuracy** and a recall of 1.
- **Shipment timing** was identified as the most critical factor in predicting late delivery risk. Features like **"Days for shipping (real)"**, **"Days for shipment (scheduled)"**, and **"diff(hours)"** were consistently ranked among the top features.
- **Payment method**, specifically **Transfer**, was another key predictor of delivery delays.

## Improvements
Potential improvements for this project:
- **Advanced feature engineering**: Introduce new features that capture more intricate business-related details.
- **Customer-level analysis**: Looking into customer-specific factors (e.g., geographical regions, customer profiles) could offer additional predictive insights.
- **Real-time integration**: Implement the model in a live system to predict and flag late deliveries before they occur.
