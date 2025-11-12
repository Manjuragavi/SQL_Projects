# 🎓 College  Management Analysis – SQL Project
## Description
This project focuses on designing and managing a College Database System using MySQL to perform data cleaning, analysis, and reporting. It demonstrates the use of SQL queries, joins, views, aggregation, and analytical functions to extract meaningful insights from college-related data such as student details, attendance, grades, feedback, and course enrollments.

---

## 🧰 Tools & Technologies

- **Database:** MySQL  
- **Query Tool:**  MySQL Workbench  
- **Data Format:** SQL, CSV   

---

## 🧱 Database Schema

### **1️⃣ STUDENT**
| Column | Description |
|--------|--------------|
| StudentID | Unique student identifier |
| FirstName | First name |
| LastName | Last name |
| Gender | Gender of the student |
| DateOfBirth | Date of birth |
| Major | Student’s major or department |
| GPA | Cumulative GPA |

### **2️⃣ COURSE**
| Column | Description |
|--------|--------------|
| CourseID | Unique course identifier |
| CourseName | Course title |
| Department | Department offering the course |
| Credits | Course credits |
| Instructor | Course instructor name |

### **3️⃣ ENROLLMENT**
| Column | Description |
|--------|--------------|
| EnrollmentID | Unique enrollment record |
| StudentID | Linked to STUDENT table |
| CourseID | Linked to COURSE table |
| Semester | Semester of enrollment |
| Year | Academic year |
| Grade | Final grade achieved |

### **4️⃣ ATTENDANCE**
| Column | Description |
|--------|--------------|
| AttendanceID | Unique attendance record |
| StudentID | Linked to STUDENT table |
| CourseID | Linked to COURSE table |
| Date | Attendance date |
| AttendanceStatus | Present / Absent |

### **5️⃣ GRADE**
| Column | Description |
|--------|--------------|
| GradeID | Unique grade record |
| StudentID | Linked to STUDENT table |
| CourseID | Linked to COURSE table |
| AssignmentType | Exam / Project / Quiz / etc. |
| Score | Marks obtained |
| Date | Date of evaluation |

### **6️⃣ FEEDBACK**
| Column | Description |
|--------|--------------|
| FeedbackID | Unique feedback ID |
| StudentID | Linked to STUDENT table |
| FeedbackDate | Date feedback was submitted |
| FeedbackText | Student’s comments or suggestions |

---
## Data aggregation 

### Create the Database
Query :
```` sql 
CREATE DATABASE COLLEGEDATABASE;
USE COLLEGEDATABASE;
````
### DATA CLEANING 
#### Check Null Values (using count)
##### ATTENDANCE TABLE
Query :
```sql
SELECT COUNT(*) AS NULL_VALUES FROM ATTENDANCE WHERE ATTENDANCEID IS NULL OR
                              STUDENTID IS NULL OR
                              COURSEID IS NULL OR
                              DATE IS NULL OR
                              ATTENDANCESTATUS IS NULL;
```
Result:

##### COURSES TABLE
Query :
```sql
SELECT COUNT(*) AS NULL_VALUES FROM COURSES WHERE COURSEID IS NULL OR
                              COURSENAME IS NULL OR
                              DEPARTMENT IS NULL OR
                              CREDITS IS NULL OR
                              INSTRUCTOR IS NULL;
```
Result:
##### STUDENTS TABLE
Query :
```sql
SELECT COUNT(*) AS NULL_VALUES FROM STUDENTS WHERE FIRSTNAME IS NULL OR
                              STUDENTID IS NULL OR
                              LASTNAME IS NULL OR
                              GENDER IS NULL OR
                              DATEOFBIRTH IS NULL OR
                              MAJOR IS NULL OR
                              GPA IS NULL;
```
Result:
### COLUMN WISE NULL VALUES
Query:
```sql
SELECT SUM(CASE WHEN STUDENTID IS NULL THEN 1 ELSE 0 END) AS STUDENTID,
       SUM(CASE WHEN FIRSTNAME IS NULL THEN 1 ELSE 0 END) AS FIRSTNAME,
       SUM(CASE WHEN LASTNAME IS NULL THEN 1 ELSE 0 END) AS LASTNAME,
	   SUM(CASE WHEN GENDER IS NULL THEN 1 ELSE 0 END) AS GENDER,
	   SUM(CASE WHEN DATEOFBIRTH IS NULL THEN 1 ELSE 0 END) AS DATEOFBIRTH,
	   SUM(CASE WHEN MAJOR IS NULL THEN 1 ELSE 0 END) AS MAJOR,
	   SUM(CASE WHEN GPA IS NULL THEN 1 ELSE 0 END) AS GPA FROM STUDENTS;
```
Result:

### CHECKING DUPLICATE VALUES IN TABLES
Query:
```sql
SELECT STUDENTID,COUNT(*) AS DUPLICATES FROM STUDENTS
GROUP BY STUDENTID 
HAVING COUNT(*)>1;
```
Result:
Query:
```sql
SELECT ENROLLMENTID,COUNT(*) AS DUPLICATES FROM ENROLLMENTS
GROUP BY ENROLLMENTID 
HAVING COUNT(*)>1;
```
Result:

### CHECKING DATATYPE IN TABLE
Query:
```sql
DESC ATTENDANCE;
SET SQL_SAFE_UPDATE=0;
UPDATE ATTENDANCE
``` 
Result:
Query:
```sql
SET DATE=STR_TO_DATE(DATE,'%Y-%M-%D');
ALTER TABLE ATTENDANCE MODIFY COLUMN DATE DATE;
```
Result:
Query:
```sql
DESC ENROLLMENTS;
ALTER TABLE ENROLLMENTS MODIFY COLUMN YEAR YEAR;
```
Result:


## 🧠 Project Highlights

- Created **6 fully normalized tables** with appropriate primary and foreign keys.  
- Implemented **20+ advanced SQL queries** using:
  - Joins (INNER, LEFT, RIGHT)
  - Aggregations (SUM, AVG, COUNT)
  - Subqueries and CTEs
  - Views for summarized reporting
  - Window functions for ranking and analysis  
- Analyzed student performance, attendance trends, and course feedback.

---

## 🧩 Sample Queries

- Find students taking more than 3 courses in the same semester.  
- Calculate average GPA by department.  
- Identify top 5 students with highest GPA.  
- Get attendance percentage per student.  
- Find courses with the highest enrollment.  
- Retrieve students who have never been absent.  
- Analyze average score by assignment type.  

---

## 📂 Project Structure


