# MongoDB Tasks
### Task 1: Add more students to the students collection
* Add at least 5 new students to the students collection with unique names, roll numbers, and course enrollments.


```
{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b61"
  },
  "name": "Jenil",
  "rollNumber": 101,
  "department": "Computer Science",
  "year": "3rd",
  "subjectsEnrolled": [
    "React",
    "NodeJS",
    "MongoDB",
    "React Native"
  ]
}


{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b62"
  },
  "name": "Mahir",
  "rollNumber": 102,
  "department": "Computer Science",
  "year": "3rd",
  "subjectsEnrolled": [
    "React",
    "NodeJS",
    "MongoDB",
    "javascript"
  ]
}


{
  "_id": {
    "$oid": "677cf33d8a877a05296a5263"
  },
  "name": "nagesh jagtap",
  "rollNumber": 103,
  "department": "Computer Science",
  "year": 2,
  "subjectsEnrolled": [
    "React",
    "NodeJS"
  ]
}


{
  "_id": {
    "$oid": "677cf33d8a877a05296a5264"
  },
  "name": "ashawini",
  "rollNumber": 104,
  "department": "Computer Science",
  "year": 3,
  "subjectsEnrolled": [
    "React",
    "NodeJS"
  ]
}



{
  "_id": {
    "$oid": "677cf33d8a877a05296a5265"
  },
  "name": "mayur",
  "rollNumber": 105,
  "department": "Electrical Engineering",
  "year": 3,
  "subjectsEnrolled": [
    "React",
    "NodeJS"
  ]
}


```

### Task 2: Insert a new course into the courses collection
* Add a new course with the following details

```
db.courses.insertOne({
  "courseCode": "CS202",
  "name": "Data Structures",
  "credits": 3,
  "instructor": "Prof. Krishna"
});
```
``` 
answer

{
  "_id": {
    "$oid": "677cf4628a877a05296a5266"
  },
  "courseCode": "CS202",
  "name": "Data Structures",
  "credits": 3,
  "instructor": "Prof. Krishna"
}

```

### Task 3: Fetch a specific student's record by roll number
* Use find() to fetch a student's information using their roll number (CS1002).
```
db.students.findOne({ rollNumber: 105});
```

```
answer 
{
  _id: ObjectId('677cf33d8a877a05296a5265'),
  name: 'mayur',
  rollNumber: 105,
  department: 'Electrical Engineering',
  year: 3,
  subjectsEnrolled: [
    'React',
    'NodeJS'
  ]
}
```

### Task 4: Query all students who are enrolled in a particular course
* Retrieve all students who are enrolled in "MATH101".





### Task 5: Update a student's courses
* Update the student with roll number CS1001 to enroll in an additional course "CS202".
```
db.students.updateOne(
  { rollNumber: "CS1001" },
  { $addToSet: { courses: "CS202" } }
);
```

#### Task 6: Remove a course from a student's courses list
* Remove the course CS101 from the student Mahir's list of enrolled courses.

```
{  
db.students.updateOne(
  { name: "Mahir" }, 
  { $pull: { coursesEnrolled: "CS101" } }
);

}
```

```
 answer 
{
  "_id": {
    "$oid": "677d6b42497eda5b1d1e4029"
  },
  "name": "Mahir",
  "rollNumber": 102,
  "department": "Computer Science",
  "year": 2,
  "coursesEnrolled": [
    "CS103"
  ]
}


```


### Task 7: Find all courses with 3 credits
* Query the courses collection to find all courses where the credits field equals 3.
```
db.courses.find(
  {credits:3});

```
```
{
  _id: ObjectId('677bfdb6c8b1336dc041ce34'),
  courseCode: 'CS101',
  name: 'Introduction to Programming',
  credits: 3,
  instructor: 'Dr. Alice'
}


{
  _id: ObjectId('677bfdb6c8b1336dc041ce36'),
  courseCode: 'EC201',
  name: 'Digital Electronics',
  credits: 3,
  instructor: 'Dr. Carol'
}



{
  _id: ObjectId('677bff8e7ebbafb20c02ab24'),
  courseCode: 'CS101',
  name: 'Introduction to Programming',
  credits: 3,
  instructor: 'vardan sir'
}

{
  _id: ObjectId('677cf4628a877a05296a5266'),
  courseCode: 'CS202',
  name: 'Data Structures',
  credits: 3,
  instructor: 'Prof. Krishna'
}

```



### Task 8: Find students who have enrolled in more than 2 courses
* Use $size operator to query students who are enrolled in more than 2 courses.







### Task 10: Fetch all students from a specific department (e.g., CSE)
* Use a query to find all students in the CSE department.
```
db.students.find({
  department: "CSE"
});
```




