### 1-film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
```
SELECT COUNT(*) FROM film
WHERE length >
(
    SELECT AVG(length) FROM film 
);

```
### 2-film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
```
SELECT COUNT(*) FROM film
WHERE rental_rate =
(
    SELECT MAX(rental_rate) FROM film
);

```
### 3-film tablosunda en düşük rental_rate ve en düşük replacement_cost değerlerine sahip filmleri sıralayınız.
```
SELECT title FROM film
WHERE rental_rate = all
(
    SELECT MIN(rental_rate) FROM Film) and replacement_cost = any (SELECT min(replacement_cost) FROM Film
)
```
### 4-payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.
```
SELECT payment.customer_id, first_name, last_name, COUNT(payment.customer_id) AS payment_count FROM payment
   LEFT JOIN customer ON payment.customer_id = customer.customer_id
   GROUP BY payment.customer_id, customer.first_name, customer.last_name
   ORDER BY payment_count DESC;
```