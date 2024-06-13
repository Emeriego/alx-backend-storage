### Things you should know
# to start mysql service
service mysql start 


cat 0-list_databases.sql | mysql -uroot -p my_database

## create a db directly from the terminal without logging in or opening mysql
echo "CREATE DATABASE hbtn_0d_tvshows;" | mysql -uroot -p


### download an sql command and apply it to a given db. the -s says operate in silence.
curl "https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/274/hbtn_0d_tvshows.sql" -s | mysql -uroot -p hbtn_0d_tvshows

### View a table in the db from the terminal
echo "SELECT * FROM tv_genres" | mysql -uroot -p hbtn_0d_tvshows

### Problem - Write a SQL script that creates a table users following these requirements:

With these attributes:
id, integer, never null, auto increment and primary key
email, string (255 characters), never null and unique
name, string (255 characters)
country, enumeration of countries: US, CO and TN, never null (= default will be the first element of the enumeration, here US)
If the table already exists, your script should not fail
Your script can be executed on any database

## solution
1-country_users.sql

### Problem - 

Write a SQL script that ranks country origins of bands, ordered by the number of (non-unique) fans

Requirements:

Import this table dump: metal_bands.sql.zip - included
Column names must be: origin and nb_fans
Your script can be executed on any database
Context: Calculate/compute something is always power intensive… better to distribute the load!



## solution
2-fans.sql

### Problem - 

Write a SQL script that lists all bands with Glam rock as their main style, ranked by their longevity

Requirements:

Column names must be: band_name and lifespan (in years until 2022 - please use 2022 instead of YEAR(CURDATE()))
You should use attributes formed and split for computing the lifespan
Your script can be executed on any database

use the metal_bands.sql db

## solution
3-glam_rock.sql


### Problem - 

Write a SQL script that creates a trigger that decreases the quantity of an item after adding a new order.

Quantity in the table items can be negative.

Context: Updating multiple tables for one action from your application can generate issue: network disconnection, crash, etc… to keep your data in a good shape, let MySQL do it for you!

## solution
4-store.sql

### Problem - 

Write a SQL script that creates a trigger that resets the attribute valid_email only when the email has been changed.

Context: Nothing related to MySQL, but perfect for user email validation - distribute the logic to the database itself!

## solution
5-valid_email.sql

### Problem - 

Write a SQL script that creates a stored procedure AddBonus that adds a new correction for a student.

Requirements:

Procedure AddBonus is taking 3 inputs (in this order):
user_id, a users.id value (you can assume user_id is linked to an existing users)
project_name, a new or already exists projects - if no projects.name found in the table, you should create it
score, the score value for the correction
Context: Write code in SQL is a nice level up!

eg.
CREATE PROCEDURE CheckSalary(IN emp_id INT, OUT result VARCHAR(50))
BEGIN
    DECLARE emp_salary DECIMAL(10,2);
    SELECT salary INTO emp_salary FROM employees WHERE id = emp_id;
    
    IF emp_salary > 100000 THEN
        SET result = 'High Salary';
    ELSE
        SET result = 'Normal Salary';
    END IF;
END;

## solution
6-bonus.sql


### Problem - 

Write a SQL script that creates a stored procedure ComputeAverageScoreForUser that computes and store the average score for a student. Note: An average score can be a decimal

Requirements:

Procedure ComputeAverageScoreForUser is taking 1 input:
user_id, a users.id value (you can assume user_id is linked to an existing users)

## solution
7-average_score.sql


### Problem - 

Write a SQL script that creates an index idx_name_first on the table names and the first letter of name.

Requirements:

Import this table dump: names.sql.zip
Only the first letter of name must be indexed
Context: Index is not the solution for any performance issue, but well used, it’s really powerful!
## solution
8-index_my_name.sql

### Problem
Write a SQL script that creates an index idx_name_first_score on the table names and the first letter of name and the score.

Requirements:

Import this table dump: names.sql.zip
Only the first letter of name AND score must be indexed
### solution
9-index_name_.sql

### Problem
Write a SQL script that creates a function SafeDiv that divides (and returns) the first by the second number or returns 0 if the second number is equal to 0.

Requirements:

You must create a function
The function SafeDiv takes 2 arguments:
a, INT
b, INT
And returns a / b or 0 if b == 0
### solution
10-div.sql

### Problem
Write a SQL script that creates a view need_meeting that lists all students that have a score under 80 (strict) and no last_meeting or more than 1 month.

Requirements:

The view need_meeting should return all students name when:
They score are under (strict) to 80
AND no last_meeting date OR more than a month

### solution
11-need_meeting.sql


### Problem
Write a SQL script that creates an index idx_name_first_score on the table names and the first letter of name and the score.

Requirements:

Import this table dump: names.sql.zip
Only the first letter of name AND score must be indexed
### solution
100-average_weight.sql


### Problem
Write a SQL script that creates a stored procedure ComputeAverageWeightedScoreForUser that computes and store the average weighted score for a student.

Requirements:

Procedure ComputeAverageScoreForUser is taking 1 input:
user_id, a users.id value (you can assume user_id is linked to an existing users)
### solution
101-average...sql
