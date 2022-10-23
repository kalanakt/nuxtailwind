---
title: Express.js vs Nest.js
description: 'Since Node.js was announced, the use of Javascript has increased in the backend world. Due to the increasing use of Node.js new frameworks and tools are getting announced every day. Express and Nest are among the most known frameworks for creating back-end applications with Node.js and in this article, we will compare them.'
category: JavaScript, Frameworks, Express.js, Nest.js
date: Jun 17 2022
img: https://dummyimage.com/200x200/ffffff/1421d9.png&text=200x200
---

# Express.js vs Nest.js (All you need to know)

![](https://miro.medium.com/max/875/1*aGCx1q4rO5Uny9AauDCqyw.png)

Since Node.js was announced, the use of Javascript has increased in the backend world. Due to the increasing use of Node.js new frameworks and tools are getting announced every day. Express and Nest are among the most known frameworks for creating back-end applications with Node.js and in this article, we will compare them.

## **Express**

Express is a minimalistic framework of Node.js. Although it covers a few core aspects of creating a server side application, it is trendy because of its simplicity, flexibility and performance and even Nest is built in top of express. But still, some problems come with express and before we dive into them, let’s understand how these frameworks make life easier. Firstly, we need to understand what they provide us, let’s create a web server without using any framework but Node.js only.

Node.js Server

As you can see, we can create a web server using the built-in HTTP module in Node.js. If you send a web request to [http://localhost:8000](http://localhost:8000), you will receive a message (Hello World) from our Node.js server. It is simple and easy, but what if we want to create a REST API with hundreds of different routes? Then we had to write a route matcher and send each route to its specific controller. Also, we have to implement HTTP methods like GET, POST, PUT etc. to satisfy REST standards, right? What express does is precisely this, express handles request/response control, routing, serving static files, and middlewares for us. That is the beauty of Express being so lightweight and simple. Now let’s see how we can create the previous application using express.

Express.js Server

The above code is also doing the same thing. But express gives us a routing mechanism that matces the requested URL, so if we want to create a cat service using express router it will look like this.

That is great, but what is the problem with express? The short answer is architecture. Express is very minimalistic and straightforward, which provides flexibility to the users. The flexibility is very beneficial for experienced users or complex scenarios, but the flexibility can cause an increase in errors and structural mistakes. In addition, applications nowadays require lots of extra logic like request validation, authorization, documentation, testing, logging etc. So thinking the express only gives us a few features, people need to solve these requirements using other libraries or frameworks. That is why Nest.js exist.

## Nest.js

Nest is a framework for building efficient, scalable Node.js server-side applications. Nest is built in top of common Node.js frameworks (Express, Fastify). It uses progressive JavaScript, is built with and fully supports TypeScript (yet still enables developers to code in pure JavaScript) and combines elements of OOP (Object Oriented Programming), FP (Functional Programming), and FRP (Functional Reactive Programming). Nest also implements SOLID principles. This is great because many backend developers are switching from typed languages to NodeJs, and it will be easy for them to get used to Nest.

Nest provides abstraction above these common Node.js frameworks (Express/Fastify) and exposes their APIs directly to the developer. This gives developers the freedom to use the myriad of third-party modules available for the underlying platform. The purpose Nest serves is to create highly testable, scalable, loosely coupled, and easily maintainable applications.

To demonstrate that, let’s create our cats service using Nest

Nest’s routing approach works with controllers, which organizes the routes and makes routing clearer and more manageable. Nest has a default error handler and other built-in utilities, which helps you for a quick start. Of course, you can implement them manually with express, but there is no need to reinvent the wheels. All these amenities make Nest a better choice for beginners because these core utilities can be hard to understand for beginners.

Now that we understand the basics of these frameworks, let’s dive into the details of what Nest provides.

# 1\. Architecture

In express, there is no architecture standard. And it becomes a problem in many large projects or microservice applications because they require a powerful and flexible architecture to keep the application maintainable. On the other hand, Nest’s most powerfull side is architecture because Nest has many utilities to provide a flexible, clean and powerful architecture. Nest-Modules are a great example for this. A Nest-Module is used to organize the application structure and helps developers to manage dependencies of the module. Also Nest is great for applying N-tier architecture which aims to divide an application into logical layers. Layers are a way to separate responsibilities and manage dependencies to fulfill the separation of concerns (SoC) principle. To accomplish that, Nest advises calling the service layer inside the controllers and do all the bussiness logic inside these service layers. For the service layer, call another layer called the repository layer, which is responsible for data access. So we separated our concerns into three layers. Separating these layers provides reusability and maintainability for the software. Also it makes our application easy to test which will be explained later in **dependency injection** topic. Think about the cat service we created, it may look like this:

CatController -> CatService -> CatRepository

![App Structure](https://miro.medium.com/max/391/1*VeijJB-b_Kgz-l0X4nvPRg.png)

Application Structure

So whenever we need to call a method of the CatService in any Controller, we simply create an instance of the CatService and call the method or we can use an existing instance of CatService by passing a CatService instance as a parameter of the CatController’s contructor which is also a concept of Nest called Dependency Injection.

# 2\. Dependency Injection

> Developers coming from different programming languages may be familiar to this term. Dependency injection is another beneficial part of Nest. Dependency injection is **a design pattern in which an object receives other objects that it depends on**. A form of inversion of control, dependency injection aims to separate the concerns of constructing objects and using them, leading to loosely coupled programs.

In Nest dependency injection can be used by adding the Injectable decorator top of the module you want to inject. For instance

cat.service.ts

cat.controller.ts

As you can see, we passed the catService instance as a parameter to the CatController’s constructor. This approach makes the application more maintainable and easy to test especially for large applications. This is one of the best advantages of using Nest.

# 3\. Middlewares

Nest middleware are, by default, equivalent to express middleware. In express middleware, you just create another route handler which runs before/after the controller. Nest has a **MiddlewareConsumer** class which is a helper class. It provides several built-in methods to manage middleware. All of them can be simply chained in the fluent style. MiddlewareConsumer has a **forRoutes** property where you can simply type the path as a string or controllers to register the middleware. Nest also has a exclude property which helps you to exclude paths or controllers.

Nest also provides middleware-like utilities such as **pipes, filters, and interceptors**. They can be considered middleware, but they are more focused on different purposes; for example, pipes are mainly used for validations and data transformations. On the other hand, Middlewares are handlers that run before the route handler and have access to request objects. Filters are the opposite of middleware. They run after the route handler and manipulate the response object for error handling etc. Finally, interceptors have access to both request and response objects before and after the route handler is called. Nest also provides a utility called ExecutionContext, which provides additional details about the current execution process like what is going to be executed next, and express middlewares being lack this information. As a result, Nest is one step ahead of the express here.

# 4\. Custom Exceptions

Nest has default exception classes for most scenarios like NotFoundException, UnAuthorizedException etc. This saves you some time. Also, it is possible to create your own exception classes just like in express.

# 5\. Validations

Request validation is beneficial in many ways. It prevents errors before happening and shows the user a meaningful message that they send a wrong input. Also, it prevents users from sending unwanted inputs, which makes the application more secure.

In express I used to add a middleware before the handler and this middleware takes a validator as a parameter which is created with Joi order order validation tools. But it is very time-consuming and causes your route/handler declarations to look longer, more complicated and you have a chance to forget to add the validator before the handler. It’s not possible to create generic middleware which can be used across all contexts across the whole application. This is because middleware is unaware of the execution context, including the handler that will be called and any of its parameters.

In Nest you can create a **validation pipe** and use it as a decorator before the method. For instance

@Post()  
@UsePipes(new JoiValidationPipe(createCatSchema))  
async create(@Body() createCatDto: CreateCatDto) {  
 this.catsService.create(createCatDto);  
}

But there is a more elegant way of doing this. If you are using Nest with **Typescript**, you can make your validations in the Dto with class-validator library.

import { IsString, IsInt } from 'class-validator';

export class CreateCatDto {  
 @IsString()  
 name: string;  
 @IsInt()  
 age: number;

@IsString()  
 breed: string;  
}

In conclusion, express requires a few more touches than Nest. Nest’s way of handling validations with Typescript is the most recommendable one.

# 6\. Authorization

Authorization is a common need in back-end applications. Some services may require role based authorizations to prevent unallowed actions. Authorization has typically been handled by a middleware in traditional Express applications and usually it looks something like this.

router.get('/create', authorize(Role.Admin), create);

Nest’s way of authorization is similar but Nest provides a few conveniences with its **Guards** concept. Guard determine whether a given request will be handled by the route handler or not. Guards can be controller-scoped, method-scoped or global-scoped which provides ease of use in implementation also helps keep your code DRY and declarative. Also the **execution-context** can be used to build generic [guards](https://docs.nestjs.com/guards) which makes guards more powerful than traditional middlewares.

@Post()  
@Roles('admin')  
async create(@Body() createCatDto: CreateCatDto) {  
 this.catsService.create(createCatDto);  
}

# 7\. Database

In express we usually use ORM (Object Relational Mapper) or ODM (Object Document Mapper) like [**Sequelize**](https://sequelize.org/) or **M**[**ongoose**](https://mongoosejs.com/) to handle database operations. Nest is not different but Nest has built-in ORM-ODM tools which provide model/repository injection, testability, and dynamic configuration to make accessing your chosen database, my opinion is, Nest’s architecture makes working with databases easier

# 8\. API Documentation

Documenting an API in Nest.js is the easiest by far. Nest provides a swagger module that automatically creates documentation for API endpoints. Also, it is possible to define request/response schemas with decorators like below.

# 9\. Performance

Nest allows to use Fastify adapter which is two times faster than Express adapter and Nest won’t be able to beat Express if not using Fastify adapter. And we know that Nest provides an abstraction of these two adapters to switch between them but this won’t be possible in every scenario because there are some cases these two adapters act differently by their nature. For instance, fastify adapter does not support nested routes, so the Express adapter should be used to accomplish that.

# 10\. Testing

Nest’s most powerful advantage of Architecture wins here too. As we discussed before Nest uses modules and couples them with dependency injection which allows injecting any dependency to any module, so you can inject a test service without instantiating it, and it saves lots of time and effort especially for larger modules and services.

# 11\. Learning Curve

Since Nest is built in top of express, Nest acts as a superset of express. So Nest is more complicated and has more features to learn. If the question here is comparing only express vs. Nest, then express will be easy to understand with no doubt, but express itself is not enough for creating a complete web server in most modern applications. Hence, developers most probably need to use other libraries for their needs, making the learning curve of express hard to predict.

# **12\. Community**

Express has a very large community which makes it almost impossible to not find what you are looking for. Despite Nest being newer and still facing some issues to fix. Luckily Nest team is working hard to make Nest better.

# 13\. Does Nest worth learning?

Nest is cutting-edge technology and dependent on express and fastify. Hence, it makes Nest less sustainable than express and fastify itself. Still, Nest is a great tool and considering the advantages we mentioned above, it is worth learning.

## Credit

![Karahan Ozen](https://miro.medium.com/fit/c/60/60/1*c5g15x1w3Lj0-N7KAukM2A.jpeg)
