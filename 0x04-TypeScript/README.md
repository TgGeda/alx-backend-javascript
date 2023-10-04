# Typescript 👩‍💻

This readme file provides instructions and explanations for the tasks outlined below.

## Task 0: Creating an interface for a student

### Instructions
1. Copy the provided configuration files (package.json, .eslintrc.js, tsconfig.json, webpack.config.js) into the `task_0` directory.
2. Write your code in the `main.ts` file.
3. Create an interface named `Student` that accepts the following elements: `firstName` (string), `lastName` (string), `age` (number), and `location` (string).
4. Create two students and store them in an array named `studentsList`.
5. Use Vanilla JavaScript to render a table and append a new row to the table for each student in the `studentsList` array.
6. Each row should contain the first name of the student and the location.

### Requirements
1. When running, Webpack should return "No type errors found".
2. Every variable should use TypeScript when possible.

## Task 1: Let's build a Teacher interface

### Instructions
1. Create a directory named `task_1` and copy the provided configuration files (package.json, tsconfig.json, webpack.config.js) into this folder.
2. Create an interface named `Teacher` with the following attributes:
   - `firstName` (string) and `lastName` (string). These two attributes should only be modifiable when a Teacher is first initialized.
   - `fullTimeEmployee` (boolean): This attribute should always be defined.
   - `yearsOfExperience` (number): This attribute is optional.
   - `location` (string): This attribute should always be defined.
3. Add the possibility to add any attribute to the `Teacher` object without specifying the name of the attribute.

Example:
```javascript
const teacher3: Teacher = {
  firstName: 'John',
  fullTimeEmployee: false,
  lastName: 'Doe',
  location: 'London',
  contract: false,
};

console.log(teacher3);

// should print
// Object
// contract: false
// firstName: "John"
// fullTimeEmployee: false
// lastName: "Doe"
// location: "London"
```

## Task 2: Extending the Teacher class

### Instructions
1. Write an interface named `Directors` that extends the `Teacher` interface.
2. The `Directors` interface requires an attribute named `numberOfReports` (number).

Example:
```javascript
const director1: Directors = {
  firstName: 'John',
  lastName: 'Doe',
  location: 'London',
  fullTimeEmployee: true,
  numberOfReports: 17,
};
console.log(director1);

// should print
// Object
// firstName: "John"
// fullTimeEmployee: true
// lastName: "Doe"
// location: "London"
// numberOfReports: 17
```

## Task 3: Printing teachers

### Instructions
1. Write a function named `printTeacher` that accepts two arguments: `firstName` and `lastName`.
2. The function should return the first letter of the `firstName` and the full `lastName` (e.g., `J. Doe`).

Example: 
```javascript
printTeacher("John", "Doe") -> J. Doe
```

3. Write an interface for the function named `printTeacherFunction`.

Thank you for reading this readme file. If you have any questions or need further assistance, please feel free to ask.

 

## Task 4: Writing a class

### Class: StudentClass

The `StudentClass` class has the following properties and methods:

#### Constructor

- Accepts `firstName` (string) and `lastName` (string) arguments.

#### Methods

1. `workOnHomework()`: Returns the string "Currently working".
2. `displayName()`: Returns the `firstName` of the student.

### Interface: StudentClassInterface

The `StudentClass` class and its constructor are described through the `StudentClassInterface` interface.

## Task 5: Advanced types Part 1

### Interface: DirectorInterface

The `DirectorInterface` interface has the following methods:

1. `workFromHome()`: Returns the string "Working from home".
2. `getCoffeeBreak()`: Returns the string "Getting a coffee break".
3. `workDirectorTasks()`: Returns the string "Getting to director tasks".

### Interface: TeacherInterface

The `TeacherInterface` interface has the following methods:

1. `workFromHome()`: Returns the string "Cannot work from home".
2. `getCoffeeBreak()`: Returns the string "Cannot have a break".
3. `workTeacherTasks()`: Returns the string "Getting to work".

### Class: Director

The `Director` class implements the `DirectorInterface` interface and has the following methods:

1. `workFromHome()`: Returns the string "Working from home".
2. `getCoffeeBreak()`: Returns the string "Getting a coffee break".
3. `workDirectorTasks()`: Returns the string "Getting to director tasks".

### Class: Teacher

The `Teacher` class implements the `TeacherInterface` interface and has the following methods:

