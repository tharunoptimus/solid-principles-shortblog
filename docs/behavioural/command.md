---
sidebar_position: 1
---

# Command

![Command](./img/command.png)

Imagine you are playing with your toy cars. You want to make the cars do different things, like drive forward, turn left, and turn right. But you don't want to have to remember all the different commands for each car.

The command pattern is like that. It allows you to encapsulate a request as an object. This object can then be passed around and executed later. In this case, the request would be a command like "drive forward" or "turn left". The object would be a command object.

In JavaScript, you can implement a command object using a class. The command object class would have a method for executing the command. For example, the `DriveForwardCommand` class might have a method called `execute()` that would make the car drive forward.

Here is an example of how to implement a command object using a class in JavaScript:

```js
class DriveForwardCommand {
    constructor(car) {
        this.car = car
    }

    execute() {
        this.car.driveForward()
    }
}

const car = new Car()
const command = new DriveForwardCommand(car)

command.execute() // the car drives forward
```

In this code, the `DriveForwardCommand` class is the command object. It has a method called `execute()` that executes the command. The `execute()` method calls the `driveForward()` method on the `car` object.

The command pattern allows us to encapsulate a request as an object. This can be useful when we want to decouple the request from the execution of the request. This can make our code more modular and easier to test.