# session27-Assignment-27_2--Assignment2
DATA ANALYTICS WITH R, EXCEL AND TABLEAU SESSION 27ASSIGNMENT 2


                                               SESSION 11: RDBMS (CONTD.)
                                                      Assignment 2
                                                    Assignment 27_2

4. Associated Data Files Use the Sakila schema, which can be found in following link (to be installed in your local system) 
http://dev.mysql.com/doc/index-other.html("sakila database") 
http://dev.mysql.com/doc/sakila/en/sakila.html(for full documentation) Requirements 
For each question, you are required to provide the following: 
- The SQL query you used 
- The answers 
- Any assumptions you made 
5. Problem Statement 1. Who is the customer who spent the most on rental movies? Return his/her customer id, first name and the amount spent.  
2. Give an interesting query of your own that is not already in the assignment. The query should involve at least two joins, HAVING clause and aggregation operation. Give the English explanation and the answer.

Answers:-
27.2.1
Question: Who is the customer who spent the most on rental movies? Return his/her customer id, first name and the amount spent.

Select c.customer_id as “customer_ID”, c.first_name as “First Name” ,sum(amount) as “Total Paid”  from payment p inner join customer c on p.customer_id=c.customer_id group by c.customer_id having sum(amount)>220 order by sum(amount) desc;
(assumed the upper level 220 for comparison of amount).
=====================
27.2.2
Question: Give an interesting query of your own that is not already in the assignment. The query should involve at least two joins, HAVING clause and aggregation operation. Give the English explana-tion and the answer.

Answer:
Display the film categories (names) where the average difference between the film replacement cost and the rental rate larger than 17? (question framed)
Ans:-
select c.name, avg(b.replacement_cost) cost, avg(b.rental_rate) rate from film_category a inner join film b on a.film_id=b.film_id inner join category c  on c.category_id=a.category_id group by a.category_id having cost-rate> 17;
=======================


 
