1. What query would you run to get all the customers inside city_id = 312? Your query should return customer first name, last name, email, and address.
SELECT address.city_id, customer.first_name, customer.last_name, customer.email, address.address, city.city, country.country
FROM customer
JOIN address ON customer.address_id = address.address_id
JOIN city ON address.city_id = city.city_id
JOIN country ON city.country_id = country.country_id
WHERE city.city_id = 312;

2. What query would you run to get all comedy films? Your query should return film title, description, release year, rating, special features, and genre (category).
SELECT film.film_id, film.title, film.description, film.release_year, film.rating, film.special_features, category.name AS genre
FROM film
JOIN film_category ON film.film_id = film_category.film_id
JOIN category ON film_category.category_id = category.category_id
WHERE category.name = "Comedy";

3. What query would you run to get all the films joined by actor_id=5? Your query should return the actor id, actor name, film title, description, and release year.
SELECT film_actor.actor_id, CONCAT_WS(" ", actor.first_name, actor.last_name) AS name,
        film.title, film.description, film.release_year
FROM film
JOIN film_actor
ON film.film_id = film_actor.film_id
JOIN actor
ON film_actor.actor_id = actor.actor_id
WHERE film_actor.actor_id = 5;

4. What query would you run to get all the customers in store_id = 1 and inside these cities (1, 42, 312 and 459)? Your query should return customer first name, last name, email, and address.
SELECT customer.first_name, customer.last_name, customer.email, address.address
FROM customer
JOIN address
ON customer.address_id = address.address_id
WHERE customer.store_id = 1
AND address.city_id = 1
OR address.city_id = 42
OR address.city_id = 312
OR address.city_id = 459;
