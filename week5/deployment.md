# Deployment - Heroku




1. What is Heroku? (Bader)


2. What are environment variables and why might we want to hide them? (Basheer)


**-- include a Demo using a website we built**


## Things to consider befor we start:
* installing Node.js and npm (Node Package Manager)
* Node.js app
* free [Heroku account](https://signup.heroku.com/dc)
* installing [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) (Command Line Client)
    * mac `$ brew tap heroku/brew && brew install heroku`
    * Ubuntu `$ sudo snap install --classic heroku`
    * Windows - download .exe file

## Declare app dependencies

After making a new file `mkdir first-heoku-app`. It's important to create `package.json` file that defines the dependencies in our application. By using the known command:
```
npm init
```
The generated `package.json` file looks like this:

```
{
  "name": "node-example",
  "version": "1.0.0",
  "description": "This example is so cool.",
  "main": "web.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "example",
    "heroku"
  ],
  "author": "jane-doe",
  "license": "MIT"
}
```
To install dependencies, use `npm install <pkg> --save`. This will install the package and also add it as a dependency in the `package.json` file. For example, to install express, you would type `npm install express --save`

To troubleshoot issues, type `rm -rf node_modules; npm install --production` and then to try to run your app locally by typing `heroku local web`. If a dependency is missing from your package.json file, you should see an error that says which module cannot be found.


## Specify the version of node

The version of Node.js that will be used to run your application on Heroku, should also be defined in your `package.json` file. You should always specify a Node.js version that matches the runtime you’re developing and testing with. To find your version type `node --version`.

Your package.json file will look something like this:
```
"engines": {
    "node": "10.x"
  },
```

Now that the dependencies are installed and the version of node to use has been specified, the `package.json` file will look something like this:
```
{
  "name": "node-example",
  "version": "1.0.0",
  "description": "This example is so cool.",
  "main": "web.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "example",
    "heroku"
  ],
  "author": "jane-doe",
  "license": "MIT",
  "dependencies": {
    "express": "^4.9.8"
  },
  "engines": {
    "node": "10.x"
  }
}
```

## Specifying a start script

To determine how to start your app, Heroku first looks for a Procfile. If no Procfile exists for a Node.js app, we will attempt to start a default web process via the start script in your package.json.

The command in a web process type must bind to the port number specified in the PORT environment variable. If it does not, the dyno will not start.


## Build your app and run it locally
Run the `npm install` command in your local app directory to install the dependencies that you declared in your `package.json` file.
```
$ npm install
```
Start your app locally using the heroku local command, which is installed as part of the Heroku CLI.
```
$ heroku local web
```
Your app should now be running on http://localhost:5000/.


## How to keep build artifacts out of git
Prevent build artifacts from going into revision control by creating a .gitignore file that looks something like this:
```
/node_modules
npm-debug.log
.DS_Store
/*.env

```

## Deploy your application to Heroku
After you commit your changes to git, you can deploy your app to Heroku.
```
git add .
$ git commit -m "Added a Procfile."
$ heroku login
Enter your Heroku credentials.
...
$ heroku create
Creating arcane-lowlands-8408... done, stack is cedar
http://arcane-lowlands-8408.herokuapp.com/ | git@heroku.com:arcane-lowlands-8408.git
Git remote heroku added
$ git push heroku master
...
-----> Node.js app detected
...
-----> Launching... done
       http://arcane-lowlands-8408.herokuapp.com deployed to Heroku

```
To open the app in your browser, type `heroku open`.


## Advanced HTTP features

The HTTP stack available to Common Runtime apps on the herokuapp.com subdomain supports HTTP 1.1, long polling, chunked responses and WebSockets.


## Provision a database

The add-on marketplace has a large number of data stores, such as Postgres, Redis, MongoDB and MySQL.


3. How can we automatically deploy merges to our Master branch? (HadiKa)
![](https://i.imgur.com/S6fyeuo.png)

![](https://i.imgur.com/THLJh4V.jpg)
![](https://i.imgur.com/PmRb0UM.jpg)
![](https://i.imgur.com/R5xkG2p.png)
![](https://i.imgur.com/KSYijzk.png)
![](https://i.imgur.com/fq9B0Fb.jpg)
![](https://i.imgur.com/rlAN6AC.png)
