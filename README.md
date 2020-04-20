# Practice Case IYKRA

1.A customer wants to know the films about "astronaut".  How many recommendations could you give for him?
```
select title
from film 
where description like '%Astronaut%'
```


2.I wonder,  how many films have a rating of "R" and a replacement cost between  $5 and $15?
```
select title
from film 
where rating = 'R' and replacement_cost between '5' and '15'
```


3. We have two staff members with staff IDs 1   and 2. We want to give a bonus to the staff member that handled the most payments.
```
select s.staff_id, count(p.payment_id) as Total_Transaksi, sum(p.amount) as Jumlah_Uang
from staff s 
join payment p
using (staff_id)
group by s.staff_id
```


4. Corporate  headquarters is auditing the store, they want to know the average  replacement cost of movies by rating
```
select rating, avg(replacement_cost) as average_cost
from film
group by rating
```


5.We want to send coupons to the 5 customers  who have spent the most amount of money. Get the customer  name, email and their spent amount!
```
select c.first_name, c.last_name,c.email, sum(p.amount) as Total_Biaya
from customer c
join payment p
using (customer_id)
group by customer_id
order by Total_Biaya desc
limit 5
```
6.We want to audit our stock of films in all of our stores.  How many copies of each movie in each store do we have?
```
select store_id,film_id, count(store_id) as total_copy
from inventory 
group by store_id, film_id
order by store_id, film_id
```
7.We want to know what customers  are eligible for our platinum credit card. The requirements are that the customer  has at least a total of 40 transaction  payments.  Get the customer name, email who are eligible for the credit card!

```
select c.first_name, c.last_name,c.email, count(p.payment_id) as Total_Transaksi
from customer c
join payment p
using (customer_id)
group by customer_id
having count(p.payment_id) >= 40
order by Total_Transaksi desc
```
Python
Please make a python function that introduces your name, address, date of birth, and print them out into one sentence!
```
name = input('Enter your name:')
address = input('Enter your address:')
date = input('Enter your date:')
def perkenalan(name,address,date):
  print("My name is "+ name+ ", I live in "+ address+ ", I was born on "+ date)
perkenalan(name,address,date)

```
