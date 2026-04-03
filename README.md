# Danny-s-Diner-SQL-Case-Study
# Introduction
Danny is passionate about Japanese cuisine, and in early 2021, he decided to take a bold step by opening a small restaurant called Danny’s Diner, serving his three favorite dishes: sushi, curry, and ramen.

After a few months of operation, the restaurant began collecting basic transactional data. However, Danny lacked the insights needed to understand his customers, optimize his menu, and make informed business decisions.

To help the restaurant stay afloat, I analyzed the available data using SQL to uncover key trends and actionable insights.

# Business Questions
 1. What is the total amount each customer spent at the restaurant?
 2. How many days has each customer visited the restaurant?
3. What was the first item from the menu purchased by each customer?
4. What is the most purchased item on the menu and how many times was it purchased by all customers?
5. Which item was the most popular for each customer?
6. Which item was purchased first by the customer after they became a member?
7. Which item was purchased just before the customer became a member?
8. What is the total items and amount spent for each member before they became a member?
9. If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
10. In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi  how many points do customer A and B have at the end of January?

# About The Dataset
The dataset for Danny’s Diner consists of three core tables that capture customer behavior, menu details, and membership information.
 1. sales Table
    The Sales table records all customer transactions at the individual level. Each row represents a purchase and includes:
    - customer_id – unique identifier for each customer
    - order_date – the date the purchase was made
    - product_id – the item purchased
   
  2. Menus Table
     The Menu table contains details about each product available at the restaurant. It includes:
     - product_id – unique identifier for each menu item
     - product_name – name of the dish (e.g., sushi, curry, ramen)
     - price – cost of each item

  3. Members Table
     The Members table captures information about customers who joined the loyalty program. It includes:
     - customer_id – unique identifier for each customer
     - join_date – the date the customer became a member

# Tools Used : Postgresql

# Solution
## Q1 - Total Amount Spent by Each Customer

| Customer ID | Total Spent ($) |
|-------------|-----------------|
| A           | 76              |
| B           | 74              |
| C           | 36              |

Customer A is the top spender, followed by B, with C spending the least.

## Q2 - Number of Days Each Customer Visited the Restaurant

| Customer ID | Days_Visited       |
|-------------|--------------------|
| A           | 4                  |
| B           | 6                  |
| C           | 2                  |

Customer B visited the restaurant the most (6 days), followed by Customer A (4 days), while Customer C had the fewest visits (2 days).

## Q3 - First Item Purchased by Each Customer

| Customer ID | Product Name         |
|-------------|----------------------|
| A           | curry                |
| A           | sushi                |
| B           | curry                |
| C           | ramen                |
| C           | ramen                |

Customer A purchased two different items (curry and sushi), Customer B purchased one item (curry), Customer C purchased two items (ramen) on the first day.

## Q4 - Most Purchased item on the menu

| Product_Name | Orders             |
|------------- |--------------------|
| ramen        | 8                  |

most Purchased item is ramen, which was purchased eight times.

## Q5 - Most popular item for customer

| Customer_Id | Product_Name       |
|-------------|--------------------|
| A           | ramen              |
| B           | ramen              |
| B           | sushi              |
| B           | curry              |
| C           | ramen              |

Ramen is the most popular item for customer A and C. For customer B all three items were purchased the same number of times.

## Q6 - Item was purchased first by the customer after they became a member

| Customer_Id | Product_Name         |
|-------------|----------------------|
| A           | curry                |
| B           | sushi                |

Customer A Purchased ramen as the first product after joining, while Customer B purchased Sushi.

## Q7 - item was purchased just before the customer became a member

| Customer_Id | Product_Name         |
|-------------|----------------------|
| A           | sushi                |
| A           | curry                |
| B           | curry                |

Both customers got curry before they joined while customer A purchased sushi.

## Q8 - the total items and amount spent for each member before they became a member

| Customer_Id | total_items          | amount_spent |
|-------------|----------------------| ------------ |
| A           | 2                    | 25           |
| B           | 3                    | 40           |

Customer A spent a total of 25 and bought 2 items before they became members, and Customer B spent a total of 40 and got 3 items. Customer C, on the other hand, isn’t a member.

## Q9 - Total points per customer

| Customer_Id | Points               |
|-------------|----------------------|
| A           | 860                  |
| B           | 940                  |
| C           | 360                  |

Customer A has the highest point of 760, B and C has points 740 and 360.

## Q10 - Total points for members at end of January (first-week 2x bonus included)

| Customer_Id | total_points         |
|-------------|----------------------|
| A           | 1370                 |
| B           | 820                  |

This query shows that Customer A has 1020 points while Customer B has 820 at the end of January.

