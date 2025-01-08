# mongodb
##  Practice Assignments
### Task 1: Create a "CodingGita Students" database
### Create a new MongoDB database called CodingGita. Add two collections:

* students: Name, roll number, department, year, courses enrolled.
* courses: Course code, name, credits, instructor.


```
{
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '2nd',
  coursesEnrolled: [
    'CS101'
  ]
}

{
  _id: ObjectId('677bff8e7ebbafb20c02ab23'),
  name: 'ashwani',
  rollNumber: 'CG124',
  department: 'Electronics',
  year: '3rd',
  coursesEnrolled: [
    'EC201'
  ]
}


```


## Task 2: Perform CRUD operations
* Add a few more students and courses to the database.
* Query data based on:

* Department (e.g., "Computer Science").
* db.students.find({ department: "Computer Science" })

```
{
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '2nd',
  coursesEnrolled: [
    'CS101'
  ]
}
```


* Year (e.g., "2").
* db.students.find({ year: "2nd" })

```
{
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '2nd',
  coursesEnrolled: [
    'CS101'
  ]
}
```

* Courses enrolled (e.g., "CS101").
```
{
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '2nd',
  coursesEnrolled: [
    'CS101'
  ]
}
```



* Update the courses for a specific student (e.g., adding a new course).

```
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

```

* Delete a student or course from the database.
* db.courses.deleteOne({ courseCode: "CS101" })
db.courses.deleteOne({ courseCode: "CS101" })

```
{
 {
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '2nd',
}
}
```



# 10 First Assignment
### 1. Create the Database and Collections
#### Step 1: Create the Database
* use codinggita  // Switch to the CodingGita database. If it doesn't exist, MongoDB will create it automatically.

``` 
{ ok: 1 }
```
#### Step 2: Create the students collection
* db.createCollection("students");
```
 { ok: 1 }
```

#### Step 3: Create the subjects collection
* db.createCollection("subjects");
```
 { ok: 1 }
```
### 2. Insert Sample Data
#### Step 1: Insert sample data into the students collection

```
db.students.insertMany([
  { 
    "name": "Jenil",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS", "MongoDB"]
  },
  { 
    "name": "Mahir",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS"]
  },
  { 
    "name": "Arjun",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "subjectsEnrolled": ["Circuit Theory", "Electrical Machines"]
  }
]);

```
```
 * result 
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('677c2b3148f405d68dfc6b61'),
    '1': ObjectId('677c2b3148f405d68dfc6b62'),
    '2': ObjectId('677c2b3148f405d68dfc6b63')
  }
}
```

#### Step 2: Insert sample data into the subjects collection

```
db.subjects.insertMany([
  { 
    "subjectName": "React",
    "topics": [
      "JSX", 
      "Components", 
      "State", 
      "Props", 
      "Hooks"
    ]
  },
  { 
    "subjectName": "NodeJS", 
    "topics": [
      "Modules", 
      "Express", 
      "File System", 
      "Asynchronous Programming"
    ]
  },
  { 
    "subjectName": "MongoDB", 
    "topics": [
      "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
    ]
  }
]);

```
```
* result


{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('677c2c3348f405d68dfc6b64'),
    '1': ObjectId('677c2c3348f405d68dfc6b65'),
    '2': ObjectId('677c2c3348f405d68dfc6b66')
  }
}

```
### 3. Querying Data
#### Step 1: Query students based on department
To find all students in the Computer Science department:
```
* db.students.find({ "department": "Computer Science" });
```

```
* result
{
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '2nd',
  coursesEnrolled: [
    'CS101',
    'CS103'
  ]
}


{
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil',
  rollNumber: 101,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir',
  rollNumber: 102,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS'
  ]
}
```
#### Step 2: Query students based on year
```
db.students.find({ "year": 2 });
```
```
result

{
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil',
  rollNumber: 101,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir',
  rollNumber: 102,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS'
  ]
}

```
#### Step 3: Query students by subject enrollment

```
db.students.find({ "subjectsEnrolled": "React" });
```

```
result 
{
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil',
  rollNumber: 101,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir',
  rollNumber: 102,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS'
  ]
}

```

#### Step 4: Query subjects with a specific topic

```
db.subjects.find({ "topics": "Hooks" });
```
```
result

{
  _id: ObjectId('677c2c3348f405d68dfc6b64'),
  subjectName: 'React',
  topics: [
    'JSX',
    'Components',
    'State',
    'Props',
    'Hooks'
  ]
}
```
### 4. Updating Data
#### Step 1: Add a subject for a student
```
db.students.updateOne(
  { "name": "Mahir" },
  { $push: { "subjectsEnrolled": "MongoDB" } }
);
```
```
answer

{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b62"
  },
  "name": "Mahir",
  "rollNumber": 102,
  "department": "Computer Science",
  "year": 2,
  "subjectsEnrolled": [
    "React",
    "NodeJS",
    "MongoDB",
    "javascript"
  ]
}

```

#### Step 2: Update a student's year

