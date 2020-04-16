-- Which actors have the first name 'Scarlett'

select *
from actor
where first_name = 'Scarlett';


-- Which actors have the last name 'Johansson'

select *
from actor
where last_name = 'Johansson';


-- How many distinct actors last names are there?

select count(distinct last_name) as count_distinct_name
from actor;


-- Which last names are not repeated?

select last_name, count(distinct first_name)
from actor
group by last_name
having count(distinct first_name) < 2;


-- Which last names appear more than once?

select last_name, count(distinct first_name)
from actor
group by last_name
having count(distinct first_name) > 1
order by 2 desc;
