CREATE DATABASE StudentManagement;

CREATE TABLE Students (
    StudentID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Gender VARCHAR(10),
    Age INT,
    Grade VARCHAR(10),
    MathScore INT,
    ScienceScore INT,
    EnglishScore INT
);
INSERT INTO Students
(Name, Gender, Age, Grade, MathScore, ScienceScore, EnglishScore)
VALUES
('Rohith', 'Male', 20, 'A', 90, 85, 88),
('Anjali', 'Female', 19, 'B', 78, 82, 80),
('Kiran', 'Male', 21, 'A', 95, 91, 89),
('Sneha', 'Female', 20, 'C', 65, 70, 72),
('Rahul', 'Male', 22, 'B', 83, 79, 81),
('Priya', 'Female', 19, 'A', 92, 94, 90),
('Arjun', 'Male', 20, 'B', 75, 77, 73),
('Divya', 'Female', 21, 'A', 88, 86, 91),
('Vikram', 'Male', 22, 'C', 60, 68, 65),
('Meena', 'Female', 20, 'B', 84, 80, 85);
SELECT * FROM Students;
SELECT
    AVG(MathScore) AS AvgMath,
    AVG(ScienceScore) AS AvgScience,
    AVG(EnglishScore) AS AvgEnglish
FROM Students;
SELECT *,
       (MathScore + ScienceScore + EnglishScore) AS TotalScore
FROM Students
ORDER BY TotalScore DESC
LIMIT 1;
SELECT Grade, COUNT(*) AS StudentCount
FROM Students
GROUP BY Grade;
SELECT Gender,
       AVG((MathScore + ScienceScore + EnglishScore)/3.0) AS AvgScore
FROM Students
GROUP BY Gender;
SELECT *
FROM Students
WHERE MathScore > 80;
UPDATE Students
SET Grade = 'A'
WHERE Name = 'Anjali';
SELECT * 
FROM Students
WHERE Name = 'Anjali';
