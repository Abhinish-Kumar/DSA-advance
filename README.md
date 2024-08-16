# DSA-advance
This course is not for beginner 



## What is a **Structure**?

A **structure** is a way to group different pieces of related information together. Think of it like a container that holds various items that are logically connected.
eg:- 
1. If you want to store details about a student, such as their name, roll number, and marks, you can use a structure to keep all this information together in one place.
2. Similarly, for a complex number, you can group its real part and imaginary part together using a structure.

In simple terms, a structure is like a blueprint that organizes complex data in a clear and meaningful way. Each item within the structure is called a **member**.


## How to Define a Structure?

"In C programming, a structure is a user-defined data type that allows you to combine data items of different types under a single name. You can think of it as a template for creating complex data types that group multiple variables."

==> To define a structure in C, you use the struct keyword followed by the structure's name and a block of code that lists the data members (variables) it will contain. Here's the general format:

```c
struct structureName {
    dataType memberName1;
    dataType memberName2;
    // ... more members can be added here
};
```

```c
struct point {
    float xcoord;  // Member to store the x-coordinate
    float ycoord;  // Member to store the y-coordinate
};
//for a point in a graph
```

In JavaScript, you don't have a built-in structure like in C, but you can achieve the same functionality using objects. An object in JavaScript is a collection of key-value pairs, and it can be used to group related data together, similar to a structure in C.

```javascript
// Defining an object to represent a point
let point = {
    xcoord: 0.0, // Property to store the x-coordinate
    ycoord: 0.0  // Property to store the y-coordinate
};

// Accessing the members
console.log(point.xcoord); // Output: 0.0
console.log(point.ycoord); // Output: 0.0
```









