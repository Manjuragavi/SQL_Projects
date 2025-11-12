# 🎓 Student Management System – SQL Project

This project is a **SQL-based Student Management System** designed to store, manage, and analyze information about students, courses, grades, attendance, and feedback.  
It demonstrates strong database design, query optimization, and data analysis skills — ideal for academic or portfolio use.

---

## 🧰 Tools & Technologies

- **Database:** MySQL  
- **Query Tool:** DBeaver / MySQL Workbench  
- **Data Format:** SQL, CSV  
- **Version Control:** Git & GitHub  

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


