-- Create Departments table
CREATE TABLE Departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(255) NOT NULL,
    location VARCHAR(255)
);

-- Create Employees table with a foreign key referencing Departments table
CREATE TABLE Employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(255) NOT NULL,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES Departments(department_id)
);

-- Populate Departments table with sample data
INSERT INTO Departments (department_id, department_name, location)
VALUES 
    (1, 'HR', 'New York'),
    (2, 'Finance', 'Los Angeles'),
    (3, 'Marketing', 'Chicago');

-- Populate Employees table with sample data
INSERT INTO Employees (employee_id, employee_name, department_id)
VALUES
    (101, 'John Smith', 1),
    (102, 'Jane Doe', 1),
    (103, 'Mike Johnson', 2),
    (104, 'Anna White', 2),
    (105, 'Chris Miller', 3),
    (106, 'David Wilson', NULL);

-- Task 1: Add a new department called 'IT' and assign an employee to it
INSERT INTO Departments (department_id, department_name, location)
VALUES (4, 'IT', NULL);

UPDATE Employees
SET department_id = 4
WHERE employee_id = 106;

-- Task 2: Update the location of the 'HR' department from 'New York' to 'Chicago'
UPDATE Departments
SET location = 'Chicago'
WHERE department_name = 'HR';

-- Task 3: Delete the employee named 'Michael Brown' from the Employees table
DELETE FROM Employees
WHERE employee_name = 'Michael Brown';


Exercise Description:
Suppose we have two tables: Employees and Departments. The Employees table contains information about company employees, and the Departments table contains details about different departments within the company. You are tasked with creating these tables and establishing a relationship between them using primary and foreign keys.

1. Create the Departments table- colums -> department id,department name(should not be null),location
2.  Create the Employees table: colum: employee id , employee name(should not be null) and one foreign key that is department id from department table
3. Populate the Departments table with some sample data:
4. Populate the Employees table with sample data:

   Exercise Tasks:
1.Add a new department called 'IT' in the Departments table and assign an employee (e.g., EmployeeID 106, 'David Wilson') to this department in the Employees table.

2.Update the location of the 'HR' department from 'New York' to 'Chicago'.

3.Delete the employee named 'Michael Brown' from the Employees table.

Expected Results:
Task 1 should successfully add the 'IT' department and assign an employee to it.
Task 2 should update the location of the 'HR' department.
Task 3 should remove the employee 'Michael Brown' from the table.
You can practice these tasks and SQL statements against the created tables to understand how primary keys (PKs) and foreign keys (FKs) work together to establish relationships between tables in a database.
