# Modules

### How can we use modules in our Node apps?
#### A background on modules

JavaScript programs started off pretty small — most of its usage in the early days was to do isolated scripting tasks, providing a bit of interactivity to your web pages where needed, so large scripts were generally not needed. Fast forward a few years and we now have complete applications being run in browsers with a lot of JavaScript, as well as JavaScript being used in other contexts (Node.js, for example).

It has therefore made sense in recent years to start thinking about providing mechanisms for splitting JavaScript programs up into separate modules that can be imported when needed. Node.js has had this ability for a long time, and there are a number of JavaScript libraries and frameworks that enable module usage (for example, other CommonJS and AMD-based module systems like RequireJS, and more recently Webpack and Babel).

The good news is that modern browsers have started to support module functionality natively, and this is what this article is all about. This can only be a good thing — browsers can optimize loading of modules, making it more efficient than having to use a library and do all of that extra client-side processing and extra round trips.


**In the Node.js module system**, each file is treated as a separate module. So, if you are creating, let’s say, a demo.js file, this implies you are creating a module in Node. Basically modules help us encapsulating our code into manageable chunks.
Anything that we define in our module (i.e. in our JavaScript file) remains limited to that module only, unless we want to expose it to other parts of our code.
So, anything we define inside our module remains private to that module only.
 ## How To Create a Module
 
 Creating a module in Node is very simple, just create a file and you are good to go.
 
```
const sum = (a, b) => {
  return a + b;
};

const result = sum(2, 3)
console.log(result)
```
 That’s it, now you have a module in Node, nothing fancy, just simple creation of a file.
 
 ## Types of Module
- Core module: Modules that come shipped with Node.js, e.g. https, os, fs, net, etc.
- Third-party module: Modules that you install from any package manager. We use these modules to accomplish or simplify any existing task. For example, to simplify our web API development we use express, or to deal with date and time we use moment.

- Local module: These are the modules that we create for our own use. These modules basically consist of core business logic of our code.

For example, consider a file named foo.js:
```
const circle = require('./circle.js');
console.log(`The area of a circle of radius 4 is ${circle.area(4)}`);
```
On the first line, foo.js loads the module circle.js that is in the same directory as foo.js.

Here are the contents of circle.js:
```
const { PI } = Math;

exports.area = (r) => PI * r ** 2;

exports.circumference = (r) => 2 * PI * r;
```
The module circle.js has exported the functions area() and circumference(). Functions and objects are added to the root of a module by specifying additional properties on the special exports object.
Variables local to the module will be private. In this example, the variable PI is private to circle.js. 

npm install <package-name> is how you install third party npm 'modules' (pieces of code from the npm repository). for exmaple: In the workshop we've done(npm-intro) `npm install tape` installed the Tape testing library we used later on on that workshop.

npm will create a node_modules folder at the root of your project. This is where any third party modules you install are stored. Don't worry if you see way more files than you expect — npm also puts all the dependencies of the modules you install in here (and their dependencies, and their dependencies and ...)

You may see npm install -g <package-name>. The -g flag installs the module globally to your machine, rather than into the node_modules folder of that specific project. This can be useful for certain kinds of modules (e.g. command-line utilities that you might want to use anywhere).
Examples about using modules:
https://github.com/mdn/js-examples/tree/master/modules

### .mjs versus .js
* It is good for clarity, i.e. it makes it clear which files are modules, and which are regular JavaScript.
* It ensures that your module files are parsed as a module by runtimes such as Node.js, and build tools such as Babel.

### Exporting module features
The first thing you do to get access to module features is export them. This is done using the export statement.
### Importing features into your script
You use the `import` statement, followed by a comma-separated list of the features you want to import wrapped in curly braces, followed by the keyword from, followed by the path to the module file

