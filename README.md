# DataAnalystProject-Sales_insights


### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

2. Show total number of customers

    `SELECT count(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

4. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

5. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table

    `SELECT t.*, d.* FROM transactions as t INNER JOIN date as d ON t.order_date=d.date where d.year=2020;;`

7. Show total revenue in year 2020,

    `SELECT SUM(t.sales_amount) FROM transactions as t INNER JOIN date as d ON t.order_date=d.date where d.year=2020 and t.currency="INR" or t.currency="USD";`
	
9. Show total revenue in year 2020, January Month,

    `SELECT SUM(t.sales_amount) FROM transactions as t INNER JOIN date as d ON t.order_date=d.date where d.year=2020 and d.month_name="January" 
    and (t.currency="INR" or t.currency="USD");`

10. Show total revenue in year 2020 in Chennai

    `SELECT SUM(t.sales_amount) FROM transactions as t INNER JOIN date as d ON t.order_date=d.date where d.year=2020 and t.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create Final_sales_amount

`= Table.AddColumn(#"Filtered Rows", "Final_sales_amount", each if [currency]="USD" then [sales_amount]*81 else [sales_amount])`