```
db.students.updateOne(
  { "name": "Arjun" },
  { $set: { "year": 4 } }
);
```
```
answer


{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b63"
  },
  "name": "Arjun",
  "rollNumber": 103,
  "department": "Electrical Engineering",
  "year": 4,
  "subjectsEnrolled": [
    "Circuit Theory",
    "Electrical Machines"
  ]
}

```

#### Step 3: Add a new topic to a subject

```
db.subjects.updateOne(
  { "subjectName": "React" },
  { $push: { "topics": "Advanced Hooks" } }
);
````
```
answer

{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b64"
  },
  "subjectName": "React",
  "topics": [
    "JSX",
    "Components",
    "State",
    "Props",
    "Hooks",
    "Advanced Hooks"
  ]
}

```

### 5. Deleting Data

#### Step 1: Delete a student record

```
db.students.deleteOne({ "name": "Arjun" });
```
```
answer

delete recode

```
#### Step 2: Delete a subject from the subjects collection
```
db.subjects.deleteOne({ "subjectName": "MongoDB" });

```

```
answer

delete subject
```

### 6. More Practice Tasks
### Task 1: Add multiple students
* Insert at least 5 students into the students collection with unique roll numbers, names, departments, years, and subjects enrolled.

```
db.students.insertMany([
  { 
    "name": "Jenil",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS", "MongoDB"]
  },
  { 
    "name": "Mahir",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS"]
  },
  { 
    "name": "Arjun",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "subjectsEnrolled": ["Circuit Theory", "Electrical Machines"]
  }
]);
```
```
answer


{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b61"
  },
  "name": "Jenil",
  "rollNumber": 101,
  "department": "Computer Science",
  "year": 4,
  "subjectsEnrolled": [
    "React",
    "NodeJS",
    "MongoDB"
  ]
}

{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b62"
  },
  "name": "Mahir",
  "rollNumber": 102,
  "department": "Computer Science",
  "year": 2,
  "subjectsEnrolled": [
    "React",
    "NodeJS",
    "MongoDB",
    "javascript"
  ]
}



{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b63"
  },
  "name": "Arjun",
  "rollNumber": 103,
  "department": "Electrical Engineering",
  "year": 3,
  "subjectsEnrolled": [
    "Circuit Theory",
   "Electrical Machines"
  ]
}
```


### Task 2: Add multiple subjects
* Insert 4 subjects into the subjects collection, each with 3 to 5 topics.
```
db.subjects.insertMany([
  { 
    "subjectName": "React",
    "topics": [
      "JSX", 
      "Components", 
      "State", 
      "Props", 
      "Hooks"
    ]
  },
  { 
    "subjectName": "NodeJS", 
    "topics": [
      "Modules", 
      "Express", 
      "File System", 
      "Asynchronous Programming"
    ]
  },
  { 
    "subjectName": "MongoDB", 
    "topics": [
      "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
    ]
  }
]);
```
```
answer

{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b64"
  },
  "subjectName": "React",
  "topics": [
    "JSX",
    "Components",
    "State",
    "Props",
    "Hooks",
    
  ]
}

{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b65"
  },
  "subjectName": "NodeJS",
  "topics": [
    "Modules",
    "Express",
    "File System",
    "Asynchronous Programming"
  ]
}


{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b65"
  },
  "subjectName": "NodeJS",
  "topics": [
    "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
  ]
}
```


### Task 3: Query students based on subject enrollment
* Query the students collection to find all students who are enrolled in NodeJS.

```
db.students.find({ "subjectsEnrolled": "React" });
```

```
answer

{
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil',
  rollNumber: 101,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir',
  rollNumber: 102,
  department: 'Computer Science',
  year: 2,
  subjectsEnrolled: [
    'React',
    'NodeJS'
  ]
}


{
  _id: ObjectId('677c2b3148f405d68dfc6b63'),
  name: 'Arjun',
  rollNumber: 102,
  department: 'Electrical Engineering',
  year: 3,
  subjectsEnrolled: [
    'React',
    'NodeJS'
  ]
}
```

### Task 4: Add a new topic to a subject
* Add a new topic to the NodeJS subject.

```
db.subjects.updateOne(
  { "subjectName": "React" },
  { $push: { "topics": "NodeJS" } }
);
````
```
answer

{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b64"
  },
  "subjectName": "React",
  "topics": [
    "JSX",
    "Components",
    "State",
    "Props",
    "Hooks",
    "Advanced Hooks",
    "NodeJS"
  ]
}

```


### Task 5: Query subjects with multiple topics
* Query the subjects collection to find subjects that contain at least 4 topics.

```
db.subjects.find({
  topics: { $size: 4 }
});

```

```
answer

{
  _id: ObjectId('677c2c3348f405d68dfc6b65'),
  subjectName: 'NodeJS',
  topics: [
    'Modules',
    'Express',
    'File System',
    'Asynchronous Programming'
  ]
}
```

### Task 6: Update student enrollment
* Add the subject "React Native" to Jenil's subjects.
```
db.students.updateOne(
  { "name": "Jenil" },
  { $push: { "subjectsEnrolled": "React Native" } }
);
```

