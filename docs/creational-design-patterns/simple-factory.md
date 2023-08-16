---
sidebar_position: 2
---

# Simple Factory

![Simple Factory](./img/simple-factory.png)


Let's say you want to create a factory that makes different kinds of cars. You could have a separate function for each type of car, like `makeCar()`, `makeTruck()`, and `makeSUV()`. But this would be a lot of code, and it would be hard to keep track of.

The simple factory pattern is a way of creating different kinds of objects without having to write a separate function for each one. It works by having a single factory function that takes an input parameter, like the type of object to create. The factory function then returns a new object of the specified type.

In JavaScript, the simple factory pattern can be implemented using a class called `Factory`. The `Factory` class has a static method called `create()` that takes an input parameter and returns a new object of the specified type.

Here is an example of how to use the simple factory pattern to create a factory that makes different kinds of cars in JavaScript:

```js
const Factory = class {
    static create(type) {
        switch (type) {
            case "car":
                return new Car()
            case "truck":
                return new Truck()
            case "suv":
                return new SUV()
            default:
                throw new Error("Invalid type")
        }
    }
}

const car = Factory.create("car")
console.log(car) // { type: "car", make: "Honda", model: "Civic" }

const truck = Factory.create("truck")
console.log(truck) // { type: "truck", make: "Ford", model: "F-150" }

const suv = Factory.create("suv")
console.log(suv) // { type: "suv", make: "Toyota", model: "RAV4" }
```
