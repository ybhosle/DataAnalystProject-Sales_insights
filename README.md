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



Screenshot of Power BI Dashboard
================================

![image](https://user-images.githubusercontent.com/107353405/216251000-9dcbdae5-0102-44a2-b2b2-50a823aecd9e.png)


![image](https://user-images.githubusercontent.com/107353405/216251159-99137d0c-dffa-4fac-a597-0e0a129410fa.png)


![image](https://user-images.githubusercontent.com/107353405/216251195-f9d882c4-a1d7-4e46-aacf-8bcee30e5e08.png)


