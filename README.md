# College Attendance Management System

A small, working college mini-project that shows how attendance can be managed digitally. It follows the Context, Level-1 and Level-2 DFDs: authenticate, manage students, mark attendance, calculate attendance, and generate reports. Theme: red and white.

## Aim and objectives
- Provide separate Administrator, Faculty and Student views.
- Let faculty select a class, subject and date, mark Present or Absent, validate, and save.
- Calculate attendance percentage automatically: (classes attended / total classes) x 100.
- Show reports from saved records, with print and CSV export.

## Technologies used
HTML5, CSS3, vanilla JavaScript, and browser LocalStorage. No backend, database, paid service or external API is needed.

## Main features
- Login with role selection and validation messages, plus Logout.
- Administrator: dashboard with calculated statistics, student list with search, add student, view details, faculty and subjects, classes, reports, Reset Demo Data.
- Faculty: select class, subject and date; Mark All Present, Mark All Absent, Reset Selection; validation; duplicate-session protection with "load existing session to update"; confirmation with counts.
- Student: own dashboard, subject-wise table with progress bars, history by date with subject filter.
- Reports: filters for class, subject, student and date range; Low (<75%) label; empty-result message; Print; CSV export.
- Percentage rules: N/A when no classes were conducted, attended never exceeds total, rounded to two decimals.

## Folder structure
```
college-attendance-system/
  index.html              login
  dashboard.html          admin and faculty dashboard
  students.html           student management (admin)
  attendance.html         mark attendance (faculty)
  reports.html            attendance reports (admin, faculty)
  student-summary.html    student dashboard
  css/style.css           theme colors are CSS variables in :root
  js/data.js              sample data, storage helpers, calculations
  js/auth.js              login, session, role-based navigation
  js/dashboard.js  js/students.js  js/attendance.js  js/reports.js  js/student-summary.js
  README.md
```

## How to run
Open `index.html` in a browser, or open the folder in VS Code and use the Live Server extension. Sample data loads on first launch.

## Demo login credentials
| Role | Username | Password |
|---|---|---|
| Administrator | admin | admin123 |
| Faculty | faculty1 | fac123 |
| Student | student1 | stu123 |

Extra accounts: faculty2 / fac456 (teaches DBMS and Software Engineering), student2 to student5 / stu123.

## Sample data
Five fictional students (CS101 Aarav Sharma, CS102 Priya Patil, CS103 Rohan Verma in TY; CS104 Ananya Singh in SY; CS105 Karan Mehta in FY), four subjects, two faculty accounts, and preloaded sessions in September 2026. student1 shows OS 8/10 (80%), CN 7/10 (70%), DBMS 9/10 (90%), SE 10/10 (100%).

## Testing scenarios
1. Valid login, wrong password, empty fields.
2. Add a student; try a duplicate roll number.
3. As faculty1: choose TY B.Tech CSE, Operating Systems, today; mark students; save.
4. Try to load without a class or subject; try saving with a missing status.
5. Save the same class, subject and date again to see the duplicate warning.
6. Check the 80%, 100% and N/A percentage cases (student1 history, and a subject with no classes in Reports).
7. Apply a date range with no sessions to see the empty-report message.
8. Refresh the page to confirm records persist; log in as student1 to confirm only their data shows; Logout.

## Current limitations
- Login is frontend-only demo security, not production-grade.
- Data lives in one browser's LocalStorage; clearing site data or using another browser starts from the sample data.
- Newly added students do not get a login account automatically.
- Faculty and subject details are fixed sample data (view only).
- Use fictional data only; do not enter real student or Aadhaar information.
