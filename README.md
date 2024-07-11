# RFM-Ecommerce


**Customer RFM Analysis for E-commerce**

**Context**

I conducted an analysis for an e-commerce company to calculate the Recency, Frequency, and Monetary (RFM) indicators for its customers. RFM analysis is a key marketing technique used to segment customers based on:

**Recency (R):** Time since the customer's last purchase (in days).

**Frequency (F):** Number of purchases made by the customer.

**Monetary (M):** Average amount spent by the customer per purchase.

**Objective**

My objective was to prepare a dataset for data modeling using a CSV file provided by the company, which contains purchase information from 37 countries. I developed a Python script to generate an output CSV file containing customer identification and RFM metrics.

**Data Structure**

The dataset contains the following columns:

**CustomerID:** Customer identification

**Description:** Product description

**InvoiceNo:** Invoice number

**StockCode:** Product code

**Quantity:** Quantity of product purchased

**InvoiceDate:** Invoice date

**UnitPrice:** Unit price of the product

**Country:** Customer's country

**Challenges and Solutions**

**Step 01: Data Inspection**

First, I read the CSV file and inspected the data. I used the describe() method to understand the data distribution and checked the data types present in the dataset. This initial analysis was crucial to identify potential issues such as missing values and incorrect data types.

**Step 02: Handling Missing Values**

I identified and removed observations with missing values in the CustomerID column using isna() and dropna().

**Step 03: Validating Prices and Quantities**

I filtered the data to check and remove records with unit prices (UnitPrice) and quantities (Quantity) less than or equal to zero. Ensuring data integrity was essential for accurate analysis.

**Step 04: Removing Duplicates**

Using duplicated(), I identified and removed duplicate rows in the dataset to avoid distortions in the analysis.

**Step 05: Correcting Data Types**

I corrected the data types of the CustomerID and InvoiceDate columns to int and datetime, respectively. This facilitated subsequent operations and calculations.

**Step 06: Handling Outliers**

I identified and removed extreme outliers, such as item quantities exceeding 10,000 or unit prices over 5,000. These values were considered errors.

**Step 07: Creating Additional Column**

I created a new column (TotalPrice) representing the total purchase value, calculated as Quantity multiplied by UnitPrice.

**Step 08: Calculating Last Purchase Date**

I calculated the last purchase date in the dataset using the max() function. This date served as the basis for calculating purchase recency.

**Step 09: Data Visualization**

To enrich the analysis, I plotted graphs showing:

**1)Top 10 countries by sales value.**

**2)Top 10 best-selling products.**

**3)Total sales value per month.**

**4)Total sales value per month and by country (considering only the top 10 countries).**

**5)Step 10: Calculating RFM Metrics**

I grouped the data by customer and invoice number (InvoiceNo) and calculated the RFM metrics:

**Recency (R):** The number of days between the customer's last purchase and the last purchase in the dataset.

**Frequency (F):** The number of purchases made by the customer.

**Monetary (M):** The average purchase value of the customer.

**Results**

The results of the RFM analysis were exported to a CSV file containing the RFM metrics for each customer, providing valuable insights into customer purchase behavior.
