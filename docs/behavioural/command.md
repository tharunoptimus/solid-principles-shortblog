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


## How is it any different from Facade?

Facade and command are two different design patterns that are used to simplify the complexity of a system.

A facade is a single object that provides a simplified interface to a complex subsystem. This makes it easier for clients to use the subsystem without having to understand the details of how it works. For example, a facade for a car might provide methods for starting the car, stopping the car, and changing gears. This would make it easier for a driver to use the car without having to know how the engine, transmission, and brakes work.

A command is an object that encapsulates a request to perform an action. This makes it easier to decouple the requestor from the receiver of the request. For example, a command to play a song might have a method called `execute()` that plays the song. This would make it easier for a music player to play a song without having to know who requested the song or why.

The main difference between facade and command is that facade provides a simplified interface to a complex subsystem, while command encapsulates a request to perform an action.

Here is an analogy that might help you understand the difference between facade and command:

* **Facade:** A facade is like a tour guide who takes you around a city. The tour guide knows the city well and can show you all the important places without having to explain how the city works.
* **Command:** A command is like a remote control that you use to operate a TV. The remote control doesn't know how the TV works, but it can send commands to the TV to turn it on, off, change channels, and adjust the volume.