1. `workFromHome()`: Returns the string "Cannot work from home".
2. `getCoffeeBreak()`: Returns the string "Cannot have a break".
3. `workTeacherTasks()`: Returns the string "Getting to work".

### Function: createEmployee

The `createEmployee` function creates an instance of either `Director` or `Teacher` based on the salary argument. It accepts the following arguments:

- `salary` (either number or string): The salary of the employee.

If `salary` is a number and less than 500, it returns a new instance of `Teacher`. Otherwise, it returns a new instance of `Director`.

 ## Tas 6 : Creating functions specific to employees

## Employee Functions

# Employee Functions

This repository contains functions specific to employees, including the functions `isDirector` and `executeWork`.

## isDirector

The `isDirector` function is a type predicate that accepts an `employee` as an argument. It determines whether the employee is a director. 

### Arguments

- `employee` (object): The employee object to be checked.

### Return Value

- `true` (boolean): If the employee is a director.
- `false` (boolean): If the employee is not a director.

## executeWork

The `executeWork` function accepts an `employee` as an argument. It performs specific tasks based on the type of employee.

### Arguments

- `employee` (object): The employee object for which the work needs to be executed.

### Behavior

- If the `employee` is a director, the function will call the `workDirectorTasks` function.
- If the `employee` is a teacher, the function will call the `workTeacherTasks` function.

## Example Usage

```javascript
executeWork(createEmployee(200));
// Expected Output: Getting to work

executeWork(createEmployee(1000));
// Expected Output: Getting to director tasks
```

 # Task 7: String literal types

## Description
This task involves creating a String literal type named `Subjects` that allows a variable to have the value "Math" or "History" only. Additionally, you need to write a function named `teachClass` that takes `todayClass` as an argument and returns the string "Teaching Math" if `todayClass` is "Math", and "Teaching History" if `todayClass` is "History".

## Example

```typescript
teachClass('Math');
// Output: Teaching Math

teachClass('History');
// Output: Teaching History
```

# Task 8: Ambient Namespaces

## Description
In this task, you need to create a directory called `task_3` and copy the following configuration files into it: `package.json`, `webpack.config.js`, and `tsconfig.json`.

Next, you need to create a file named `interface.ts` inside the `task_3` directory. Inside this file, you should:

- Create a type `RowID` and set it equal to `number`.
- Create an interface `RowElement` that contains the following fields:
  - `firstName: string`
  - `lastName: string`
  - `age?: number`

After that, you are required to save entities to a database. Due to time constraints, you cannot write a connector to the database. Instead, you have decided to download a library called `crud.js`. Copy the `crud.js` file into the `task_3/js` directory.

Create an ambient file within `task_3/js` called `crud.d.ts`. This file should contain the type declarations for each crud function. Import `RowID` and `RowElement` from `interface.ts` at the top of the `crud.d.ts` file.

In `main.ts`:

- Include a triple slash directive at the top of the file that includes all the dependencies from `crud.d.ts`.
- Import the `RowID` type and `RowElement` from `interface.ts`.
- Import everything from `crud.js` as `CRUD`.
- Create an object called `row` with the type `RowElement` and set the fields to the following values:
  - `firstName: Guillaume`
  - `lastName: Salva`
- Create a constant variable named `newRowID` with the type `RowID` and assign it the value of the `insertRow` command.
- Next, create a constant variable named `updatedRow` with the type `RowElement` and update `row` with an `age` field set to `23`.
- Finally, call the `updateRow` and `deleteRow` commands.

## Example

```typescript
const obj = {firstName: "Guillaume", lastName: "Salva"};
CRUD.insertRow(obj)
// Output: Insert row {firstName: "Guillaume", lastName: "Salva"}

const updatedRow: RowElement = { firstName: "Guillaume", lastName: "Salva", age: 23 };
CRUD.updateRow(newRowID, updatedRow);
// Output: Update row 125 {firstName: "Guillaume", lastName: "Salva", age: 23}

CRUD.deleteRow(125);
// Output: Delete row id 125
```

## Requirements
- When running `npm run build`, no TypeScript errors should be displayed.
- Every variable should use TypeScript when possible.
- Both the main file and the ambient file should import the types defined in the interface file.
- You can test your ambient file by looking at the intellisense of your IDE when using the 3rd party functions.

# Task 9: Namespace & Declaration merging

# Task 4: Namespace & Declaration Merging

## Description
This task involves creating a new directory named `task_4` and copying the provided `tsconfig.json` and `package.json` files into it. Inside the `task_4/js/subjects` directory, you need to create several TypeScript files and make modifications to existing files.

