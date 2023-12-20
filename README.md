# Sales-Insights-of-Data-Analysis-AtliQ-Hardware
## Introduction
AtliQ Hardware, based in Delhi, India, is a leading supplier of computer hardware and peripherals with a widespread presence across India. The company faced challenges in tracking sales in a dynamically growing market, leading to a decline in overall sales. The Sales Director encountered difficulties obtaining comprehensive insights from regional managers, relying on verbal communication without factual proof. To address this, the company aimed to unlock sales insights through data analysis, supporting data-driven decision-making and reducing manual data gathering time.

## AIMS Grid
### Purpose:
*   Unlock sales insights for decision support and automate data gathering.
### Stakeholders:
*   Sales Director
*   Marketing Team
*   Customer Service Team
*   Data and Analytics Team
*   IT
### End result:
*   An automated dashboard providing quick and latest insights for data-driven decision-making.
### Success Criteria:
*   Dashboard uncovering sales order insights with the latest data.
*   10% cost saving of total spend proven by the sales team.
*   20% business time saved by stopping manual data gathering.
  ## Data Analysis using MySQL
### Importing Data to MySQL Workbench
*   Import data from the provided MySQL dump file (**'db_dump.sql'**) for further analysis.
### Analysis of Data
Identify and address garbage values in the **'sales.market'** and **'sales.transactions tables'**.
Perform various SQL statements to extract insights, including customer records, total number of customers, transactions for specific markets, distinct product codes, and revenue analysis by year and month.
## Data Cleaning and ETL (Extract, Transform, Load)
### Steps:
*   Connect MySQL database with Power BI Desktop.
*   Load data into Power BI Desktop from MySQL.
*   Transform data using Power Query for data cleaning and ETL operations.
  ![Scatter digram](https://github.com/RatnaSingh007/Sales-Insights-of-Data-Analysis-AtliQ-Hardware/assets/146417100/bef6bb09-4abe-445a-9d97-53e34e2b869c)

### Data Cleaning Tasks:
*   Refine the **'sales.market'** table by filtering out null values.
*   Filter negative and zero values in the **'sales.transactions table'**.
*   Convert USD values to INR for accurate representation.
*   Identify and compute total USD values for further analysis.
## Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

The sales insights data tables as show below:
![Scatter digram2](https://github.com/RatnaSingh007/Sales-Insights-of-Data-Analysis-AtliQ-Hardware/assets/146417100/64ae199a-4fc4-4ef8-af01-14ce29ce425d)

  
## Data Analysis (DAX)
### Key Measures:
```
Profit Margin % = DIVIDE ([Total Profit Margin], [Revenue],0)
Profit Margin Contribution % = DIVIDE ([Total Profit Margin], CALCULATE ([Total Profit Margin], ALL ('sales products'), ALL ('sales customers'), ALL ('sales markets')))
Revenue = SUM ('sales transactions'[sales_amount])
Revenue Contribution % = DIVIDE([Revenue], CALCULATE([Revenue], ALL ('sales products'), ALL ('sales customers'), ALL ('sales markets')))
Revenue LY = CALCULATE([Revenue], SAMEPERIODLASTYEAR ('sales date'[date]))
Sales quantity = SUM ('sales transactions'[sales_qty])
Total Profit Margin = SUM ('Sales transactions'[Profit_Margin])
Profit Target:
Profit Target1 = GENERATESERIES (-0.05, 0.15, 0.01)
Profit Target Value = SELECTEDVALUE ('Profit Target1'[Profit Target])
Target Diff = [Profit Margin %]-'Profit Target1'[Profit Target Value]
```
## Power BI Visualization: Key Insights Dashboard

The Key Insights Dashboard for AtliQ Hardware is designed to provide a quick yet comprehensive view of sales performance. Featuring a Revenue Trend and Sales Quantity Trends chart, stakeholders can easily track revenue and product quantity dynamics over time. The Top 5 Customers section highlights key contributors to revenue, while Revenue by Product Code offers insights into individual product performance. Geographical perspectives are provided through Sales Quantity and Revenue by Markets charts. Cards display key metrics like total Revenue and Sales Quantity, and a slicer enhances interactivity for customized data analysis. The visually appealing dark canvas background adds clarity to the presented information, enabling informed decision-making.

## Conclusion
The created dashboard provides comprehensive insights into AtliQ Hardware's sales performance. Key metrics such as Revenue, Sales Quantity, Revenue and Sales by Market, and Revenue Trend are visually presented. The dashboard allows filtering by YEAR and MONTH, enabling the Sales Director to quickly assess sales performance and make informed decisions to address declining sales.
For the complete set of SQL commands and DAX queries, refer to the respective sections in this report.








