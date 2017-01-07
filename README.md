# Webpage-Transitions
Versions: 
node:"4.4.2"
pg: "9.5.4"

SQL Query to return what pages users came from 

The original table contains three columns: pid, event, and time. 
The pid is the user that is accessing the web page called event. Time is when the user accessed the page. The query will return a table with three columns: prev, event, and count. 

 pid | event |        time         
-----+-------+---------------------

   1 | A     | 2016-09-23 02:21:13
   
   2 | B     | 2016-09-23 03:24:13
   
   2 | C     | 2016-09-23 04:21:13
   
   3 | A     | 2016-09-23 05:21:13
   
   3 | B     | 2016-09-23 02:21:13
   
   1 | B     | 2016-09-23 04:21:13
   
   
Prev is the web page that the user was on before clicking to enter web page in event. Count is how many times a user made a transition from the web page in prev to the web page in event. 

 prev | event | count 
 
------+-------+-------

 B         | A     |     1
 
 A         | B     |     1
 
 B         | C     |     1

The folder with tests contains javascript files that will create the tables to run tests. Make sure to create a database called webtransition in postgresql. Then, create the tables for each test by running the javascript files within folder called test. 

Currently, transitionquery.sql will display the result for test5. Thus, one will need to create the table in test5.js by running node test5.js before running transitionquery.sql. 


To run transitionquery.sql: 
  type: psql transitionquery.sql 
