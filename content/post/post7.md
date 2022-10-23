---
title: Best Practice for Node.js Folder Structure
description: 'Project structuring is an important topic because the way you bootstrap your application can determine the whole development experience throughout the life of the project.'
category: Node, Folder-Structure
date: March 22 2021
img: https://dummyimage.com/200x200/ffffff/1421d9.png&text=200x200
---

# Best Practice for Node.js Folder Structure

## By [Yogesh Mishra](https://www.linkedin.com/in/yogimishra96/)

![best-practice-for-node-js-folder-structure](https://miro.medium.com/max/875/1*NBbGgfSrfimwxjuTuykCuw.jpeg)

Best Practice for Node.js Folder Structure

Project structuring is an important topic because the way you bootstrap your application can determine the whole development experience throughout the life of the project.

# Routes-

Where we define endpoints should be noun based and do not use verbs.

`router.get("api/v1/get-book-list", getBookMethod); // avoid` `router.get("api/v1/book-list", getBookMethod); // please use`

# Controller -

Basic skeleton of the API should be there if the method is getting big, use a service file and move some logic there. Write reusable code and common functions.

Ex. You can’t save a web socket circular object into an app instance of express.

# Organizing Files around Module

![](https://miro.medium.com/max/855/0*zDvJS4qcybkXLwnc.png)

![](https://miro.medium.com/max/843/0*S0hItPkGciwIW9_n.png)

## 👉 Place Your Test Files Next to The Module

Tests are not just for checking whether a module produces the expected output, they also document your modules. Because of this, it is easier to understand if test files are placed next to the implementation.

Put your additional test files in a separate **test** folder to avoid confusion.

![](https://miro.medium.com/max/875/0*_6e-qMJTx3heZDdD.png)

## 👉 Use a `config` Directory

To place your configuration files, use a **config** directory.

![](https://miro.medium.com/max/875/0*mfLuShflXVm362WT.png)

## 👉 All shell scripts in `scripts` folder

Avoid writing long scripts in package.json. Create a separate file for that and use that file.

![](https://miro.medium.com/max/875/0*c6y7pzD9vqNEnpMi.png)

## 👉 Third-party API calls and common reusable code in `services` folder

Third-party API integration in separate service files and maintain them in the `services` folder.

To sign and verify a token create a separate `jwt-service` and import this to sign and verify the token.

![](https://miro.medium.com/max/875/0*lXIZnam0E-30fK8p.png)

## 👉 Directory for common utils

Create a subfolder on the basis of type like `**server-utilities**`\-

![](https://miro.medium.com/max/875/0*jZ4euv2CIedQbOAI.png)

## 👉 DB directory for database-related stuff (MongoDB or Postgres)

Let’s assume we are dealing with **Postgres**, then-

![](https://miro.medium.com/max/875/0*vSsID7_iC3uokosR.png)

## 👉 Request validation : express-validator

Add an `express-validator` to validate and sanitize the request. Validation should be added on the model level and on the request level.

![](https://miro.medium.com/max/875/0*JjEijX7y25UB_u0s.png)

## 👉 Do not write every constant in the `.env` file

Only server-related essential credentials should be there for third parties etc.

Create a separate file and read from there like **environment.json** or put them in constants.js in utilities.

`"doc": "apidoc -i app/ -o client/dist/eps-client/doc",` and `npm run doc apidoc.json` will be in parallel of `package.json`

_Originally published at_ [_https://habilelabs.io_](http://habilelabs.io/best-practice-for-node-js-folder-structure/) _on September 23, 2022._

# Read More-

## Best Folder Structure for React Native Project

### By Muskan Jain

[learn.habilelabs.io](https://learn.habilelabs.io/best-folder-structure-for-react-native-project-a46405bdba7)

## Async Hooks in Node.js- Features & Use Cases

### An easiest way to track your async resources!

[learn.habilelabs.io](https://learn.habilelabs.io/async-hooks-in-node-js-features-use-cases-c8cd8372ba6b)

## Credit

![Habilelabs](https://miro.medium.com/fit/c/60/60/1*uq5xCKzivY-VHAY5erHUYg.jpeg)
