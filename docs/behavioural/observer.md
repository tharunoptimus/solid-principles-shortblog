---
sidebar_position: 3
---

# Observer

![Observer](./img/observer.png)

Imagine you are a child and you want to know when your parents come home. You can't always be at the door to see them, so you need a way to be notified when they arrive.

The observer pattern is like that. It allows you to subscribe to changes in an object. When the object changes, it will notify all of its subscribers. In this case, the object is your parents, and the subscribers are you and your siblings. When your parents come home, they will notify you and your siblings that they have arrived.

In JavaScript, you can implement the observer pattern using a class. The object that is being observed would be called the "subject", and the objects that are subscribed to the changes would be called the "observers". The subject would have a method for adding and removing observers, and for notifying its observers when it changes. For example, the `Parents` class might have methods called `addObserver()`, `removeObserver()`, and `notifyObservers()`.

Here is an example of how to implement the observer pattern using a class in JavaScript:

```js
class Parents {
    constructor() {
        this.observers = []
    }

    addObserver(observer) {
        this.observers.push(observer)
    }

    removeObserver(observer) {
        this.observers.splice(this.observers.indexOf(observer), 1)
    }

    notifyObservers() {
        for (const observer of this.observers) {
            observer.update()
        }
    }

    comeHome() {
        this.notifyObservers()
    }
}

class Child {
    constructor(parents) {
        parents.addObserver(this)
    }

    update() {
        console.log("My parents came home!")
    }
}

const parents = new Parents()
const child1 = new Child(parents)
const child2 = new Child(parents)

parents.comeHome() // "My parents came home!"
```

In this code, the `Parents` class is the subject. It has methods for adding and removing observers, and for notifying its observers when it changes. The `Child` class is the observer. It has a method for updating itself when the subject changes.

The observer pattern allows us to decouple the objects that are observing from the objects that are being observed. This can make our code more modular and easier to test.