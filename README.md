# The-SQL-Murder-Mystery

A crime has taken place and the detective needs your help. The detective gave you the crime scene report, but you somehow lost it. You vaguely remember that the crime was a ​murder​ that occurred sometime on ​Jan.15, 2018​ and that it took place in ​SQL City​. Start by retrieving the corresponding crime scene report from the police department’s database.

<img src="/images/Screenshot (119).png" alt="schema diagram">

Use your knowledge of the database schema and SQL commands to find out who committed the murder.
-----------------
Retrive data from "crime_scene_report"
<code>
Select * from
  crime_scene_report
where
  type = 'murder'
and
  city = 'SQL City'
and
  date = 20180115;
     </code>     
     
 <img src="/images/data 1" alt="first query">
  

  



