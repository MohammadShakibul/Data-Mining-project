# **Intelligent Sales Revenue Forecast**

This project implements an **Intelligent Sales Revenue Forecasting System** using machine learning techniques.  
It uses the *Sample – Superstore* dataset to analyze historical sales performance and build predictive models capable of forecasting future revenue.

The system focuses on understanding key sales drivers such as:

* Product category and sub-category  
* Region and customer segment  
* Discounts, profit margins, and order quantities  
* Shipping methods and delivery timelines

The uploaded notebook (Intelligent Sales Revenue Forecast) contains end-to-end steps including data preprocessing, exploration, visualization, and model training.

## **Project Overview**

The goal of this project is to leverage machine learning and data mining techniques on transactional sales data to achieve two key objectives:

1. **Loss Prediction (Classification):** Accurately predict whether a new sales order is likely to result in a financial loss (Negative Profit).  
2. **High-Profit Product Association (Market Basket Analysis):** Identify strong co-purchase relationships between items that typically generate high profits, enabling targeted cross-selling and product bundling strategies.

## **Dataset**

The project utilizes the Sample \- Superstore (1).csv dataset, which contains 9,994 records of sales transactions with the following key columns:

* Order Date, Ship Date  
* Segment, Region, State, City  
* Category, Sub-Category, Product Name  
* Sales, Quantity, Discount, and **Profit**

## **Methodology and Analysis**

The project employs a two-pronged data mining approach:

### **1\. Loss Prediction via Classification**

* **Feature Engineering:** A new feature, **Processing Time** (Ship Date \- Order Date), was calculated to determine its influence on profit outcomes.  
* **Target Variable:** A binary variable, **Is\_Loss**, was created (1 for Loss, 0 for Profit).  
* **Preprocessing:** A scikit-learn pipeline was used for simultaneous:  
  * **Standard Scaling** on numerical features (Sales, Quantity, Discount, Processing Time).  
  * **One-Hot Encoding** on all categorical features (Category, Sub-Category, Region, etc.).  
* **Model:** A **Random Forest Classifier** was trained to predict the Is\_Loss outcome.

### **2\. High-Profit Association Rule Mining**

* **Data Preparation:** The analysis was narrowed down to transactions containing products from high-profit **Sub-Categories** (where the sub-category's average profit was greater than $100).

* ### **Algorithm:** The Apriori Algorithm was used to discover frequent itemsets and generate association rules for these high-profit items.

### **Approach Summary** **1\. Data Loading & Cleaning**

* Handling missing values  
  * Parsing dates  
  * Filtering invalid entries

**2\.** **Feature Engineering**

* ### **Extracting month, year, season**

  * Creating aggregated sales features  
  * Encoding categorical variables

**3\.** **Exploratory Data Analysis**

* ### **Trend line of sales over years**

  * Category-wise revenue distribution  
  * Regional performance analysis  
  * Profit vs. Discount relationship

**4\.** **Model Building**Depending on the notebook, these models may be implemented:

* ### **Linear Regression – baseline**

  * **Random Forest Regressor** – improved accuracy

**5\.** **Forecasting Output**The notebook generates:

* ### Predicted sales

  * Error metrics  
  * Sales trend charts

## 

##  **Key Results & Insights**

### **A. Classification Results (Loss Prediction)**

The Random Forest model demonstrated excellent performance on the test set:

* **Accuracy:** 100%  
* **Precision and Recall:** 1.00 for both Profit (0) and Loss (1)

#### **Top Features Driving Order Loss:**

Analysis of feature importance revealed the most significant drivers contributing to an order being a financial loss.

| Feature Name | Importance Score |
| :---- | :---- |
| **Discount** | High Importance |
| **Sales** | High Importance |
| **Furniture-Tables** | High Importance |
| **Binders-Binders** | High Importance |

### **B. Association Rule Mining Results (High-Profit Items)**

The analysis identified key co-purchase patterns among high-profit products, useful for bundling and marketing:

| Rule (Antecedent → Consequent) | Lift | Insight |
| :---- | :---- | :---- |
| **(Storage)** $\\rightarrow$ **(Furnishings, Paper)** | **1.435** | Customers buying Storage are significantly more likely to also buy Furnishings and Paper together. |
| **(Furnishings, Paper)** $\\rightarrow$ **(Storage)** | **1.435** | A strong mutual relationship exists between these item groups. |
| **(Furnishings)** $\\rightarrow$ **(Paper, Storage)** | **1.264** | People who buy Furnishings have a statistically strong chance of also purchasing Paper and Storage. |

**Insight:** Leverage these high-lift association rules for targeted product bundling or strategic store layouts to encourage cross-selling and maximize overall profit.

## **🛠️ Technologies Used**

* Python  
* Pandas  
* NumPy  
* Scikit-Learn  
* Matplotlib / Seaborn  
* Jupyter Notebook

## **⚙️ Requirements**

To run the project notebook, you will need the following Python libraries:

* pandas  
* numpy  
* matplotlib  
* seaborn  
* scikit-learn (sklearn)  
* mlxtend

You can install them using pip:

pip install pandas numpy matplotlib seaborn scikit-learn mlxtend

## ** How to Run the Project**

1. **Clone the Repository:**  
   git clone \[https://github.com/MohammadShakibul/Data-Mining-project.git\](https://github.com/MohammadShakibul/Data-Mining-project.git)  
   cd Data-Mining-project

2. **Download Dataset:** Ensure the Sample \- Superstore (1).csv file is in the root directory.  
3. **Open the Notebook:** Run the Intelligent Sales Revenue Forecast Jupyter Notebook.  
4. **Execute Cells:** Run all cells in sequence to reproduce the data cleaning, model training, loss prediction, and association rule mining analysis.

## ** License**

This project is licensed under the MIT License \- see the LICENSE.md file for details (if applicable).
