# Churn_Analysis_And_Prediction
# 📉 Customer Churn Analysis & Prediction

An end-to-end **Customer Churn Analysis and Prediction** project built using **SQL Server, Power BI, Python, and Machine Learning**.

The project analyzes customer behavior, identifies patterns behind churn, builds an interactive Power BI dashboard, and uses a **Random Forest Classifier** to predict customers who may churn in the future.

> **From raw customer data → business insights → churn prediction.** 📊🤖

---

## 📌 Project Overview

Customer churn is one of the biggest challenges for subscription-based businesses.

Knowing that customers are leaving is useful.

But knowing **why they are leaving** and **who might leave next** is much more valuable.

This project follows an end-to-end analytics workflow to:

* Clean and transform customer data
* Store and process data using SQL Server
* Analyze customer demographics and behavior
* Identify churn patterns and possible churn reasons
* Build an interactive Power BI dashboard
* Prepare data for Machine Learning
* Train a Random Forest classification model
* Predict potential future churners
* Visualize predicted churners in Power BI

---

## 🏗️ Project Architecture

```text
Raw Customer Data
        ↓
   SQL Server
        ↓
   Staging Table
        ↓
 Data Exploration
        ↓
 Data Cleaning
        ↓
 Production Table
        ↓
    SQL Views
        ↓
     Power BI
        ↓
 Data Transformation
        ↓
   DAX Measures
        ↓
 Churn Analysis Dashboard
        ↓
 Python + Machine Learning
        ↓
 Random Forest Classifier
        ↓
 Churn Prediction
        ↓
 Predicted Churners
        ↓
 Power BI Prediction Dashboard
```

---

## 🛠️ Tech Stack

| Technology               | Purpose                                                      |
| ------------------------ | ------------------------------------------------------------ |
| **Microsoft SQL Server** | Data storage, cleaning, transformation and SQL analysis      |
| **Power BI**             | Data modeling, DAX, visualization and interactive dashboards |
| **Python**               | Machine Learning and prediction                              |
| **Pandas**               | Data manipulation                                            |
| **NumPy**                | Numerical operations                                         |
| **Scikit-learn**         | Machine Learning                                             |
| **Matplotlib**           | Visualization                                                |
| **Seaborn**              | Data visualization                                           |
| **Joblib**               | Model serialization                                          |

---

# 🗄️ 1. SQL Server — Data Preparation

The project begins by loading the raw customer dataset into **Microsoft SQL Server**.

A staging table is created to hold the raw data:

```text
stg_Churn
```

After exploring the dataset and handling missing or inconsistent values, the cleaned data is moved into:

```text
prod_Churn
```

SQL is then used to perform exploratory analysis and create analytical views.

### Important SQL Views

```text
vw_ChurnData
vw_JoinData
```

`vw_ChurnData` is used for historical churn analysis, while `vw_JoinData` contains customers who recently joined and are used later for churn prediction.

---

# 📊 2. Power BI — Churn Analysis Dashboard

The cleaned data is imported into Power BI for transformation, modeling and visualization.

Several calculated fields and measures are created to support the analysis.

### Important KPIs

* 👥 Total Customers
* 🆕 New Joiners
* 📉 Total Churn
* 📊 Churn Rate

### Customer Analysis

The dashboard analyzes churn across multiple dimensions, including:

* Gender
* Age Group
* State
* Contract Type
* Tenure
* Payment Method
* Monthly Charges
* Internet Type
* Customer Services
* Churn Category
* Churn Reason

The dashboard is interactive, allowing users to filter and explore different customer segments.

---

# 🖥️ Dashboard Screenshots

## Executive Summary Dashboard

<!-- Add your screenshot here -->

![Executive Summary Dashboard](images/executive-summary.png)

---

## Customer Churn Analysis

<!-- Add your screenshot here -->

![Customer Churn Analysis](images/churn-analysis.png)

---

## Churn Reasons / Service Analysis

<!-- Add your screenshot here -->

![Churn Reasons](images/churn-reasons.png)

---

## 🔮 Churn Prediction Dashboard

<!-- Add your screenshot here -->

![Churn Prediction Dashboard](images/churn-prediction.png)

> **Tip:** Replace the image paths above with the actual screenshots you upload to the repository.

---

# 🤖 3. Machine Learning — Churn Prediction

After analyzing historical churn, the project moves from **descriptive analytics to predictive analytics**.

The objective is to identify customers who are likely to churn in the future.

### Target Variable

The customer status is converted into a binary target:

```text
Stayed  → 0
Churned → 1
```

