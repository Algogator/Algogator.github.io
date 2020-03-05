---
layout: "post"
title: "Design Patterns"
date: "2020-03-05 12:16"
---

### Singleton (Creational)

You create only ONE instance of a class. And provide global access to that instance. For example a database object.

![You work with the same object all the time](https://refactoring.guru/images/patterns/content/singleton/singleton-comic-1-en.png)

### Decorator (Structural)

Add new behavior to an object by putting these objects inside a wrapper object that contain new behaviors. The wrapper alters the result by doing something before or after.

You could try to extend class but sub-classes can only inherit from one parent.

### Command (Behavioral)

Turn a request into an object which has information about the request. You can create methods that can then handle different kinds of requests.

- Has receivers, commands associated with receivers, senders associated with specific commands. 
