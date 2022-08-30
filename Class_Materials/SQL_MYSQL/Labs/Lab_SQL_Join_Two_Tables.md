use sakila;

### Q1
### Which actor has appeared in the most films?
SELECT first_name, last_name, count(actor_id)  FROM film_actor JOIN actor USING (actor_id)
GROUP BY actor_id
ORDER BY count(actor_id) DESC
LIMIT 1;

### Q2
### Most active customer (the customer that has rented the most number of films)
SELECT first_name, last_name, count(customer_id) FROM rental JOIN customer USING (customer_id)
GROUP BY customer_id
ORDER BY count(customer_id) DESC
LIMIT 1;

### Q3
### List number of films per category.
SELECT name, count(category_id) FROM film_category JOIN category USING (category_id)
GROUP BY name
ORDER BY name;