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
