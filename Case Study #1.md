## Case Study Questions

Each of the following case study questions can be answered using a single SQL statement:
1. What is the total amount each customer spent at the restaurant?

2. How many days has each customer visited the restaurant?

  3.  What was the first item from the menu purchased by each customer?
  4.  What is the most purchased item on the menu and how many times was it purchased by all customers?
 5.   Which item was the most popular for each customer?
  6.  Which item was purchased first by the customer after they became a member?
  7.  Which item was purchased just before the customer became a member?
 8.   What is the total items and amount spent for each member before they became a member?
 9.   If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
 10.   In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi - how many points do customer A and B have at the end of January?
 11. Recreate the following table output using the available data:
 12. Danny also requires further information about the ranking of customer products, but he purposely does not need the ranking for non-member purchases so he expects null ranking values for the records when customers are not yet part of the loyalty program.



## Answers

```sql
--1
select 
    s.customer_id,
    sum(m.price) as total_price
from dannys_diner.sales s
left join dannys_diner.menu m on m.product_id = s.product_id 
group by s.customer_id
order by total_price desc;

```
```sql
--2
SELECT
  customer_id,
  count(distinct(order_date)) as count_of_visit

FROM dannys_diner.sales
group by 1;
```
