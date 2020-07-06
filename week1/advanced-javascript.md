





# In depth JAVASCRIPT (kinda..)

###### tags: `javascript` `advanced js` `research ما تكلمني`

> Please dont be afraid to ask anyquestion, answering them is our playtstation  :video_game: 

---


## :memo: abeer's section: 


#  value vs reference

- A variable may store two types of values: value(primitive) and reference. 
 
 ![](https://i.imgur.com/xEE6yni.png)


- Value are copied by thier value
- Object are copied by the reference 


---

***let's take example of value types:***
```javascript=
//javaScript 
// the value is stored inside of this variable
let x=10;
//copy the value of x 
let y=x; 

x=20;


console.log(x)   // x=20
console.log(y)   // y=10
```


---

***Another example of reference type:***
```javascript=

 //the object is not stored in the variable,is stored in the memory
let X = { value: 10 };

//when we copy x to y is the address or the reference that this copy
let Y = X; 

X.value = 20;  

console.log(X);
console.log(Y);
/*
 * this gives us the following output:

 * X.value = 20   
 * Y.value = 20


 * y changed too, this is because 
 * both X and Y share the same reference!
 */
```


---

<br>

---


# Double equals ( == ) vs Triple equals ( === )

###  Double equals (==) 
 is a comparison operator, which  comparing two variables, but it ignores the datatype of variable



---


###  Triple equals (===)
  is a comparison operator used for comparing two variables, but this operator also checks datatype and compares two values.

let's take an example:
```javascript=

/
let x=10;
let y='10';

x == y // true
      
// it's will return true(equal) because the two operands are equal although the  data types are different

```

---


 
Another example:

```javascript=

/
let x=10;
let y='10';

 x === y // false

      
// it's will return false(not equal) although they have the same value but data types are different 


```


---




---

## :memo: khaled's section:
<hr>

**What is Scope?
**

Scope in JavaScript refers to the accessibility or visibility of variables. That is, which parts of a program have access to the variable or where the variable is visible.



---

## **Why is Scope Important?**

1. The main benefit of scope is security. That is, the variables can be accessed from only a certain area of the program. Using scope, we can avoid unintended modifications to the variables from other parts of the program.
2. The scope also reduces the namespace collisions. That is, we can use the same variable names in different scopes.

## **Types of Scope**

There are three types of scope in JavaScript — 1) Global Scope, 2) Function Scope, and, 3) Block Scope.


---


1. Global Scope

Any variable that’s not inside any function or block (a pair of curly braces), is inside the global scope. The variables in global scope can be accessed from anywhere in the program. For example:

```javascript=

var greeting = 'Hello World!';
function greet() {
  console.log(greeting);
}
// Prints 'Hello World!'
greet();
```


---




2. Local Scope or Function Scope

Variables declared inside a function is inside the local scope. They can only be accessed from within that function, that means they can’t be accessed from the outside code. For example:


---

```javascript=

function greet() {
  var greeting = 'Hello World!';
  console.log(greeting);
}
// Prints 'Hello World!'
greet();
// Uncaught ReferenceError: greeting is not defined
console.log(greeting);
```


---

3. Block Scope

ES6 introduced let and const variables, unlike var variables, they can be scoped to the nearest pair of curly braces. That means, they can’t be accessed from outside that pair of curly braces. For example:


---

```javascript=

{
  let greeting = 'Hello World!';
  var lang = 'English';
  console.log(greeting); // Prints 'Hello World!'
}
// Prints 'English'
console.log(lang);
// Uncaught ReferenceError: greeting is not defined
console.log(greeting);
```


---

We can see that var variables can be used outside the block, that is, var variables are not block scoped.


---



## **Nested Scope**


Just like functions in JavaScript, a scope can be nested inside another scope. For example:


---

```javascript=

var name = 'Peter';
function greet() {
  var greeting = 'Hello';
  {
    let lang = 'English';
    console.log(`${lang}: ${greeting} ${name}`);
  }
}
greet();

```


---


Here we have 3 scopes nested within each other. First, the block scope (created due to the let variable) is nested inside the local or function scope which is in turn nested inside the global scope.

---


**Conclusion**

So in a nutshell, a scope is an area where a variable is visible and accessible. Just like functions, scopes in JavaScript can be nested and the JavaScript engine traverses the scope chain to find the variables used in the program.

Scope is fundamental concept of JavaScript that every JavaScript developer should understand. Having a good knowledge of this concept will help you to become a much more effective and better JavaScript developer.


