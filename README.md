![GitHub Banners (3)](https://github.com/user-attachments/assets/d5eeed72-48bc-4126-b0d9-96076e237bb3)

# RFM Analysis on Customer Sales Data

This project performs RFM Analysis on customer transaction data to segment customers based on their purchasing behavior. RFM or Recency-Frequency-Monetary analysis, is a framework developed by the direct mailers back in the 1970s due to cost associated with emailing which was expensive and they wanted to give virtual scores eg: from one to five to their recipients based on different customer groups in terms of how recently they’ve made a purchase (Recency), how often they make purchases (Frequency), and how much money they spend (Monetary). 

In recent times, the biggest retailers in the world are using the RFM model to identify high-value customers, infrequent buyers, and those likely to churn.

---

## Project Objectives

- Load and preprocess sales transaction data
- Calculate **Recency**, **Frequency**, and **Monetary** metrics
- Assign RFM scores to each customer using quantile-based scaling
- Create meaningful customer segments (Platinum Plus, Platinum, Gold, Silver, Bronze)
- Visualize the distribution of customer segments

---


## Business Insights

#### 1. Identify high-value, repeating customers from the observation
-   Customer with ID **12347** is a High-Value customer with high recency, high frequency purchase, and high spending record
#### 2. Identify low-valued infrequent customers most likely to churn
-   Customer with ID **12346** is a customer who is more likely to churn with distant recency, infrequent purchase, and a low spending record

![image](https://github.com/user-attachments/assets/46ec5a47-3f37-485f-8e4f-51f562858659)


---

## Tools & Technologies

- **Python**: pandas, numpy, matplotlib
- **Google Colab**: notebook development and execution

---

## Dataset

The dataset includes transactional data such as invoice date, customer ID, quantity, and unit price. This dataset contains all purchases made for an online retail company based in the UK during an eight-month period, collected from  [Kaggle](#https://www.kaggle.com/datasets/vijayuv/onlineretail).

The dataset is a cleaned version of online retail transactions and contains:
Extracting necessary columns for RFM Analysis by taking:
-   **CustomerID:** The grouping column for various aggregations
-   **InvoiceDate:** Day difference between the  date of invoice generation and the date of analysis
-   **InvoiceNo:** Number of Invoices generated for a customer
-   **Sales:** Total sales generated for a customer

---

## Methodology

### 1. Data Preprocessing
- Mounted Google Drive to access the dataset
- Calculated `Sales = Quantity * UnitPrice`

### 2. Extracted Columns for RFM
- Selected: `CustomerID`, `InvoiceDate`, `InvoiceNo`, `Sales`
- Defined the analysis date as one day after the latest transaction

### 3. RFM Metric Calculation
- **Recency**: Number of days since last purchase
- **Frequency**: Total invoices per customer
- **Monetary**: Total spend per customer

### 4. RFM Scoring
- Used `pd.qcut()` to assign scores from 1 to 5:
  - Recency: Lower value indicates a more recent purchase
  - Frequency & Monetary: Higher value indicates better performance

### 5. Customer Segmentation
- Computed overall `RFMScore` by summing individual R, F, M scores
- Assigned customer segments:
  - Platinum Plus (14+)
  - Platinum (11–13)
  - Gold (8–10)
  - Silver (5–7)
  - Bronze (<5)

### 6. Visualization:
- The business has almost an equal number of customers in the Silver and the Gold segments
- Comparatively fewer customers from the Platinum and the Platinum Plus segments, which is desirable
- Also, the least number of customers from the Bronze segment is a positive indication for the business

![image](https://github.com/user-attachments/assets/22254068-2562-49ef-90c1-c4a057646670)


---

## Suggestions

The suggestions to the business will be:
- Retain high-value customers through loyalty programs
- Re-engage low-activity customers with targeted offers
- Personalize marketing strategies based on customer behavior
