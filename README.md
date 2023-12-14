# DDL-Practise
 In this SQL script, I created a "Practise" database and a table named "employee" with columns for employee details. After inserting sample data, I modified the table, changing the data type of "Date_Of_Birth" to VARCHAR, later updating it back to DATE.
USE Practise;

CREATE TABLE employee (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    Last_Name VARCHAR(50),
    First_Name VARCHAR(50),
    Age INT,
    Job_Title VARCHAR(50),
    Date_Of_Birth DATE, -- Change the data type to VARCHAR
    Phone_Number VARCHAR(20),
    Insurance_id VARCHAR(10)
);

INSERT INTO employee (ID, Last_Name, First_Name, Age, Job_Title, Date_Of_Birth, Phone_Number, Insurance_id)
VALUES
    (1, 'Smith', 'John', 32, 'Manager', '1989-05-12', '5551234567', 'INS736'),
    (2, 'Johnson', 'Sarah', 28, 'Analyst', '1993-09-20', '5559876543', 'INS832'),
    (3, 'Davis', 'David', 45, 'HR', '1976-02-03', '5550555995', 'INS007'),
    (4, 'Brown', 'Emily', 37, 'Lawyer', '1984-11-15', '5551112022', 'INS035'),
    (5, 'Wilson', 'Michael', 41, 'Accountant', '1980-07-28', '5554403003', 'INS943'),
    (6, 'Anderson', 'Lisa', 22, 'Intern', '1999-03-10', '5556667777', 'INS332');

SELECT * FROM employee;
DESCRIBE employee;
ALTER TABLE EMPLOYEE 
CHANGE COLUMN ID Employee_ID int;
select * from Employee;
alter TABLE employee
add column Phone_no INT;
update  Empolyee Set Phone_no =cast(phone_number as signed );
ALTER TABLE EMPLOYEE
DROP column pHONE_NO;

CREATE TABLE EMPLOYEE_INSURANCE(
INSURANCE_ID varchar(15) PRIMARY KEY,
INSURANCE_INFO varchar(100)
);
INSERT INTO EMPLOYEE_INSURANCE (INSURANCE_ID,INSURANCE_INFO)
VALUES
("INS736", "unavailable"),
("INS832", "unavailable"),
("INS007", "unavailable"),
("INS035", "unavailable"),
("INS943", "unavailable"),
("INS332", "unavailable"),
("INS433", "unavailable");
SELECT * FROM employee_insurance;

DESCRIBE employee_insurance;
ALTER TABLE EMPLOYEE
ADD COLUMN INSURANCE_ID INT;

alter table employee
add constraint fk_employee_insurance
foreign key (insurance_id)
REFERENCES EMPLOYEE_INSURANCE(INSURANCE_ID);
DESCRIBE employee_insurance;