## Installation
To get started with this task, follow the steps below:

1. Create a new directory named `task_4`.
2. Copy the provided `tsconfig.json` and `package.json` files into the `task_4` directory.
3. Inside the `task_4/js/subjects` directory, create the following files:
   - `Teacher.ts`
   - `Subject.ts`
   - `Cpp.ts`
   - `React.ts`
   - `Java.ts`

## Usage
### Teacher.ts
In the `Teacher.ts` file, write an interface named `Teacher` inside a namespace named `Subjects`. The `Teacher` interface should have two required attributes: `firstName` and `lastName`, both of type `string`.

### Subject.ts
In the `Subject.ts` file, write a class named `Subject` inside the `Subjects` namespace. The `Subject` class should have one attribute named `teacher`, which implements the `Teacher` interface. Additionally, the class should have a setter method named `setTeacher` that accepts a teacher as an argument and sets the instance attribute `teacher` with it.

### Cpp.ts
In the `Cpp.ts` file, make the following modifications inside the `Subjects` namespace using declaration merging:

1. Add a new optional attribute named `experienceTeachingC` of type `number` to the `Teacher` interface.
2. Create a class named `Cpp` that extends from `Subject`.
3. Write a method named `getRequirements` inside the `Cpp` class that returns a string: "Here is the list of requirements for Cpp".
4. Write a method named `getAvailableTeacher` inside the `Cpp` class that returns a string: "Available Teacher: <first name of teacher>". If the teacher doesn't have any experience in teaching C, the method should return: "No available teacher".

### React.ts
In the `React.ts` file, write a class named `React` inside the `Subjects` namespace.

1. Add a new optional attribute named `experienceTeachingReact` of type `number` to the `Teacher` interface.
2. Write a method named `getRequirements` inside the `React` class that returns a string: "Here is the list of requirements for React".
3. Write a method named `getAvailableTeacher` inside the `React` class that returns a string: "Available Teacher: <first name of teacher>". If the teacher doesn't have any experience in teaching React, the method should return: "No available teacher".

### Java.ts
In the `Java.ts` file, write a class named `Java` inside the `Subjects` namespace.

1. Add a new optional attribute named `experienceTeachingJava` of type `number` to the `Teacher` interface.
2. Write a method named `getRequirements` inside the `Java` class that returns a string: "Here is the list of requirements for Java".
3. Write a method named `getAvailableTeacher` inside the `Java` class that returns a string: "Available Teacher: <first name of teacher>". If the teacher doesn't have any experience in teaching Java, the method should return: "No available teacher".

 

# Task 10: Update task_4/js/main.ts

 # Task 4

## Description
This task involves updating the `main.ts` file located in the `task_4/js` directory of the GitHub repository `alx-backend-javascript`. The following changes need to be made:

1. Create and export a constant `cpp` for Cpp Subjects.
2. Create and export a constant `java` for Java Subjects.
3. Create and export a constant `react` for React Subjects.
4. Create and export a `Teacher` object named `cTeacher` with `experienceTeachingC` set to 10.
5. For the Cpp subject:
   - Log the string "C++" to the console.
   - Set `cTeacher` as the teacher.
   - Call the `getRequirements` and `getAvailableTeacher` methods and print the strings they return.
6. For the Java subject:
   - Log the string "Java" to the console.
   - Set `cTeacher` as the teacher.
   - Call the `getRequirements` and `getAvailableTeacher` methods and print the strings they return.
7. For the React subject:
   - Log the string "React" to the console.
   - Set `cTeacher` as the teacher.
   - Call the `getRequirements` and `getAvailableTeacher` methods and print the strings they return.

  

# Task 5

## Description
This task involves creating a directory named `task_5` and copying the following configuration files into the root of `task_5`:

- `package.json`
- `tsconfig.json`
- `webpack.config.js`

In the `task_5/js/main.ts` file, the following changes need to be made:

1. Create two interfaces named `MajorCredits` and `MinorCredits`.
2. Each interface should define a number property named `credits`.
3. Add a `brand` property to each interface in order to uniquely identify them.
4. Create two functions named `sumMajorCredits` and `sumMinorCredits`.
5. Each function should take two arguments `subject1` and `subject2`.
6. The `sumMajorCredits` function should return a `MajorCredits` value, and the `sumMinorCredits` function should return a `MinorCredits` value.
7. Each function should sum the credits of the two subjects.

 