Categorical features are converted into numerical representations before training the model.

The dataset is divided into:

```text
80% → Training Data
20% → Testing Data
```

---

# 🌲 4. Random Forest Classifier

A **Random Forest Classifier** is used to predict customer churn.

The model learns patterns from existing customers whose churn status is already known.

It then uses those patterns to predict whether new customers are more likely to:

```text
Stay
or
Churn
```

### Model Evaluation

The model is evaluated using:

* Confusion Matrix
* Precision
* Recall
* F1-Score
* Classification Report

Feature importance is also analyzed to understand which customer characteristics contribute most to the model's predictions.

---

# 🔮 5. Predicting Future Churners

Once the Random Forest model is trained, it is applied to customers whose future churn status is not yet known.

The model generates a predicted customer status:

```text
Customer_Status_Predicted
```

Customers predicted as potential churners are then extracted and visualized in Power BI.

This creates a **Churn Prediction Dashboard** that can help identify customers who may require retention efforts.

---

# 💡 Key Insights

The project focuses on answering questions such as:

* Which customer segments have higher churn?
* Which contract types are associated with higher churn?
* Does customer tenure influence churn?
* Which payment methods show higher churn?
* Which regions have higher churn rates?
* What are the most common reasons for customers leaving?
* How do different services relate to customer retention?
* Which customers are predicted to churn in the future?

The goal is not just to visualize these patterns, but to turn them into information that can support business decisions.

---

# 📁 Project Structure

```text
Customer-Churn-Analysis/
│
├── SQL/
│   ├── database_setup.sql
│   ├── data_cleaning.sql
│   ├── exploratory_analysis.sql
│   └── views.sql
│
├── PowerBI/
│   └── Customer_Churn_Dashboard.pbix
│
├── Python/
│   ├── churn_prediction.py
│   ├── model_training.py
│   └── requirements.txt
│
├── Data/
│   └── README.md
│
├── Images/
│   ├── executive-summary.png
│   ├── churn-analysis.png
│   ├── churn-reasons.png
│   └── churn-prediction.png
│
└── README.md
```

---

# 📚 Project Documentation

I also documented the project in detail on Medium.

### Part 1 — Churn Analysis & Power BI

**What If Your Customers Are Quietly Leaving…?? (Part 1)**

👉 [Read Part 1 on Medium](https://medium.com/@DhanashriPetkar/what-if-your-customers-are-quietly-leaving-part-1-ac32ab0e06b9)

This part covers:

* Customer churn fundamentals
* Project objectives
* SQL Server setup
* Data exploration
* Data cleaning
* SQL views
* Power BI transformations
* DAX measures
* Dashboard development
* Demographic analysis
* Geographic analysis
* Churn reasons
* Service analysis

---

### Part 2 — Churn Prediction & Machine Learning

**What If Your Customers Are Quietly Leaving…?? (Part 2)**

👉 [Read Part 2 on Medium](https://medium.com/@DhanashriPetkar/what-if-your-customers-are-quietly-leaving-part-2-653d7064fb0f)

This part focuses on:

* Preparing data for Machine Learning
* Feature encoding
* Train-test split
* Random Forest
* Model evaluation
* Feature importance
* Future churn prediction
* Predicted churners
* Power BI prediction dashboard

---

# 🎯 Key Learning Outcomes

Through this project, I worked with an end-to-end data analytics workflow involving:

* SQL-based data preparation
* ETL concepts
* Data cleaning
* Exploratory data analysis
* Power BI data transformation
* DAX measures
* Interactive dashboard design
* Customer segmentation
* Churn analysis
* Classification Machine Learning
* Random Forest
* Model evaluation
* Feature importance
* Predictive analytics

The biggest takeaway?

> **Data analysis isn't just about finding numbers. It's about turning raw data into insights that can lead to better decisions.**

---

# 🚀 Future Improvements

Some possible improvements for this project include:

* Experimenting with other classification algorithms
* Hyperparameter tuning
* Improving model performance
* Adding customer-level churn probability scores
* Building automated prediction pipelines
* Adding more advanced customer segmentation
* Creating real-time or scheduled dashboard updates

---

# 👩‍💻 About Me

**Dhanashri Petkar**

Data Science Graduate | Machine Learning Freelancer

I enjoy working with data analytics, Machine Learning, SQL, Power BI and data visualization — and probably overthinking datasets more than necessary. 😭📊

---

⭐ If you found this project useful, consider giving the repository a **star**!

Feel free to explore the project, raise an issue, or connect with me for collaboration.