That’s it and i hope you found this article helpful.

---

---

### Bader's section : :rocket:

# JS Closures
- [ ] What are closures? 
> GREAT QUESTION! here's a thorough explination:

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state. 
In other words, **a closure gives you access to an outer function’s scope from an inner function**. ==In JavaScript, closures are created every time a function is created, at function creation time.==

- Code block with color and line numbers：
```javascript=15
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() { // displayName() is the inner function, a closure
    alert(name); // use variable declared in the parent function
  }
  displayName();
}
init();
```
:::info
:pushpin: Want to learn more? ➜ [A simple guide to help you understand closures in JavaScript](https://medium.com/@prashantramnyc/javascript-closures-simplified-d0d23fa06ba4)
:::

> **Shocked huh?**
![reference link](https://media.giphy.com/media/iHe7mA9M9SsyQ/giphy.gif)


let take a look at another example:

**JavaScript Closures**
Remember self-invoking functions? What does this function do?
```javascript
var add = (function () {
  var counter = 0;
    /*  ↙️ this return here closed the parent function!*/
    return function () {/* ◀️ this is an anonymous function! as it has no name!*/
        counter += 1; 
        return counter
        }
    }
)();

add();
add();
add();

// the counter is now 3 <===
```
let explain our code! 
The variable ==**add**== is assigned the ***return*** value of a self-invoking function.

The self-invoking function only runs once. It sets the counter to zero (0), and returns a function expression.

This way add becomes a function. The *"wonderful"* part is that it can access the counter in the parent scope.

This is called a **JavaScript closure**. It makes it possible for a function to have =="private"== variables *(a variable that is not accessible from other parts of the code)*

The counter is **"protected"** by the scope of the anonymous function, and can only be changed using the add function.

:::info
🧠 Gist: A closure is a function having access to the parent scope, even after the parent function has closed.
::: 

let dive deep into the thought bubble! :thought_balloon: 
:::info
Variable `counter` is created, and its value is set to 0.
JavaScript now tries to execute ==`counter` + 1==. 
Here is where things get interesting. 
JavaScript knows that ==`counter`== no longer exists. 
Since ==`counter` is part of the outer function ***add***==, 
so `counter` would only exist while the ***add*** function is in **execution**. 
Since the ***add*** function finished execution and returned a New anonymous functions 
any variables within the scope of the outer function (outer layer of the add function) cease to exist, and hence variable `counter` should no longer exist
How does JavaScript handle this?
:::

> **ANSWER!?**
with JAVASCRIPT CLOSURE! [color=#3b75c6]

>The inner function can access the variables of the enclosing function due to **closures in JavaScript.** ==In other words, the inner function **preserves** the scope chain of the enclosing function at the time the enclosing function was executed, and thus can access the enclosing function’s variables.== [color=#3b75c6]

![](https://media.giphy.com/media/xT0xeJpnrWC4XWblEk/giphy.gif =350x250)![](https://media.giphy.com/media/kVA5mbyY6Z6AU/giphy.gif =250x250)![](https://media.giphy.com/media/l0IypeKl9NJhPFMrK/giphy.gif =350x250)![](https://media.giphy.com/media/KI9oNS4JBemyI/giphy.gif =250x250)


- [ ] **How does closures affect the scope?**

> A closure is a feature in JavaScript where an inner function
has access to the outer (enclosing) function’s variables — a scope chain.
    in simpler terms:
    - The closure has three scope chains:[color=#3b75c6]

> -it has access to its own scope (variables defined between its curly brackets)
         -it has access to the outer function’s variables
         -it has access to the global variables [color=#3b75c6]
         
Functions do not have access to each other’s scopes usually, however if you think about it
JavaScript closures "Breaks" this rule, it allows the inner fucntion to access the outer function's variables, even after they ceased to exist!
==this, in a sense can be used to create private variables==
However this doesnt work the otherway around, the outer function can't see the inner function's variables

![](https://i0.wp.com/css-tricks.com/wp-content/uploads/2017/08/one-way-glass.png?ssl=1)


---


# Clean code concept

 ## Introduction

![Humorous image of software quality estimation as a count of how many expletives
you shout when reading code](https://www.osnews.com/images/comics/wtfm.jpg)
 
This is not a style guide. It's a guide to producing
[readable, reusable, and refactorable](https://github.com/ryanmcdermott/3rs-of-software-architecture) software in JavaScript.

Not every principle herein has to be strictly followed, and even fewer will be
universally agreed upon. These are guidelines and nothing more, but generally are good practice to follow on
 
### **Variables**

#### Use meaningful and pronounceable variable names

**Bad:**

```javascript
const yyyymmdstr = moment().format("YYYY/MM/DD");
```

**Good:**

```javascript
const currentDate = moment().format("YYYY/MM/DD");
```
<hr>

#### Use the same vocabulary for the same type of variable

**Bad:**

```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```

**Good:**

```javascript
getUser();
```
<hr>


#### Use searchable names

We will read more code than we will ever write. It's important that the code we
do write is readable and searchable. By _not_ naming variables that end up
being meaningful for understanding our program, we hurt our readers.
Make your names searchable. Tools like
[buddy.js](https://github.com/danielstjules/buddy.js) and
[ESLint](https://github.com/eslint/eslint/blob/660e0918933e6e7fede26bc675a0763a6b357c94/docs/rules/no-magic-numbers.md)
can help identify unnamed constants.

**Bad:**

```javascript
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```

**Good:**

```javascript
// Declare them as capitalized named constants.
const MILLISECONDS_IN_A_DAY = 86_400_000;

setTimeout(blastOff, MILLISECONDS_IN_A_DAY);
```
<hr>

 
#### Avoid Mental Mapping

Explicit is better than implicit.

**Bad:**

```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(l => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  // Wait, what is `l` for again?
  dispatch(l);
});
```

**Good:**

```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(location => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  dispatch(location);
});
```
<hr>


#### Don't add unneeded context

If your class/object name tells you something, don't repeat that in your
variable name.

**Bad:**

```javascript
const Car = {
  carMake: "Honda",
  carModel: "Accord",
  carColor: "Blue"
};

function paintCar(car) {
  car.carColor = "Red";
}
```

**Good:**

```javascript
const Car = {
  make: "Honda",
  model: "Accord",
  color: "Blue"
};

function paintCar(car) {
  car.color = "Red";
}
```


## **Functions**

### Function arguments (2 or fewer ideally)

Limiting the amount of function parameters is incredibly important because it
makes testing your function easier. Having more than three leads to a
combinatorial explosion where you have to test tons of different cases 

One or two arguments is the ideal case, and three should be avoided if possible.
Anything more than that should be consolidated. Usually, if you have
more than two arguments then your function is trying to do too much. In cases
where it's not, most of the time a higher-level object will suffice as an
argument.

Since JavaScript allows you to make objects on the fly, you can use an object if you are finding yourself needing a
lot of arguments.


**Bad:**

```javascript
function createMenu(title, body, buttonText, cancellable) {
  // ...
}

createMenu("Foo", "Bar", "Baz", true);

```

**Good:**

```javascript
function createMenu({ title, body, buttonText, cancellable }) {
  // ...
}

createMenu({
  title: "Foo",
  body: "Bar",
  buttonText: "Baz",
  cancellable: true
});
```
<hr>

### Functions should do one thing

This is by far the most important rule in software engineering. **When functions
do more than one thing, they are harder to compose, test, and reason about.**
When you can isolate a function to just one action, it can be refactored
easily and your code will read much cleaner. ==**If you take nothing else away from
this guide other than this, you'll be ahead of many developers.**==

**Bad:**

```javascript
function emailClients(clients) {
  clients.forEach(client => {
    const clientRecord = database.lookup(client);
    if (clientRecord.isActive()) {
      email(client);
    }
  });
}
```

**Good:**

```javascript
function emailActiveClients(clients) {
  clients.filter(isActiveClient).forEach(email);
}

function isActiveClient(client) {
  const clientRecord = database.lookup(client);
  return clientRecord.isActive();
}
```
<hr>


#### Function names should say what they do

**Bad:**

```javascript
function addToDate(date, month) {
  // ...
}

const date = new Date();

// It's hard to tell from the function name what is added
addToDate(date, 1);
```

**Good:**

```javascript
function addMonthToDate(month, date) {
  // ...
}

const date = new Date();
addMonthToDate(1, date);
```
 <hr>
 
 ### Remove duplicate code
 
Do your absolute best to avoid duplicate code. Duplicate code is bad because it
means that there's more than one place to alter something if you need to change
some logic.
 
:::info
:pushpin: this will be too long if want to try listing all the principles, please do take the time checking the full list here: 
[clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript/edit/master/README.md)
:::

---
