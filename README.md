# *Supply Chain Optimization*

## Table of Contents

- [Data Cleaning/Preparation](data-cleaning?preparation)
- [Exploratory Data Analysis](exploratory-data-analysis)
- [Results and Findings](results-and-findings)
- [Recommenadtion](recommendation)


### **Project Overview**
---

This project aims to analyze the logistics network of a global supply chain management company, focusing on warehousing and last-mile delivery services. The company's Operations and Business Intelligence teams have recently pinpointed several key issues in the supply chain, including:

- Supplier performance inconsistencies
- Fluctuating revenue trends

This project seeks to provide valuable insights to address these challenges and optimize the company's logistics operations.

### **Data Sources**

Customers.csv,  suppliers.csv, inventory.csv, orders.csv, inventory.csv and products.csv

###  **Tools Used**
- Excel - Data Cleaning
- SQL Server - Data Analysis 
- PoWer BI - Creating reports

### Data Cleaning/Preparation

The following were Performed at the initial data preparation phase
1. Data Loading and Inspection
2. Handling Missing Value
3. Data cleaning and formatting

### Exploratory Data Analysis

This invloves exploring the data set to answer key questions such as;

- Which product is the best-selling products
- What is the Trend analysis for total revenue and average delivery time
- What is the Average Delivery Time per category

<img width="434" height="152" alt="Image" src="https://github.com/user-attachments/assets/d09867a3-e32d-4ce8-9d2a-15673511145f" />

### Data Analysis

Includes some interesting code/features worked with.

``` DAX
Total_revenue = SUMX(orders,orders[Quantity]*related(Products[Price]))
```
``` DAX
Weekend = SWITCH(
    TRUE(),
    CalendarTable[Day] = "Sat", "Y",
    CalendarTable[Day] = "Sun", "Y",
    "N"
)
```
``` SQL
BULK INSERT Customers
FROM 'C:\path\to\your\customers.csv'
WITH (
    FIRSTROW = 2,
    FIELDTERMINATOR = ',',
    ROWTERMINATOR = '\n',
)
```
### **Results and Findings**
The results of the analysis can be summarised as below;
1. Product 72 is the Best performing product
2. Initially, as average delivery time decreases, total revenue increases. This makes sense, as faster deliveries often lead to higher customer satisfaction and potentially more business. However, from 2022 onwards, there's a shift: as average delivery time increases, total revenue decreases.
3. As the volume of transactions grows, the existing Customers may struggle to keep up with the demand, with the number of suppliers remaining unchanged.



![bar_plot](https://github.com/user-attachments/assets/e0800736-8e54-474a-b9eb-8ded6a55dfa8)

### **Recommenadtion**

Based on the result, the following are recommended
1. Onboarding new suppliers to distribute the workload
2. Implementing process improvements to support existing suppliers
3. Automated inventory alert for low stock levels
4. Prioritize restocking schedules respecialy for the top performing products

### **Limitations**

I had to remove null from supplier table because it would have affected the accuracy of my report

   


