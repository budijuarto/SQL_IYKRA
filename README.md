"# SQL_IYKRA" 

1.
```select title
from film 
where description like '%Astronaut%'
```


2.
select title
from film 
where rating = 'R' and replacement_cost between '5' and '15'

3.
select s.staff_id, count(p.payment_id) as Total_Transaksi, sum(p.amount) as Jumlah_Uang
from staff s 
join payment p
using (staff_id)
group by s.staff_id

4.
select rating, avg(replacement_cost) as average_cost
from film
group by rating

5.
select c.first_name, c.last_name,c.email, sum(p.amount) as Total_Biaya
from customer c
join payment p
using (customer_id)
group by customer_id
order by Total_Biaya desc
limit 5

6.
select store_id,film_id, count(store_id) as total_copy
from inventory 
group by store_id, film_id
order by store_id, film_id

7.
select c.first_name, c.last_name,c.email, count(p.payment_id) as Total_Transaksi
from customer c
join payment p
using (customer_id)
group by customer_id
having count(p.payment_id) >= 40
order by Total_Transaksi desc

