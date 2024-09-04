# JSONHOL
JSON HOL OCW2024 


### 1. Query entire STUDENT_SCHEDULE Duality View
curl -X GET \
'https://\<ADB String\>.adb.us-ashburn-1.oraclecloudapps.com/ords/classmate/student_schedule/?q=%7B%20%22student.studentName%22%3A%20%22Jane%22%20%7D'


### 2. Query Single entry from STUDENT_SCHEDULE for Jane-
curl -X 'GET' \
'https://\<ADB String\>.adb.us-ashburn-1.oraclecloudapps.com/ords/classmate/student_schedule/?q=%7B%20%22student.studentName%22%3A%20%22Jane%22%20%7D'

### 3. Update the STUDENT_SCHEDULE for Jane by INSERTING a new entry-

#### 3.1 Create a file called *janeClass.json*  and paste the following entries into the file

   ```
      { "student" : {"studentId" : "1735",
                     "studentName" : "Jane",
                     "studentInfo" : {"lastName": "Jameson", "Major": "Accounting"}
                     },
        "schedule": {"courseId" : "C152",
                     "courseName" : "CALC_01",
                     "courseRoom" : "A104",
                     "courseTime" : "10:00",
                     "teacherName" : "Anna",
                     "teacherId" : 645 }
   ```

#### 3.2 Call the file the following POST operation-

curl -i -X POST --data-binary @janeClass.json -H "Content-Type: application/json" https://\<ADB String\>.adb.us-ashburn-1.oraclecloudapps.com/ords/classmate/student_schedule/

