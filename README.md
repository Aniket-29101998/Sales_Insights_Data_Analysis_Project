**Sales Insight Data Analysis Project**

**Table of Contents**

Overview
Motivation
Objectives
Project Structure
Tools and Technologies
Installation and Setup
Usage
Contributing
License
Contact

**Overview**
The Sales Insight Data Analysis Project is aimed at providing comprehensive insights into sales data to help businesses make data-driven decisions. This project involves the extraction, transformation, and analysis of sales data from various sources, with the ultimate goal of uncovering patterns, trends, and actionable insights.

**Motivation**
In today’s competitive business landscape, understanding sales trends and customer behavior is crucial for driving growth and profitability. This project was motivated by the need to empower decision-makers with actionable insights derived from sales data. By leveraging data analysis techniques, businesses can optimize their sales strategies, identify growth opportunities, and enhance customer satisfaction. This project seeks to bridge the gap between raw data and meaningful insights that can significantly impact a company’s success.

**Objectives**
**Data Collection**: Gather sales data from various sources such as CRM systems, e-commerce platforms, and transactional databases.
**Data Cleaning**: Perform data cleaning and preprocessing to ensure the accuracy and consistency of the data.
**Exploratory Data Analysis (EDA)**: Analyze the data to understand underlying patterns, trends, and relationships.
**Data Visualization**: Create visual representations of the data to convey insights in an intuitive manner.
**Sales Performance Metrics**: Calculate key sales performance metrics such as revenue growth, conversion rates, and customer segmentation.
**Predictive Analytics**: Implement predictive models to forecast future sales trends and customer behavior.
Project Structure

**The project is organized into the following sections:**

**Data**: Contains the raw sales data files and any supplementary data used in the analysis.
**Scripts**: Includes all scripts used for data cleaning, transformation, and analysis.
**Notebooks**: Jupyter notebooks that document the exploratory data analysis and any model development processes.
**Visualizations**: Charts, graphs, and dashboards generated from the data.
**Reports**: Summarized reports and presentations that highlight the key findings and insights.

**Tools and Technologies**
Programming Language: Python
Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
Database: SQL for querying and managing data
Visualization Tools: Tableau, Power BI, or Matplotlib
Version Control: Git/GitHub for version control and collaboration
Installation and Setup
To set up the project locally, follow these steps:

Data Exploration: Use the notebooks to explore and understand the sales data.
Generate Insights: Run the analysis scripts to generate insights from the data.
Visualize Results: Use the visualization tools to create charts and dashboards.
Forecast Sales: Apply predictive models to forecast future sales trends.
Contributing
If you would like to contribute to this project, please follow these steps:

Fork the repository on GitHub.
Create a new branch for your feature or bug fix.
Submit a pull request once your changes are complete.

### Instructions to setup mysql on your local computer

1. Follow step in this video to install mysql on your local computer
https://www.youtube.com/watch?v=WuBcTJnIuzo

1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it as per instructions given in the tutorial video

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

Contact
For any inquiries or feedback, please contact:

Aniket Goyal
Email: goyal26aniket@gmail.com
LinkedIn: www.linkedin.com/in/aniket-goyal234


