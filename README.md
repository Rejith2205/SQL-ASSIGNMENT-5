## SORTING AND GROUPING


### *Create a table named Country with fields: Id Country_name Population Area*

Create table country(COUNTRY_NAME VARCHAR(50) ,
					POPULATION  INT,
					AREA INT);
### *Create another table named Persons with fields: Id Fname Lname Population Rating Country_Id Country_name*

Create table PERSONS(F_NAME VARCHAR(50),
					 L_NAME VARCHAR(50),
                    				 POPULATION INT,
                              RATING INT,
                    				 COUNTRY_ID INT,                                
                   				  COUNTRY_NAME VARCHAR(50));
### *Insert values into the table Country*
INSERT INTO COUNTRY VALUES (‘SINGAPORE,40000000,1000),(‘INDONESIA’,100000000,2500),
INSERT INTO COUNTRY VALUES	('USA',6600000,4000),('ROME',200000,1000),
                        ('TANZANIA',5000000,1500),('KENYA',3000000,1000);
INSERT INTO COUNTRY VALUES	('UK',6500000,2000),('CANADA',450000000,5500),
                        ('AUSTRALIA',80000000,6500),('INDIA',500000000,3000);

### *Insert values into the table persons*
INSERT INTO PERSONS VALUE ('TINU','TOM',40000000,5,10010,'SINGAPORE');	
INSERT INTO PERSONS VALUES('KANNAN','RAVI',6600000,6,10001,'USA'),
('MANJU','NATH', 6600000,3,10001,''),
('SUKANYA','SURESH', 6500000,7,10002,'UK'),
('ANDREW','THOMPSON', 450000000,8,10003,'CANADA'),
('ANIL','CHOUDHARY', 500000000,4,10005,'INDIA'),
('SIMILY','MATHEW', 80000000,6,10004,'AUSTRALIA'),
('ABDUL','SALAM', 5000000,3,10225,'TANZANIA'),
('ROBERT','MOGAMBE', 5000000,4,10225,'TANZANIA'),
                                                ('SUKVINDER','SINGH', 6500000,6,10002,'UK');
### *1.	Write an SQL query to print the first three characters of Country_name from the Country table*

SELECT LEFT(COUNTRY_NAME, 3) AS COUNTRYCODE
FROM COUNTRY;	

### *2.	Write an SQL query to concatenate first name and last name from Persons table* 
SELECT CONCAT(F_NAME , L_NAME)
 AS FULLNAME  FROM PERSONS;

### *3.	Write an SQL query to count the number of unique country names from Persons table* 

SELECT  DISTINCT COUNT(COUNTRY_NAME),COUNTRY_NAME FROM PERSONS
 GROUP BY COUNTRY_NAME;
	
### *4.	Write a query to print the maximum population from the Country table*

SELECT MAX(POPULATION) FROM PERSONS;
### *5.	Write a query to print the minimum population from Persons table* 

SELECT MIN(POPULATION) FROM PERSONS;	
### *6.	Insert 2 new rows to the Persons table making the Lname NULL. Then write another query to count Lname from Persons table*

INSERT INTO PERSONS VALUES('JALEEL','NULL',6600000,7,10001,'USA'),
('MANOJ','NULL',6600000,8,10001,'USA');

### *7.	Write a query to find the number of rows in the Persons table*


SELECT COUNT(*) FROM PERSONS;

### *8.	Write an SQL query to show the population of the Country table for the first 3 rows*

SELECT POPULATION FROM COUNTRY
  LIMIT 3;


### *9.	Write a query to print 3 random rows of countries*

SELECT * FROM COUNTRY
ORDER BY RAND()
LIMIT 3;	

### *10.	List all persons ordered by their rating in descending order* 

SELECT * FROM PERSONS
ORDER BY RATING DESC;

### *11.	Find the total population for each country in the Persons table* 

SELECT SUM(POPULATION) FROM PERSONS;

### *12.	Find countries in the Persons table with a total population greater than 50,000*

SELECT COUNTRY_NAME ,POPULATION FROM PERSONS
WHERE POPULATION >50000
GROUP BY COUNTRY_NAME,POPULATION;

### *13.	List the total number of persons and average rating for each country, but only for countries with more than 2 persons, ordered by the average rating in ascending order*

SELECT COUNT(*), AVG(RATING),COUNTRY_NAME
FROM PERSONS
GROUP BY COUNTRY_NAME  
Having COUNT(*)>=2  





