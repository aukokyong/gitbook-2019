# functions

In the next 12 weeks we will learn to write web applictation software.

As we build up to an example of a complete application, we'll be starting with the fundamental building blocks of that application (and of all software)

First we'll see functions as the fundamental building block of all programs.

Functions are the atomic computation structure of a program- something that takes input, computes and makes output.

As programmers the definition of functions is the first tool we'll define to begin the process of solving complex problems.

```js

var add = function(a,b){

  return a + b;
};
```

##### function definition

A function is a program definiton of at least one operation that gives back a value (the result of some operations)

The return keyword: gives data as output of the function


### functions as operations on data

A real world example is a function that calculates area of a disk:

```

var areaOfDisk = function( radius ){

  return 3.1415 * radius;
}
```

#### naming of parameters / variables

Design and writing of programs menas we must define the data we are operating on. We define this data firstly by naming what it represents.

### composition of operations

As the goal of our programs grows in complexity, the we want ot be able to slowly grow our programs and manage their complexity.

We need a method that has several attributes:

- modular / composed of parts
- easily verifiable
- easy to understand at each level

To do that, we will be trying to make a series of functions that rely upon each other to compute and trasform our inputs from start to finish.

We'll call this function composition.

Example:

We want to know the area of a ring instead of a disk.

We can define the area of a ring as the area of one disk minus the other. We can create a function that encapsulates this:

```
var areaOfRing = function(d1, d2){
  var ring = areaOfDisk(d1) - areaOfDisk(d2);
  return ring;
}

```

### functions built into the language
We've already seen `parseInt`. What does parseInt return?

There are some other functions we already know how to call:

```
console.log()
alert()
```

Some others are:
```
var weather = "sunny";
weather.toUpperCase();
weather.toLowerCase();
weather.charAt();
```

What do these do? Google them to see how they work.

What other functions are there?

## word problems

The reason we engage computers to do stuff for us is because we want them to process data and come up with some output for us.

The tasks we want computers to accomplish always begin with a very general statement about what the task is.

One of the main jobs of a programmer is to understand what a plain-language problem statement means, and how to represent that problem in code.

Example:

You are tasked with creating a program for a restaurant that will tell the owners how much an employee's wages are each month. The employees are paid by the hour.

Here you must infer that the task is to take the employees hourly wage and multiply it by the number of hours worked.

You are taking input and giving output.

Your solution might look something like this:
```
var calculateWage = function( hourlyRate, hoursWorked ){
  return hourlyRate * hoursWorked;
};
```

We made a couple of program design descisions here:

- we defined our parameters by naming them what they represent
- we did a multiplication operation on them
- we returned the result
- we made an implicit assumption as to the js data type of the parameters


## function writing process

We will be implementing a specific process for translating our word problems into functions that run on data.

 1. Data Description

Describe what data your function deals with

```
hourlyRate - the rate earned per hour
hoursWorked - number of hours worked
```

 2. Data Examples

Write actual examples.
```
var hoursWorked = 5;
```

 3. Function Signature
```
hourlyRate (number), hoursWorked (number) --> monthlyWage (number)
```

 4. Function Purpose
To calculate the monthly wage of a worker given a rate and the hours worked.

 5. Function Header
calculateWage( hourlyRate, hoursWorked )

 6. Code
Make it work.

 7. Functional Examples
var monthlyWage = calculateWage( 15, 40 ); // will equal 600

 8. Test
Run the examples yourself.

 9. Review & Refactor
If your code is sloppy or could be changed to be more abstract, make those changes. Have you repeated yourself? Is there a way to make your code more clear? Easier to read?

A completed example:
```
// calculateWage

// data description
// hourlyRate - the rate earned per hour
// hoursWorked - number of hours worked

// input example
// var hoursWorked = 5;

// function signature
// hourlyRate (number), hoursWorked (number) --> monthlyWage (number)

// function purpose
// To calculate the monthly wage of a worker given a rate and the hours worked.

// function header
//calculateWage( hourlyRate, hoursWorked )

// functional examples
// var monthlyWage = calculateWage( 15, 40 ); // will equal 600

var calculateWage = function( hourlyRate, hoursWorked ){
  return hourlyRate * hoursWorked;
};
```

### pairing exercises

Repeat the examples above.

Before you write any running code, be sure to write all of the function writing steps first.

Write a function that takes the parameters width, length and height of a rectangluar shape and computes the volume.

Write a function that takes in those same three numbers and computes the total surface area of the shape.

Write a function that calculates the volume of a sphere.

Write a function that calculates the surface area of a sphere.

Write a function that takes two string arguments. The function should return a single string with the two words combined.

### further

Note: you will need `.length` for this:
```
var weather = "sunny";
console.log( weather.length ); // outputs 5
```

Write a function that takes in a string argument. The function should return the string length.

Write a function that takes in two string arguments. The function should return the longer word.

Write a function that takes in two string arguments. The function should return a single string that is the combination of the two arguments. The longer string should be first.