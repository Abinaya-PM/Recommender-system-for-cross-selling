# **Recommender System for Cross-Selling**    

## **Overview**  

This project develops a cross-selling recommendation system for e-commerce using a clustering-based method. We adapt the l-CrossSold algorithm and enhance its recommendation capabilities by incorporating user demographics in addition to product similarities and profit margins.  

The key goal is to improve traditional recommendation systems by ensuring higher accuracy and relevance in product recommendations.  

---

## **Key Features**  

🔹 **Personalized Recommendations** – Tailored cross-selling suggestions based on customer purchase history and demographic data.  
🔹 **Clustering-Based Approach** – Uses a clustering-based method to group products for improved cross-selling insights.  
🔹 **Enhanced l-CrossSold Algorithm** – Incorporates user demographics to refine the recommendation process.  
🔹 **Optimized Data Processing** – Handles missing values, integrates raw data, and transforms it for effective analysis.  
🔹 **Evaluation Metrics** – Model evaluated using F1-score (achieved 0.41) to measure precision and recall.  

---

## **Dataset**  

 **Dataset Used:** Adventure Works Dataset (sourced from Kaggle)  
🔹 Contains sales transactions, product details, customer demographics, and purchase history.  

## **Data Preprocessing Steps:**
- **Handling Missing Values** (e.g., filling missing gender data with mode).  
- **Feature Engineering** – Extracted age from birthdate and encoded categorical variables.  
- **Data Normalization** – Standardized purchase and order frequency values.  

---

## **Methodology**  

### **1️. Data Processing & Transformation**  
🔹 **Data Integration** – Merged transactional data with customer and product details.  
🔹 **Exploratory Data Analysis (EDA)** – Identified patterns, missing values, and feature correlations.  
🔹 **Data Preprocessing** – One-hot encoding for categorical attributes (e.g., Gender, Country, Region).  

### **2️. Cross-Sold Score Calculation**  
🔹 **Point of Sale (POS) Matrix** – Captures order quantity per product per customer.  
🔹 **Product Frequency-Inverse Transaction Frequency (PF-ITF) Matrix** – Adjusts for product popularity variations.  
🔹 **Product Similarity Calculation** – Computes **cosine similarity** between products.  
🔹 **User Similarity Calculation** – Measures similarity between customers based on demographics.  
🔹 **Profit Component Calculation** – Determines profitability of recommendations.  
🔹 **Final Cross-Sold Score (CSS) Formula:**  

```
CSSij = α(1 - (ci + cj) / (pi + pj)) + (1 - α) * δij * δuv
```

- **δij** → Product similarity  
- **δuv** → User similarity  
- **α (alpha)** → Balances profit margin and similarity scores  

### **3️. Clustering & Recommendation Generation**  
🔹 **Clustering-Based Method** – Groups products based on similarity to form clusters.  
🔹 **User-Specific Product Recommendations** – Products recommended from the same cluster as the user’s selected product.  
🔹 **Dynamic Cross-Selling Suggestions** – Real-time filtering based on user basket contents.  

### **4️. Model Evaluation**  
🔹 **Precision at K** – Measures how many recommended products are relevant.  
🔹 **Recall Score** – Identifies the percentage of relevant items retrieved.  
🔹 **F1-Score (Achieved: 0.41)** – Balances precision and recall for optimal recommendations.  

---

## **Tech Stack & Libraries Used**  

🔹 **Programming Language:** Python  
🔹 **Data Processing:** Pandas, NumPy  
🔹 **Machine Learning & Similarity Metrics:** scikit-learn (cosine similarity, clustering)  
🔹 **Graph Processing & Clustering:** NetworkX, Agglomerative Clustering  
🔹 **Evaluation Metrics:** Precision, Recall, F1-score  

---

## **Results & Insights**  

🔹 **Cross-Sold Score Matrix** – Determines product compatibility based on purchase trends & user demographics.  
🔹 **Product Clusters Identified** – 12 distinct clusters formed using Agglomerative Clustering.  
🔹 **Personalized Recommendations Generated** – Users receive suggestions tailored to their purchase history.  
🔹 **F1-score Achieved: 0.41** → Indicates a well-balanced model performance in precision & recall.  

---

## **Challenges & Limitations**  

🔹 **Data Quality Issues** – Incomplete customer data affects recommendation accuracy.  
🔹 **Scalability Concerns** – Large datasets may require optimized computation.  
🔹 **Cold Start Problem** – New customers with no purchase history receive less personalized recommendations.  
🔹 **Dynamic Preferences** – Customers' buying habits change over time, requiring adaptive learning.  

---

## **Future Enhancements** 

🔹 **Real-Time Data Integration** – Connect live transactional data for real-time recommendation updates.  
🔹 **Deep Learning Models** – Explore Neural Collaborative Filtering (NCF) for improved recommendations.  
🔹 **Hybrid Approach** – Combine collaborative filtering & content-based filtering to enhance recommendation quality.  

---
