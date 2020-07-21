# Types of tests

### What are all the different ways to make sure our code is correct?


---




# What is Prettier? How might it help us write better code?

#### What is Prettier?

![](https://i.imgur.com/PyiwA5q.png)



Prettier is an opinionated code formatter that Supports many languages,It removes all original styling and ensures that all outpute code conforms to a consistent style.

let's take an exmple:
```javascript
const name = "James";

const person ={first: name
}

console.log(person);

const sayHelloLinting = (fName) => {
console.log(`Hello linting, ${fName}`)
}

sayHelloLinting('James');

```

in this code you may notice some missteps:

1.A mix of single and double-quotes.
2.The first property of the person object should be on its own line.
3.The console statement inside of the function should be indented.
4.You may or may not like the optional parenthesis surrounding the parameter of the arrow function.



### Installation

Search for Prettier - Code Formatter in the extension panel of VS Code 

![](https://i.imgur.com/YY6e5JK.png)


### Usage

Using Command Palette (CMD/CTRL + Shift + P)
1. CMD + Shift + P -> Format Document

OR

1. Select the text you want to Prettify
2. CMD + Shift + P -> Format Selection





when we use prettier the code will formatted :

```javascript=

const name = 'James';

const person = { first: name };

console.log(person);

const sayHelloLinting = (fname) => {
  console.log(`Hello linting, ${fName}`);
}

sayHelloLinting('James');

```




-----------------------


# What is static analysis? How can a linter help us avoid bugs?

static analysis is the art of trying to spot problems in your source code before it’s run. These can be small things, such as stylistic preferences or finding unused variables, or complex analyses such as detecting overly complex functions.

### how static analysis work?

![](https://i.imgur.com/QTWr9lb.png)


### Formatters and linters
Most common forms of static analysis are formatters and linters.
The most popular JavaScript formatter is Prettier as described above.
And, JavaScript’s most popular **linter** by far is **ESLint.** 

![](https://i.imgur.com/iagcmmX.png)


While formatters only work on formatting issues, linters can work on those as well as more complex issues. **Linters scan source code with a set of “rules”, or descriptions of behaviors to watch out for, and let you know of any violations they find.**

### Each ESLint rule contains roughly two objects:
* A meta object containing documentation on the rule’s name, behavior, settings, and other metadata.
* A create method that returns an object with methods ESLint will call when visiting nodes.

![](https://i.imgur.com/mTp8qLu.png)

For more on ESLint rules, see [ESLint’s rules guide.](https://eslint.org/docs/developer-guide/working-with-rules)

-----------------------

