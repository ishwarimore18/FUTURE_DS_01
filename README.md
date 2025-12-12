## **Future Interns: Data Science & Analytics Internship**

# **📊 Task 1 – E-Commerce Sales Dashboard (Power BI)**

### **🚀 Project Overview**
#### ◆ This repository contains the completed work for **Task 1** of the **Future Interns – Data Science & Analytics Internship**.  
#### ◆ The objective was to analyze e-commerce sales data and build an **interactive Business Sales Dashboard** using **Power BI**.  
#### ◆ The dashboard provides insights into sales trends, customer behavior, and product performance using visually clean KPIs and charts.
---
### **📁 Dataset Used**
#### The dataset was downloaded from **Kaggle – Online Retail II Dataset**, consisting of UK-based e-commerce transactions.
Files available in the downloaded ZIP:
- `online_retail_II_2009-2010.csv`
- `online_retail_II_2010-2011.csv`
- `online_retail_II.xlsx` *(Not used)*
#### ✔ For this task, only the **two CSV files** were used.
---
### **🛠️ Data Cleaning & Transformation (Power Query)**
After loading both CSV files, the following steps were executed:
### **1️⃣ Combine Datasets**
  -  Imported both CSV files into Power BI  
  -  **Appended** them to create a single consolidated table
### **2️⃣ Data Filtering & Cleaning**
Removed rows where:
- **Quantity ≤ 0**  
- **Invoice starts with “C”** (cancellation entries)  
- **CustomerID is null**  
- **Description is null**  
- **Price ≤ 0** 
-  Additional cleaning: Trimmed extra spaces in text columns
### **3️⃣ Created Custom Columns**
- **Sales = Quantity × Price**  
- Removed numbers from Description using:  
```
Text.Remove([Description], {"0".."9"})
```
- Replaced `"cm"` with blank  
- Added date-based columns:
  - Year  
  - Month  
  - Month Name  
  - Quarter  
- Added **Price Range** classification:
```DAX
Price Range =
SWITCH(
    TRUE(),
    'Sales Combined'[Price] < 20, "Budget",
    'Sales Combined'[Price] < 200, "Standard",
    "Premium"
)
```
### **4️⃣ DAX Measures Created**
- Total Sales  
- Total Quantity Sold  
- Total Invoices  
- Total Customers  
- Average Order Value (AOV)  
- Invoice Sales  
---
### **📊 Dashboard Visuals Created (Power BI Report View)**
### ✔ **KPI Cards**
- Total Sales  
- Total Invoices  
- Total Customers  
- Total Quantity Sold  
-  Average Order Value (AOV)  
### ✔ **Charts Used**
- 📅 **Yearly Quantity Sold**  
- 📈 **Monthly Sales Trend**  
- 🛒 **Top 10 Best-Selling Products**  
- 👥 **Top 10 Customers by Revenue**  
- 💰 **Average Order Value by Month**  
- 🎯 **Sales by Price Range** (Donut Chart)
### ✔ **Filters (Slicers)**
- Country  
- Quarter  
---
### **📸 Dashboard Preview**
<img width="1084" height="681" alt="DS 1_1" src="https://github.com/user-attachments/assets/4142bd5e-d68b-4aa4-b4ad-ad3e22996ba3" />

---
### **🏷️ Skills & Tools**

| Category                | Skills / Tools                                      |
|-------------------------|----------------------------------------------------|
| Data Analysis     | Power Query, DAX, Data Cleaning, Data Transformation |
| Visualization      | Power BI Dashboard Design, Charts, KPIs, Slicers  |
| Business Skills     | Business Storytelling, Insights Extraction        |
| Tools              | Power BI Desktop, Microsoft Excel, Kaggle CSVs    |
---
### **📂 Repository Structure**
```
FUTURE_DS_01/
│
├── README.md
├── DS_01.pbix
├── datasets/
│   ├── datasets.zip
└── images/
    └── DS 1_1.png
    └── DS 1_2.png
    └── DS 1_3.png
    └── DS 1_4.png
```
---
### **📦 Dataset Extraction Instructions**
To access and use the dataset in this project:
1. Open the **`datasets/`** folder in this repository  
2. Download the file: **`datasets.zip`**  
3. Extract the ZIP file to your system  
4. After extraction, you will see the following CSV files:
  - online_retail_II_2009-2010.csv
  - online_retail_II_2010-2011.csv
  
These two CSV files were used for all data cleaning, transformation, and dashboard creation in Power BI.
