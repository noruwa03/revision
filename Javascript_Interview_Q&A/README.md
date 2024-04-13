# What is Javascript?
**Javascript is a dynamic programming language that runs on the web browser. It is a programming language that coverts static web pages into _interactive and dynamic_ web pages**

## What is Javascript Engine?
**Since Javascript runs on our web browser. They must be a way right? Hence Javascript Engines. This Engines different for each browser. Javascript engines are present in our web browser that executes our javascript code. Chrome (V8), Firefox (Spider monkey) Safari (Javascript core), Microsoft Edge (Chakra).**

# What are Client side and Server side?
**A client is a device, application, or software that request and consumes services or resources from a server**<br>
**A server is a device, computer, or software that provides services, resources or functions to a client**

# Scopes in Javascript
**Scope determins where we define and assess our variables. We have 3 scopes in javascript**
1. Global
2. Blocked or Enclosing
3. Local

### Types of Variables
**When we declare a variable without var, let or const, Out program implicitly declare that variable with var**

# What is Hoisting?
**Hoisting is a javascript behaviour that moves variables, functions declaration to the top of their respective scopes during compilation phase**

# What is JSON?
**JSON stands for Javascript Object Notation, It enables us store data in form of text, Some method are JSON.stringify which converts a native javascript object to a string, JSON.parse which converts a string to a native javascript object**

# What are Variables
**Variables are containers which store our values or data**

# What are the difference between var, let and const
[X] Var keyword is used for variable declaration, and it is global scope, It is hoisted at the top level during compilation phase. <br>
[X] Let is also used for variable declaration, but it is blocked scope (only use within {}), It is hoisted at the top level. <br>
[X] Const is readonly and cannot be reassigned, It is blocked scope, Not hoisted at top level. Const variable can be mutated e.g An array can be declared with the keyword __const__ and we can push/append to the array.

# What are Data Types in Javascript
**We have seven data types in javascript, They are listed below;**
1. String
2. Number
3. Boolean
4. Null
5. Undefined
6. Bigint
7. Symbol

# Difference between Primitive and Non Primitive Data types
#### Primitive
1. They can only store one data
2. They can only store one data type
3. They are fast
4. They use less memory

#### Non Primitive
1. They can store more that one data, and they store the address of the data
2. User defined
3. They are slow
4. They use more memory

# What is the use of the Typeof operator?
**The typeof method is a built-in method available in javascript to check the data types of variables**

# What is type coersion
**Type coersion occurs when the compilier tries to convert one data type to another during the execution of the program.**

# Operator Precedence
**Follows BODMAS, higher precedence are evaluated first**

# Unary, Binary and Tenary operators
[X] Unary -> Single operand <br>
[X] Binary -> Two operand <br>
[X] Tenary -> Three operand

# Short-circuit evaluation in Javascript?

# Type of Condition Statement in Javascript
**We have three types of conditional statements in javascript. They are list below;**
1. If/Else
2. Tenary
3. Switch

**The items listed above are used for decision making**

# Logical and Comparison Operators
#### Logical operators
1. And -> &&
2. Or -> || 
3. Not -> !()

#### Comparison operators
1. Double equal to symbol -> == (This can cause type coersion)
2. Triple equal to symbol -> ===

# Spread and Restof Operator
#### Spread operator uses
1. Copy an array
2. Merging an array
3. Use to take multiple argument in a function

#### Restof operator
**It represent the rest of items in an iterable**

# Arrays in Javascript
**Arrays is used to store a collection of items, Some method available in arrays are coded below it the code block**
```js
const nameArr = ["Anna", "Alex", "Wayne", "Sarah"];

// To get an item from an array, we use an index, arrays start from zero (0).
// To get Alex
console.log(nameArr[1]);

// To add to our array, add to the end
nameArr.push("Fin");

// unshift will add to the start

// To remove
nameArr.pop()

// shift will remove from the start of the array

// To delete we use the keyword delete, but that index will be empty and return null
delete nameArr[0]

```

# Filter and Find
**Filter is used to return a collection of items from an iterable if a certain condition is true** <br>
**Find is used to return the first element in an array if the condition is true**

# Slice
**Slice is used to return a collection of items from an iterable start from an index which is mandatory and an ending index (optional), If an ending index is not provided, it will return items from the start point to the end. Also slice method does not mutate the origin array.**

# Splice
**Splice method is used to add/remove or replace items from an iterable, it modifies / mutates the original array.**

# Concat and Push method in Array
**Concat method is used to combine two or more arrays to form a single array, A push method is used to mutate/add to the collection of items in an array**

# How to access value in Object
1. Dot notation
2. Square bracket notation
3. Expression notation

# Example of Array-Like Objects
1. String
2. Arguments in functions
3. HTML collection

# Ways in we can convert an Array-like Object to an Array
1. Using spread operator syntax
2. Array.from() method
3. Array.prototype.slice.call();


# Loop
**To run a piece of code until a condition is true** <br>
**Loops have four items to check, Controlled variable, Variable incrementation/updation, Condition, and body. Types of loops:**
1. Entry controlled loop: It checks the condition before the execution of the code, e.g For loop, While loop.
2. Exist controlled loop: The condition is not checked before the execution of the code. It must run once before checking the condition. e.g Do while loop.

# Break and Continue keywords
**Break keyword is use to stop the execution of a code if a condition is true, while continue is use to continue the execution of a code and skip the checked condition.**

# Functions
**Functions are methods that perform certain tasks in our code** <br>
**Types of function**
1. Named functions
2. Anonymous functions
3. Function expression
4. Arrow functions
5. IIFE
6. Callback function
7. Higher order functions

# Arguments and Parameters
**Arguments a the actual values passed in a function, while parameters are placeholder for our values in a function**

# Arguments in Function
1. Positional arguments
2. Named arguments
3. Argument objects

# Pure and Impure function
**Pure function is a function that produces the same output for the same input, No side effects, cannot update state. While an impure function is a function that produces different output for the same input, has side effects, can update state**

# Call, Apply and Bind
**They are use to assign an object to the __this__ keyword**

# What is DOM
**DOM (Document Object Model) represent the web page as a tree-like structure that allows javascript to dynamically manipulate the content and structure of the web page**

# DOM create, select, modify, remove
##### Create
[X] createElement
[X] appendChild

#### Select
[X] getElementByID
[X] getElementByClassName
[X] getElementByTagName

#### Modify
[X] innerHTML
[X] textContent
[X] setAttribute
[X] removeAttribute
[X] style.property

#### Remove
[X] remove
[X] removeChild

#### Function
[X] addEventListener
[X] removeEventListener