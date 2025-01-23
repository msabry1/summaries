### Normalization
### Primary and Foreign Keys
- keys : identifier for only one row and can be column or more
  - Candidate Keys : the groups that can be keys (unique row)
    ![[Pasted image 20240930022421.png]]
	   Groups : ID | ID , GivenNames |  ID , GivenNames , SurName | ID , SurName |
- Primary Key (Super Key):   the Least number of columns that forms a key 
- Foreign Key : A columns  in a table and present in another table as a Primary Key      (Foreign is subset of primary keys)
  ![[Pasted image 20240930023540.png]]
###  OLTP vs OLAP
- **OLTP (Online Transaction Processing)**
	- DBMS (Optimized for CRUD ) 
	- OLTP has the work to administer day-to-day transactions in any organization. The main goal of OLTP is data processing not data analysis **(CRUD Operations)**
	- Not Necessary has all Data (May has data for the last three months for example) 
	- Data should be Normalized

- OLAP (Online Analytical Processing)  :
	  -   Data Ware House (Optimized for write once Read Many times)
	- OLAP systems have the capability to analyze database information of multiple systems at the current time. The primary goal of OLAP Service is data analysis and not data processing **(Read Operation)**
	- has all data to make analytics on it to generate reports
	- Data should be not Normalized (in one table because read operation is Expensive operation so all attributes  will be in one row )
### DDL VS DML VS DCL
- **DDL** : Data Definition Language is used to define the Database structure or schema
- **DML** (Data Manipulation Language) / **DQL**  (Data Query Language) :  DML statements are used for managing data with in schema objects **(CRUD OPERATIONS)** .
- **DCL** : A Data Control Language is a syntax similar to a computer programming language used to control access to data stored in a database (**Authorization**).
### CHAR_LENGTH vs CHAR_LENGTH
-  LENGTH() returns the length of the string measured in bytes.
- CHAR_LENGTH() returns the length of the string measured in characters.
  ```sql
  SELECT CHAR_LENGTH('€') # is equal to 1
  SELECT LENGTH('€')  # is equal to 3
	```