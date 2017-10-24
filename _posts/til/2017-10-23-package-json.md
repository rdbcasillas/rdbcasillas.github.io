---

layout: post
title: "TI(re)L about package.json"
categories: til

---

Today I re-learned about *package.json* after having used it back in 2013 and then completely forgetting about it. One of the main ingredients of any npm (acronym for Node Package Manager, [but not really](https://www.npmjs.com/)) project/package is the *package.json* file. This file stores a json object that is *supposed to contain* relevant information about an npm project (Note: I use package and project interchangeably in this article). Npm is the [largest package registry](http://www.modulecounts.com/) by a massive margin (over 534k at the moment). They all come with their own package.json file. But if you are creating a node project of your own, you can either use app generators that can create package.json for you or you can create it from scratch. 

Go inside the project where you want to create your node app and type this:

```shell
npm init
```

This will be followed by a set of questions, answers to which will go into making a package.json for you. Following is a snippet of what happens when you type that command:

```shell
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
# Enter package name without capital letters
package name: (node_practice) testProject
Sorry, name can no longer contain capital letters.
package name: (node_practice) test-project 
# Random version. you would want to put 0.0.1 unless updating an old project
version: (1.0.0) 2.3.1
description: Playing with package.json
entry point: (index.js) app.js  # This is the file that will be called first when people "require" your project in their project
test command: ls -ltr # this is the command that will run when you do npm test (for running some tests)
git repository: # left empty for now
keywords: ["test", "package.json"] # keywords that help people to quickly identify the purpose of your project
author: vats
license: (ISC) MIT
About to write to /Users/rdbcasillas/programming/node_practice/package.json:

{
  "name": "test-project",
  "version": "2.3.1",
  "description": "Playing with package.json",
  "main": "app.js",
  "scripts": {
    "test": "ls -ltr",
    "start": "node server.js" # this was chosen as default because it already existed in my test-project folder. There won't be a "start" script otherwise. 
  },
  "keywords": [
    "[\"test\"",
    "\"package.json\"]"
  ],
  "author": "vats",
  "license": "MIT"
}
```

Once you have a boiler plate *package.json* ready, you would want to add dependencies for your package. Let's say you want to install Express.js framework to reduce the cognitive load and lines of code that comes with writing pure Node.js. In order to install that for your test-project, simply do this: 

```shell
npm install express --save
```

This will add a "dependencies" object in your package.json object with "express" key and it's version as the corresponding value. Like this:

```shell
"license": "MIT",
  "dependencies": {
    "express": "^4.16.2"
  }
```

A new folder *node_modules* will also be created which is where all the dependencies (including Express) will live. You can find out Express's dependencies by checking it's package.json file @ *path/to /yourproject/node_modules/express/package.json*. All of these dependencies were installed during Express's installation and that's why you see them all in *node_modules* folder. 

Using *npm install express - - save* is the preferred method to install a dependency (compared to simply running *npm install* <dependency name>) because it modifies the *package.json* directly with all the dependencies that you are interested in, which you can then share with your colleagues so that they can simply do *npm install* and have the same version of dependencies that your project depends on. Usually, it's [not a good idea](https://www.joezimjs.com/javascript/no-more-global-npm-packages/) to do *npm install -g <dependency name>* so avoid that as much as possible.

To learn more about different fields available for *package.json*, run this command in your shell:

```shell
npm help json
```