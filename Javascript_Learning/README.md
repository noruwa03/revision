# Javascript Interview Questions and Study

### *Ways we can create objects in Javascript*
1. Using the Object literal syntax
2. Object.create(null) method
3. Function constructor
4. From instantiating a class
5. Object constructor

__The code below demonstrates some ways in which objects can be created in javascript__
```js
--Object literal syntax--
const user = {
    name: "Alex Finnland",
    age: 20
}

--Object.create(null) method--
const user = Object.create(null);

--Function constructor--
function log(name, age) {
    this.name = name,
    this.age = age
}

const logDetail = new log("Anna Walker", 28);

--Instantiating a class--
class Human {
    constructor(name, hairColor) {
        this.name = name,
        this.hairColor = hairColor
    }
}

const humanOne = new Human("Jane", "Red");

--Object constructor--
var obj = new Object();
```

### **What do you understand by JSON**
#### JSON stands for Javascript object notation, it is a text based data format. some methods are provided below
```js
// This converts a string to a native object
JSON.parse();

// This converts a native object to a string
JSON.stringify();

```

### **Slice and Splice method in Array**
*Slice: method is used to return a collection of items in an array from a given start point (index), to an end (if provided), if the end point (index) is not provided, it will return a collection of items starting from the start point to the end. This method does not mutate the origin array.*

*Splice: method is used to insert/delete items from an array, the start point is required, while the endpoint is optional. It returns the delete subset of the array, and it modifies the original array.*

### Double equal (==) and Triple equal (===) Operator
**When using __==__ operator, only the variable is being checked, and this can lead to type coersion (Converting of one data type to another on both sides). While __===__ operator, checks both variable and data type.**

### What a lambda or Array functions
**Short syntax or short way of writing function expression**

### First class function
**A first class function, is a function that can be treated as a variable, have a function as an argument and can also return a function.**

### First order function
**A function that cannot be treated as a variable and does not take a function as an argument, does not return a function**

### Higher order function
**Exactly the same as a first class function**

### Variable declaration keywords and scopes: Local, Enclosing, Global, Built-in
**Var: Global scoped, hoisted** <br>
**Let: this is blocked scope, it is hoisted but not initialized** <br>
**Const: Read-only, cannot be reassigned** <br>

### Immediately invoked function expression
**A function that is being executed as the program is being loaded.**

### Memoization
**Memoization is a functional programming technique use to increase a function performance by caching the previously computed result.

### Modules
**Modules are small units of independent reusable codes. Benefits are maintenance, reusability, name space.**

### Service worker
#### A service worker is basically a javascript script that runs in the background. It does not require user interaction such as push notification

### Web Storage
##### We have there web storage API in our web.
1. Cookie
2. LocalStorage
3. SessionStorage

__Difference between the three of them in terms of *Accessed by client or server*, *Lifetime*, *SSL support*, *Max data size*__

**Cookie can be accessed by both client and server, expiry data can be set, has SSL support, max data size is 4kb** <br>
**LocalStorage can be accessed by only client side, no expiry data (only when we decide to delete it), No SSL support, max data size is 5mb** <br>
**SessionStorage can be accessed by on client side, it expires when the browser tab is being closed, No SSL support, max data size is 5mb**

### Promise
**Promise is used in asynchronous operations. It is a object that returns a single value in the future over some time with the resolved value, or a reason why it didn't resolve the value (rejected). There are three states, _Pending_, _Rejected_, and _Fulfilled_.**

### Callback
**A function that is passed in as an argument in another function**

### Callback Hell
**When a function has nested multiple callback which makes code harder to read, and debug**

### PWAs: Progressive Web Apps
**These are mobile apps that are delivered through the web, built using common web technologies tools such as HTML, CSS, and Javascript.**

### Polyfill
**It is a piece of javascript code that provides modern functionality to older web browser that do not natively support it.**

### Tree shaking: Dead code elimination, unused modules will not be included in the bundle during the build process. It is implemented in Rollup and Webpack bundlers.

### Regex, Regular Expression.
**It is a sequence of characters that forms a search pattern**

### What is Typescript
##### Typescript is a typed superset of javascript, it adds types to javascript and complies to plain javascript.

### Emuns
#### Enums are set of predefined named constant. The first value is always zero unless reassigned.

### Some Features of ES6
[X] Template literal
[X] Multi-line string
[X] Rest and Spread operator
[X] Destructuring Assignment
[X] Class
[X] Modules
[X] Promise

### What are dynamic import
#### Dynamic import enables web developer use the import() function syntax to load modules on demand by using promises or async/await syntax.

### Adding the operator to some primitve data type
1. +null -> 0
2. +undefined -> NaN
3. +false -> 0
4. +NaN -> NaN
5. +"" -> 0


### Throttling and Debouncing
#### Throttling is used to limit the execution of code of an event handler function. While deboucing is also the limit of the execution of code until a specified no of time.