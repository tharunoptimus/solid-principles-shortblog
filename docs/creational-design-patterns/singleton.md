---
sidebar_position: 4
---

# Singleton

![Singleton](./img/singleton.png)

Imagine you have a pet dog. You only have one dog, and you want to make sure that everyone in your family knows that the dog is the same dog. You don't want someone to think that there are two dogs, or that the dog disappeared and was replaced by a new dog.

The singleton design pattern is like that. It ensures that there is only one instance of a particular object, and that everyone in your code knows that it is the same object. This can be useful for things like configuration settings, logging, and caching.

In JavaScript, you can implement a singleton using a closure. A closure is a function that has access to the variables in its surrounding scope, even after the surrounding function has finished executing.

Here is an example of how to implement a singleton using a closure in JavaScript:

```js
const mySingleton = (function () {
    let instance

    function getInstance() {
        if (!instance) {
            instance = new MySingleton()
        }
        return instance
    }

    return {
        getInstance: getInstance
    }
})()

const instance1 = mySingleton.getInstance()
const instance2 = mySingleton.getInstance()

console.log(instance1 === instance2) // true
```

This code creates a singleton object called `mySingleton`. The `getInstance()` method on the `mySingleton` object returns the same instance of the object every time it is called. This ensures that there is only one instance of the `mySingleton` object, and that everyone in our code knows that it is the same object.