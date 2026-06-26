# Data Cleaning and Quality Assessment Project

## Problem Summary

This project focuses on cleaning, validating, and analyzing an e-commerce order dataset using Microsoft Excel. The objective is to improve the quality, consistency, and reliability of the data by applying standard data cleaning techniques, implementing business rules, identifying data quality issues, and generating meaningful summaries through pivot tables.

---

# Dataset Description

The dataset contains transactional order information for an online retail business. It includes customer details, product information, sales values, discounts, shipping details, payment status, and order status.

Main columns include:

* Order ID
* Order Date
* Ship Date
* Customer Name
* Segment
* Region
* State
* City
* Category
* Sub Category
* Quantity
* Unit Price
* Cost
* Sales
* Discount
* Ship Mode
* Payment Status
* Order Status

---

# Tools Used

* Microsoft Excel
* Excel Formulas
* Pivot Tables
* Data Validation
* Conditional Formatting
* Sorting and Filtering
* Find and Replace
* Flash Fill
* Text Functions

---

# Cleaning Steps Performed

### 1. Raw Data Preservation

* Original dataset stored as `raw_orders.xlsx`
* Cleaning performed separately in `cleaned_orders.xlsx`

### 2. Text Cleaning

The following columns were standardized:

* Customer Name
* Segment
* Region
* State
* City
* Category
* Sub Category
* Ship Mode
* Payment Status
* Order Status

Cleaning included:

* Removing leading spaces
* Removing trailing spaces
* Removing extra spaces
* Standardizing capitalization
* Correcting inconsistent category names
* Removing unwanted special characters where applicable

Functions used:

* TRIM()
* SUBSTITUTE()
* PROPER()
* Find & Replace
* Flash Fill

---

### 3. Date Cleaning

Both Order Date and Ship Date were cleaned and converted into a consistent date format.

The following issues were identified:

* Missing dates
* Invalid date values
* Text entries instead of dates
* Ship dates occurring before order dates

Shipping delay was calculated using:

Shipping Delay = Ship Date − Order Date

---

### 4. Duplicate Handling

Duplicate analysis included:

* Exact duplicate rows
* Duplicate Order IDs
* Conflicting duplicate records

Exact duplicate records were removed.

Conflicting duplicate Order IDs were retained and flagged for manual review.

---

### 5. Business Rules Applied

The following business rules were implemented:

* Missing Region values were replaced with **Unknown**
* Missing Ship Mode values were replaced with **Unknown**
* Missing Discount values were replaced with **0** only when other sales fields were valid
* Negative discounts were flagged as invalid
* Discounts above the acceptable range were flagged
* Ship Date before Order Date was marked invalid
* Cancelled orders excluded from completed sales summaries
* Failed payment orders excluded from completed sales summaries
* Refunded orders summarized separately

---

### 6. Calculated Columns

The following calculated columns were added:

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

Formulas used included:

* Sales = Quantity × Unit Price × (1 − Discount)
* Profit = Calculated Sales − Cost
* Profit Margin = Profit ÷ Sales

---

# Business Rules Applied

| Rule                        | Action Taken                  |
| --------------------------- | ----------------------------- |
| Missing Region              | Filled with Unknown           |
| Missing Ship Mode           | Filled with Unknown           |
| Missing Discount            | Replaced with 0 when valid    |
| Negative Discount           | Flagged as Invalid            |
| Discount Above Limit        | Flagged as Invalid            |
| Ship Date Before Order Date | Flagged as Invalid            |
| Cancelled Orders            | Excluded from completed sales |
| Failed Payments             | Excluded from completed sales |
| Refunded Orders             | Summarized separately         |

---

# Summary of Data Quality Issues Found

The dataset contained several quality issues including:

* Missing values
* Duplicate records
* Duplicate Order IDs
* Invalid dates
* Incorrect shipping dates
* Missing discounts
* Invalid discount values
* Inconsistent text formatting
* Mixed date formats
* Missing region information
* Missing shipping mode values

All identified issues were cleaned or flagged appropriately.

---

# Summary of Final Pivot Reports

The following Pivot Tables were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled and Failed Orders by Region
6. Monthly Sales Trend

Several pivot tables were sorted and filtered for better readability.

---

# Key Business Insights

* Certain regions generated significantly higher sales than others.
* Technology and Furniture were among the highest revenue-generating categories.
* Standard Class was the most frequently used shipping mode.
* Consumer customers contributed the highest number of orders.
* Cancelled, refunded, and failed payment orders reduced realized revenue.
* Profit margins varied considerably across customer segments and product categories.
* Seasonal trends were visible in monthly sales performance.

---

# Assumptions and Limitations

## Assumptions

* Discount values are valid only within the accepted business range.
* Missing discounts were treated as zero only when sales-related fields were available.
* Unknown regions and shipping modes were retained instead of deleting records.
* Conflicting duplicate Order IDs require manual verification.

## Limitations

* Some business rules required assumptions due to incomplete documentation.
* Conflicting duplicate records were flagged rather than automatically removed.
* Invalid source data may still require manual verification.
* Results depend on the quality of the original dataset.

---

# Screenshots Included

The repository includes the following screenshots:

* raw_data_preview.png
* cleaned_data_preview.png
* pivot_summary_1.png
* pivot_summary_2.png

These screenshots demonstrate the original dataset, cleaned dataset, and major pivot table summaries.

---


# Conclusion

The dataset was successfully cleaned, validated, and standardized according to the specified business rules. Data quality issues were documented, calculated fields were created, duplicate records were analyzed, and multiple pivot reports were generated to support business decision-making. The final dataset is more accurate, consistent, and suitable for reporting and further analysis.
