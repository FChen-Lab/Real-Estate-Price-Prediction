# Real Estate Price Prediction Challenge

This repository contains the code and resources for the **Real Estate Price Prediction Challenge**, conducted as part of our **Machine Learning** course. The goal is to develop a robust machine learning model to predict real estate prices based on various property characteristics. The dataset includes both hierarchical tabular data and, optionally, visual data such as photos of properties, allowing for an exploration of whether the integration of visual data improves prediction accuracy.

## Key Achievement:
- **Achieved a Mean Absolute Percentage Error (MAPE) score of 29.7**, using tabular data alone (without incorporating photos).

## Table of Contents
1. [Project Description](#project-description)
2. [Data Description](#data-description)
3. [Objectives](#objectives)
4. [Approach](#approach)
5. [Evaluation Metrics](#evaluation-metrics)
6. [Results & Interpretability](#results--interpretability)
7. [Next Steps](#next-steps)
8. [Conclusion](#conclusion)
9. [Acknowledgments](#acknowledgments)
10. [Contributing](#contributing)

## Project Description

Accurately predicting real estate prices is a major challenge in the field of real estate analytics. The complexity of the market is driven by a wide variety of influencing factors such as property location, size, energy efficiency, and additional features (e.g., number of rooms, presence of a balcony). This project aims to leverage machine learning techniques to estimate property prices efficiently, while addressing issues like missing data and high-dimensional categorical variables.

In this repository, we focus on:
- Developing a regression model for property price estimation.
- Investigating feature importance to understand the key drivers of price variability.
- Laying the groundwork for integrating visual data (photos of the properties) into the modeling pipeline.

## Data Description

### Target Variable (PRICE)
- **PRICE**: The real estate price in euros (continuous variable). The target variable is highly dispersed, making preprocessing essential.

### Input Features (X)
The dataset includes **27 features**, with a mix of numerical and categorical variables:
- **Property Characteristics**:
  - Property type (house, apartment, mansion, etc.)
  - Location: Latitude, longitude, postal code, city, etc.
  - Size: Living area, land area (if applicable).
  - Number of rooms, bedrooms, bathrooms, etc.
  - Energy performance indicators (energy consumption and greenhouse gas emissions).
  
- **Additional Features**:
  - Presence of cellar, balcony, air conditioning, etc.
  - Number of photos attached to the listing (if available).

#### Photos:
- A folder named `ann_XX` contains 1 to 6 photos for each listing, where `XX` corresponds to the listing identifier. **Photos were not used in the current implementation but may be integrated in the future to enhance model performance**.

## Objectives
- **Main Objective**: Build a robust regression model for real estate price prediction.
- **Secondary Objective**: Investigate feature importance and model interpretability to identify the most influential features in predicting property prices.
- **Future Work**: Lay the groundwork for incorporating visual data to improve prediction accuracy.

## Approach

1. **Data Preprocessing**:
   - Handled missing values using techniques like **K-Nearest Neighbors (KNN) Imputer** for numerical features and **Iterative Imputation** for categorical features.
   - Applied **Label Encoding** for ordinal variables (e.g., energy performance category) and **One-Hot Encoding** for nominal variables (e.g., city, property type).
   - Standardized numerical features to improve model performance.

2. **Feature Engineering**:
   - Identified and removed redundant features to simplify the model.
   - Added derived features (e.g., total square footage of the property combining size and land size) to improve predictive power.

3. **Model Selection**:
   - Experimented with various regression models, including **Linear Regression**, **K-Nearest Neighbors (KNN)**, and **Random Forest**.
   - The **XGBoost** model was chosen as the best performer, offering superior handling of large datasets and feature interactions.

4. **Hyperparameter Tuning**:
   - Tuned **XGBoost** hyperparameters using **GridSearchCV** to optimize the model's performance.

5. **Future Enhancements**:
   - Plan to incorporate **photo data** and experiment with **multimodal models** to further improve prediction accuracy.

## Evaluation Metrics

We evaluated the performance of the regression models using the following metrics:

- **Mean Absolute Percentage Error (MAPE)**: Measures the accuracy of the model by calculating the percentage difference between predicted and actual values.
  - **MAPE**: Achieved a score of **29.7** with tabular data alone.
  - **Feature Importance**: Helps us understand which features were most influential in predicting property prices.

## Results & Interpretability

### Performance Metrics
The final model achieved a **Mean Absolute Percentage Error (MAPE) of 29.7** using only structured tabular data. We also focus on model interpretability:
- **Feature Importance**: Location, property type, and size were found to be the most influential features in predicting property prices.
- **Relationships**: We explored how key variables interact and influence price predictions.

### Next Steps
1. **Incorporate Visual Data**: Experiment with multimodal models that combine structured data with photos of properties to improve prediction accuracy.
2. **Fine-tune Models**: Explore advanced architectures and hyperparameter optimization to further reduce the MAPE score.

## Conclusion
This project demonstrates the potential for using machine learning techniques to predict real estate prices accurately with structured data. We achieved meaningful results by investigating feature importance and modeling techniques, and we are planning further steps to incorporate visual data and improve the model's precision.

## Acknowledgments
We would like to thank **Tony Bonnaire** for their invaluable guidance and support throughout this project. Their insights were essential for shaping our approach and achieving the final results.

## Contributing
Contributions are welcome! If you'd like to contribute, please follow these steps:

1. **Fork the repository.**
2. **Create a new branch** for your feature or bugfix:
    ```bash
    git checkout -b feature/your-feature-name
    ```
3. **Commit your changes**:
    ```bash
    git commit -m "Add your commit message here"
    ```
4. **Push to the branch**:
    ```bash
    git push origin feature/your-feature-name
    ```
5. **Open a pull request** and describe your changes.