```
answer
{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b61"
  },
  "name": "Jenil",
  "rollNumber": 101,
  "department": "Computer Science",
  "year": 4,
  "subjectsEnrolled": [
    "React",
    "NodeJS",
    "MongoDB",
    "React Native"
  ]
}
```

### Task 7: Query all students
* Query all students in the database and print out their names and enrolled subjects.

```
db.students.find(
  {}, 
  { name: 1, subjectsEnrolled: 1}
);
```
```
answer
{ 
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil',
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB',
    'React Native'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir',
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB',
    'javascript'
  ]
}



{
  _id: ObjectId('677c2b3148f405d68dfc6b63'),
  name: 'Arjun',
  subjectsEnrolled: [
    "CRUD Operations", 
      "Aggregation", 
      "Indexes"
  ]
}
```


### Task 8: Update multiple students' year
* Update the year for all students in the Computer Science department to year 3.

``` 
{
db.students.updateMany(
  {"department": "Computer Science"},
  {$set: {year:'3rd'}});
}
```
```
answer 

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
},


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
```


### Task 9: Add new topics to multiple subjects
* Add new topics to React, NodeJS, and MongoDB subjects. Ensure each subject gets at least one new topic.
```
db.subjects.updateOne(
  { subjectName: "React" },
  { $push: { topics: "react" } },
  { $push: { topics: "NodeJs" } },
  { $push: { topics: "Mongodb" } }
);
```

```
answer


{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b64"
  },
  "subjectName": "React",
  "topics": [
    "JSX",
    "Components",
    "State",
    "Props",
    "Hooks",
    "Advanced Hooks",
    "react"
    "NodeJS",
    "Mongodb"
    
  ]
}
```

### Task 10: Remove a topic from a subject
* Remove the topic "Express" from the NodeJS subject.

```
{
  db.subjects.updateOne(
  { subjectName: "NodeJS" },
  { $pull: { topics: "Express" } }
);
}

```


```
answer


{
  "_id": {
    "$oid": "677c2c3348f405d68dfc6b65"
  },
  "subjectName": "NodeJS",
  "topics": [
    "Modules",
    "File System",
    "Asynchronous Programming",
    "Event Loop"
  ]
}


```

### Task 11: Query all students in a specific year
* Query and return all students in year 2 or year 3.

```
db.students.find(
  {$or:[{year : "2nd"},{year:"3rd"}]});
```
```
answer


{
  _id: ObjectId('677bff8e7ebbafb20c02ab22'),
  name: 'nagesh jagtap',
  rollNumber: 'CG123',
  department: 'Computer Science',
  year: '3rd',
  coursesEnrolled: [
    'CS101',
    'CS103'
  ]
}

{
  _id: ObjectId('677bff8e7ebbafb20c02ab23'),
  name: 'ashwani',
  rollNumber: 'CG124',
  department: 'Electronics',
  year: '3rd',
  coursesEnrolled: [
    'EC201'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil',
  rollNumber: 101,
  department: 'Computer Science',
  year: '3rd',
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB',
    'React Native'
  ]
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir',
  rollNumber: 102,
  department: 'Computer Science',
  year: '3rd',
  subjectsEnrolled: [
    'React',
    'NodeJS',
    'MongoDB',
    'javascript'
  ]
}

```


### Task 12: Delete a student by roll number
* Delete a student from the database using their roll number.

```
db.students.deleteOne(
  {rollNumber:"103"}
);

```
```
answer
delete student database 

{
  "_id": {
    "$oid": "677c2b3148f405d68dfc6b63"
  },
  "name": "Arjun",
  "rollNumber": 103,
  "department": "Electrical Engineering",
  "year": 3,
  "subjectsEnrolled": [
    "Circuit Theory",
   "Electrical Machines"
  ]
}


```


### Task 13: Delete all students from a department
* Delete all students who belong to the Electrical Engineering department.

```
{   
db.student.deleteMany(
  {department:"Electrical Engineering"}
);
}
```

```
answer 
delete student Electrical Engineering department.
```

### Task 14: Retrieve all topics for a subject
*Query the MongoDB subject and retrieve all topics listed for it.


```
db.subjects.find(
  { subjectName: "NodeJS" },
  { topics: 1 }
);


```

```
answer


{
  _id: ObjectId('677c2c3348f405d68dfc6b65'),
  topics: [
    'Modules',
    'File System',
    'Asynchronous Programming',
    'Event Loop'
  ]
}
```



### Task 15: Count the number of subjects in which a student is enrolled
* Write a query that returns the number of subjects each student is enrolled in.

```
db.students.aggregate([
  { $project: { name: 1, subject:1 } }
]);

``` 
```
answer

{
  _id: ObjectId('677c2b3148f405d68dfc6b61'),
  name: 'Jenil'
}

{
  _id: ObjectId('677c2b3148f405d68dfc6b62'),
  name: 'Mahir'
}



```

















