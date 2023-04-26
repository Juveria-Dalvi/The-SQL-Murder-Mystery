# The-SQL-Murder-Mystery

A crime has taken place and the detective needs your help. The detective gave you the crime scene report, but you somehow lost it. You vaguely remember that the crime was a ​murder​ that occurred sometime on ​Jan.15, 2018​ and that it took place in ​SQL City​. Start by retrieving the corresponding crime scene report from the police department’s database.

<img src="/images/Screenshot (119).png" alt="schema diagram">

Use your knowledge of the database schema and SQL commands to find out who committed the murder.
-----------------
Retrive data from "crime_scene_report"

<code>Select * from
  crime_scene_report
where
  type = 'murder'
and
  city = 'SQL City'
and
  date = 20180115;
     </code>     
     
 <img src="/images/data 1.PNG" alt="first query">
  
Retrive data from "Person" - First Witness

<code>select * from 
	person
where
	address_street_name 
like 
	'northwestern %'
order by
	address_number
desc limit 1; 
</code>

 <img src="/images/data 2.PNG" alt="second query">

Retrive data from "Person" - Second Witness

<code>select * from 
	person
where
	address_street_name 
like 
	'franklin Ave'
and 
	name 
like "Annabel%" 
</code>

 <img src="/images/data 3.PNG" alt="third query">

above are 2 Witnesses Now check their "Interviews"

<code>select * from 
	interview
where
	person_id 
IN 
	(14887,  16371);
</code>

 <img src="/images/data 4.PNG" alt="fourth query">

Now, write a query according to their statements

<code>select * from 
	get_fit_now_member A
Join
	get_fit_now_check_in B
ON 
	A.id = B.membership_id
where
	membership_id like '48Z%'
And
	membership_status like 'gold';
</code>

 <img src="/images/data 5.PNG" alt="fifth query">
 
 try and insert both names to find out culprit
 
  <img src="/images/solution 1.PNG" alt="sol1 query">

So now, lets check his statement in interview

<code>select * from 
	interview
where
	person_id = 67318;
</code>

 <img src="/images/data 6.PNG" alt="sixth query">
 
 Let's find the women
 
 <code>select * from 
	drivers_license
where
	hair_color 
like
	'red'
and
	gender = 'female'
and
	height between 65 and 67
and
	car_make = 'Tesla'
</code>

 <img src="/images/data 7.PNG" alt="7 query">
 
 Now we have 3 suspects lets find out who went for SQL Symphony Concert but lets have their person ID
 
<code>Select * from
	person
where 
	license_id IN (202298,291182,918773)
</code>

 <img src="/images/data 8.PNG" alt="8 query">
 
 now that we got person IDs lets check events in "facebook_event_checkin"
 
<code>select * from 
	facebook_event_checkin
where
	date 
like
	'201712%'
and
	event_name like '%SQL Symphony Concert%'
and
	person_id
IN (78881,90700,99716);
</code>

 <img src="/images/data 9.PNG" alt="9 query">
 
we are close to find out the Culprit let's check 'person' with above ID

 <img src="/images/data 10.PNG" alt="10 query">
