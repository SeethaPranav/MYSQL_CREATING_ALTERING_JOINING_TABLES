# MYSQL_CREATING_ALTERING_JOINING_TABLES
This repository provides a comprehensive guide and examples for creating, altering, and joining tables in SQL to enhance your database management skills.

1. Create table ‘COUNTRY’
   
  CREATE TABLE COUNTRY (ID INT PRIMARY KEY NOT NULL, COUNTRY_NAME VARCHAR(20), POPULATION INT, AREA INT);

![image](https://github.com/user-attachments/assets/d42bcc3a-3880-47df-a873-72de94adcaf1)

2. Insert 10 rows into table.
   
INSERT INTO COUNTRY VALUES(101, 'India', 1234567891, 3550000),
						  (102, 'ARGENTINA', 242538529, 9800000),
						  (103, 'USA', 430962186, 7900000),
						  (104, 'UK', 63438365, 327653),
						  (105, 'CANADA', 94081541, 67453628),
						  (106, 'RUSSIA', 143865423, 15469000),
						  (107, 'NIGERIA', 227045617, 400000),
						  (108, 'ETHIOPIA', 134182467, 1100000),
						  (109, 'BRAZIL', 24567435, 8500000),
						  (110, 'GERMANY', 128204293, 1200000);
        
SELECT * FROM COUNTRY;

![image](https://github.com/user-attachments/assets/3fafe7c3-9037-4640-ac71-65d3aedd0108)

3. Create table ‘PERSONS’
    
  CREATE TABLE PERSONS (ID INT PRIMARY KEY NOT NULL, FNAME VARCHAR(30), LNAME VARCHAR(30), POPULATION INT, RATING DECIMAL(5,2), COUNTRY_ID INT,COUNTRY_NAME VARCHAR(20),FOREIGN KEY(COUNTRY_ID) REFERENCES COUNTRY(ID));

![image](https://github.com/user-attachments/assets/758761fd-560c-4124-8abb-72277f4b49d2)

4. Insert 10 rows.
   
INSERT INTO Persons VALUES 
(551, 'JOHN', 'LUTHER', 1234567891, 4.4, 101, 'India'),
                 (552, 'SHAMIN', 'KUMAR', 242538529, 4.2, 102, 'ARGENTINA'),
                        (553, 'ZERA', 'MARTIN', 63438365, 3.4, 104, 'UK'),
         (554, 'HALA', 'YOUSEF', 134182467, 3.9, 108, 'ETHIOPIA'),
      (555, 'MIKE', 'TISON', 128204293, 4.4, 110, 'GERMANY'),
                        (556, 'SONY', 'KJ', 227045617, 4.6, 107, NULL),
  (557, 'JERY', 'TOMAS', 94081541, 3.0, 105, 'CANADA'),
         (558, 'THOMAS', 'VARGEES', 1234567891, 2.6, 101, NULL),
    (559, 'RAYAN', 'PHILIP', 143865423, 3.3, 106, 'RUSSIA'),
                        (560, 'JACK', 'DANIEL', 24567435, 3.8, 109, NULL);
   
SELECT * FROM PERSONS;

![image](https://github.com/user-attachments/assets/2c882ccf-a1f7-43ba-bf81-4a0fecbb615b)

5.To remove column population
   
ALTER TABLE COUNTRY DROP COLUMN POPULATION;

6.To delete all rows from country table

TRUNCATE TABLE COUNTRY;

7.To delete table country

DROP TABLE COUNTRY;

8.Perform inner joins, left joins, right joins

#INNER JOIN
  
SELECT P.ID, P.FNAME, P.COUNTRY_ID, P.COUNTRY_NAME,  P.POPULATION FROM
 PERSONS P INNER JOIN COUNTRY C 
ON P.COUNTRY_ID = C.ID;

![image](https://github.com/user-attachments/assets/c0f30cd5-5d31-4c4f-8ff8-c0b69b27f926)

#LEFT JOIN

SELECT P.ID, P.FNAME, P.COUNTRY_ID, P.COUNTRY_NAME,  P.POPULATION FROM
 PERSONS P LEFT JOIN COUNTRY C 
ON P.COUNTRY_ID = C.ID;

![image](https://github.com/user-attachments/assets/0dd94941-ae81-4a09-a6ab-a0dde07ee138)

#RIGHT JOIN

SELECT P.ID, P.FNAME, P.COUNTRY_ID, P.COUNTRY_NAME,  P.POPULATION FROM
 PERSONS P RIGHT JOIN COUNTRY C 
ON P.COUNTRY_ID = C.ID;

![image](https://github.com/user-attachments/assets/6076aeb0-80bc-4f2e-95db-3d557096ccac)

9. List all distinct country names from both the country and persons table.
    
  SELECT DISTINCT COUNTRY_NAME FROM COUNTRY 
UNION
SELECT DISTINCT COUNTRY_NAME FROM PERSONS;

![image](https://github.com/user-attachments/assets/760734f5-71f6-42cd-9772-f798251e113e)

10. List all country names from both the country and persons tables, including duplicates.
    
SELECT COUNTRY_NAME FROM COUNTRY 
UNION ALL
SELECT COUNTRY_NAME FROM PERSONS;

![image](https://github.com/user-attachments/assets/d55d6a76-e666-4662-90fd-4bfae3858b23)

















