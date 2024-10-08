# Mall Customer Spending Behavior Analysis

## Overview
This project analyzes customer behavior in a shopping mall using demographic data such as age, gender, and annual income to predict spending scores. Through decision tree modeling and customer segmentation (clustering), we explore patterns in spending behavior and group customers into distinct segments for targeted marketing strategies. The project uses dummy data for educational purposes.

## Objective
To analyze customer demographics and spending patterns in order to:
1. Predict customer spending scores using decision tree modeling.
2. Segment customers into distinct groups based on demographic factors for targeted marketing strategies.

### Key Areas of Focus:
1. **Spending Score Prediction:**
   - Build a decision tree model to predict spending scores based on demographic factors (age, gender, and annual income).
   - Identify key characteristics of high-spending customers.
   
2. **Customer Segmentation:**
   - Use k-means clustering to segment customers based on age and income.
   - Identify target groups for marketing based on spending patterns and demographics.

## Data
The dataset used for this project contains the following variables:
- `Gender`: Customer gender (Male/Female)
- `Age`: Age of the customer
- `Annual Income`: Customer’s annual income in thousands of dollars
- `Spending Score`: A score assigned by the mall based on customer spending behavior

## Tools & Technologies
- **R Programming Language**: Used for data manipulation, modeling, and visualization
- **ggplot2**: For creating data visualizations
- **rpart & rpart.plot**: For building and visualizing decision tree models
- **k-means clustering**: For customer segmentation
- **caTools**: For data splitting and model evaluation

## Skills Demonstrated
- **Data Wrangling**: Cleaning and transforming customer data
- **Exploratory Data Analysis (EDA)**: Visualizing distributions and relationships between variables
- **Decision Tree Modeling**: Predicting spending scores based on demographic factors
- **Clustering**: Grouping customers into meaningful segments using k-means clustering
- **Business Insights**: Generating actionable insights for customer marketing strategies based on spending behavior

## Project Structure
### 1. Decision Tree for Spending Score Prediction
- **Question**: Which demographic factors most influence spending behavior, and how can we predict customer spending scores?
  
  **Code Snippet**:
  ```r
  # Fitting a Decision Tree (Regression) on the Training Set
  model <- rpart(Spending.Score ~ Gender + Age + Annual.Income, data = training_set, method = 'anova')

  # Visualizing the Decision Tree
  rpart.plot(pruned_tree)
  ```

  ## Insights

- **Older, higher-income customers** tend to have higher spending scores, making them a key target for premium products and services.
- **Younger customers with low income** have lower spending scores, suggesting that they are more price-sensitive and would respond better to discounts and promotions.

### Visuals

![Decision Tree](path_to_decision_tree_image.png)

---

## 2. Customer Segmentation Using K-Means Clustering

### Question: 
How can we group customers into distinct segments based on their demographic characteristics?

### Code Snippet:
```r
# Final Clustering with 3 clusters
km.out <- kmeans(data_2cols, centers = 3, nstart = 20)
data$cluster_id <- factor(km.out$cluster)

# Visualize the Clusters
ggplot(data, aes(Age, Annual.Income, color = cluster_id, alpha = Gender)) +
  geom_point(size = 2) +
  xlab("Age") +
  ylab("Annual Income ($ in thousands)") +
  scale_alpha_manual(values = c(0.3, 0.9))
```

## Insights

- **Cluster 1**: Young, high-income customers are ideal targets for premium products.
- **Cluster 2**: Young, low-income customers are more price-sensitive and may respond to discounts.
- **Cluster 3**: Older, lower-income customers are value-conscious, making them ideal candidates for loyalty programs or practical product offerings.

### Visuals
![Cluster Visualization](path_to_cluster_image.png)

---

## Data Sources

This project uses **dummy data** representing mall customer demographics and spending scores. The dataset is fictional and intended for educational purposes.

---

## Conclusion

This analysis provides valuable insights into customer segmentation and spending behavior in a mall setting:

- **Older, wealthier customers** are more likely to spend more, making them prime candidates for premium offerings.
- **Younger, price-sensitive customers** can be targeted with discounts and promotions to boost engagement.
- The segmentation highlights three key customer groups, allowing for tailored marketing strategies based on spending habits and demographic characteristics.

---