## Differences between modules and standard scripts
You need to pay attention to local testing — if you try to load the HTML file locally (i.e. with a file:// URL), you'll run into CORS errors due to JavaScript module security requirements. You need to do your testing through a server.
Also, note that you might get different behavior from sections of script defined inside modules as opposed to in standard scripts. This is because modules use strict mode automatically.
There is no need to use the defer attribute (see <script> attributes) when loading a module script; modules are deferred automatically.
Modules are only executed once, even if they have been referenced in multiple <script> tags.
Last but not least, let's make this clear — module features are imported into the scope of a single script — they aren't available in the global scope. Therefore, you will only be able to access imported features in the script they are imported into, and you won't be able to access them from the JavaScript console, for example. You'll still get syntax errors shown in the DevTools, but you'll not be able to use some of the debugging techniques you might have expected to use.

---
#### What's the difference between our own, built-in, and 3rd party modules?
## Types of Module
- Third-party module: Modules that you install from any package manager. We use these modules to accomplish or simplify any existing task. For example, to simplify our web API development we use express, or to deal with date and time we use moment.

- Local module: These are the modules that we create for our own use. These modules basically consist of core business logic of our code.




-----------------------
#### What is the package.json file for?


package.json file is a file that contains metadata relevant to the project. This file gives information to npm that allows it to identify the project as well as handle the project's dependencies.

Briefly, every thing about your project is defined inside package.json file.

 ##### What does package.json file consist of?
The metadata information in package.json file can be categorized int two categories:
1. Identifying metadata properties: It  consist of the properties to identify the module such as the name of the project, current version of the module, license, author of the project, description about the project etc.
2. Functional metadata properties:  it consists of the functional values of the module such as the starting point of the module, dependencies in project, scripts being used  etc.


#### example of package.json file : 

![](https://i.imgur.com/TYTjOTt.png)

- The name filed is a name  of the module.
![](https://i.imgur.com/QShbjnQ.png)


- The verion filed  indicates the current version of the package. The version should follow semantic versioning rules,which means the version is always expressed with 3 numbers: x.x.x.

![](https://i.imgur.com/8YmEl8w.png)


- The description and keyword allows people to understand what your project is in a few words
![](https://i.imgur.com/zNXyjHq.png)
![](https://i.imgur.com/Z3x8cPh.png)



- Authors and contributors  fields can all be used to credit the people who contributed to the project, show how to contact the author/maintainer, and give links for additional references.
![](https://i.imgur.com/qSaVXQu.png)
![](https://i.imgur.com/0UpZ5vm.png)






-  The scripts field defines a set of node scripts you can run
![](https://i.imgur.com/feVfZew.png)


- The dependencies field is used to list all the dependencies of your project that are available on npm.
![](https://i.imgur.com/qYFZFEq.png)




-----------------------
### What is npm? Why are npm scripts useful? What does npx do?

#### What is npm? (Node Package Manager)
npm is the standard package manager for Node.js.
Most commonly, it is used to publish, discover, install, and develop node programs.
npm manages downloads of dependencies of your project.

Installing all dependencies
![](https://i.imgur.com/j9VSpZ7.png)

Installing a single package
![](https://i.imgur.com/Jf3vgmp.png)

Updating packages
![](https://i.imgur.com/kaG6AZc.png)

Updating single package
![](https://i.imgur.com/4dO1I9S.png)

![](https://i.imgur.com/CctM94r.png)



#### Why are npm scripts useful?

![](https://i.imgur.com/YGv1eQR.gif)


Package.json has various sections, scripts is one of them, which allows you to write npm script which we can run using npm run <script-name>. Run npm run to see available scripts. Binaries of locally install packages are made available in the PATH , so you can run them by name instead of pointing to node_modules/

A Few Use Cases for NPM Scripts:
* Minification/Uglification of CSS/JavaScript
* Automating the build process
* Linting your code
* Compressing images
* Automatically injecting changes with BrowserSync



#### What does npx do?
![](https://i.imgur.com/31E5q9u.gif)


NPX: The npx stands for Node Package Execute and it comes with the npm.
NPX is an NPM package runner that makes it really easy to install any sort of node executable that would have normally been installed using NPM.

There are a number of ways to install node packages, you can have them sitting locally (local to the project) or install globally (in the user environment).

Sometimes, instead of using either of the two install methods above, you may just want to use the package and go.

Sometimes, you might just want to experiment with a list of packages as you may not know exactly what you need.

In these cases, ​instead of installing locally or globally, you can go straight to running those packages with NPX.

To use NPX, you would run a command like this:
![](https://i.imgur.com/kXUTXzy.png)

One great way for you to see how quickly NPX works is to create a react app using:
![](https://i.imgur.com/XhrbC18.png)

