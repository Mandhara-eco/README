![image](https://github.com/user-attachments/assets/5d4f6140-0851-469f-ba70-5412218e2c3d)![image](https://github.com/user-attachments/assets/2c48d2af-bb70-490c-8c21-8f6ef0d70167)QUESTION 1
SELECT AVG(grade)AS Average_Grade
FROM Enrollments;ALTER
![Screenshot 2024-09-28 193910](https://github.com/user-attachments/assets/579c2f18-5724-4304-a2e6-4bf6e2b6c1c6)

QUESTION 2
SELECT Students.name, Courses.course_name FROM Enrollments JOIN Students ON Enrollments.student_id = Students.student_id JOIN Courses ON Enrollments.course_id = Courses.course_id;
![Screenshot 2024-09-28 200736](https://github.com/user-attachments/assets/82d0b49b-d241-4226-af59-34af853cb5ff)

QUESTION 3
SELECT grade_level, COUNT(*) AS student_count FROM Students GROUP BY grade_level;
![Screenshot 2024-09-28 200944](https://github.com/user-attachments/assets/f95e15b8-9928-426d-bad3-02af8e0bc41a)

QUESTION 4
SELECT Courses.course_name, MAX(Enrollments.grade) AS max_grade FROM Enrollments JOIN Courses ON Enrollments.course_id = Courses.course_id GROUP BY Courses.course_name;
![Screenshot 2024-09-28 201046](https://github.com/user-attachments/assets/f21299c8-bd85-42b3-aaf3-9cfe780bf205)

QUESTION 5
SELECT AVG(Enrollments.grade) AS average_grade FROM Enrollments JOIN Students ON Enrollments.student_id = Students.student_id WHERE Students.grade_level = 3;
![Screenshot 2024-09-28 201216](https://github.com/user-attachments/assets/87aa40a8-1b44-4384-81a8-d2559a2864c5)

QUESTION 6
SELECT Students.name, Courses.course_name, Courses.credits FROM Enrollments JOIN Students ON Enrollments.student_id = Students.student_id JOIN Courses ON Enrollments.course_id = Courses.course_id;
![Screenshot 2024-09-28 201342](https://github.com/user-attachments/assets/c0c5ffe2-bf3d-458a-b0e8-57ca218d15eb)

QUESTION 7
SELECT Courses.course_name, AVG(Enrollments.grade) AS average_grade FROM Enrollments JOIN Courses ON Enrollments.course_id = Courses.course_id GROUP BY Courses.course_name HAVING AVG(Enrollments.grade) > 3.0;
![Screenshot 2024-09-28 201458](https://github.com/user-attachments/assets/fd34a9b2-715f-4fe9-a1ed-f747328dc745)

QUEATION 8
SELECT DISTINCT Students.name FROM Students WHERE Students.student_id NOT IN ( SELECT Enrollments.student_id FROM Enrollments WHERE Enrollments.grade = 4.0);
![Screenshot 2024-09-28 202211](https://github.com/user-attachments/assets/fb6cd167-0744-443f-aeb9-a1482cb93b79)

QUESTION 9
WITH StudentAverage AS ( SELECT student_id, AVG(grade) AS avg_grade FROM Enrollments GROUP BY student_id), OverallAverage AS ( SELECT AVG(grade) AS overall_avg FROM Enrollments) SELECT Students.name FROM StudentAverage JOIN Students ON StudentAverage.student_id = Students.student_id WHERE StudentAverage.avg_grade > (SELECT overall_avg FROM OverallAverage);
![Screenshot 2024-09-28 202325](https://github.com/user-attachments/assets/9ef9288a-00a9-4436-a1e6-1a1cdabff336)

QUESTION 10
SELECT Students.name, COUNT(Enrollments.course_id) AS total_courses, AVG(Enrollments.grade) AS average_grade FROM Enrollments JOIN Students ON Enrollments.student_id = Students.student_id GROUP BY Students.name;
![Screenshot 2024-09-28 202458](https://github.com/user-attachments/assets/abc38b0b-cf4e-461f-a3c3-225bd75c42c5)






