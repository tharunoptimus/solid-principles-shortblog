---
sidebar_position: 3
---

# Factory Method

![Factory Method](./img/factory.png)

Let's say you want to create a factory that makes different kinds of animals. You could have a separate function for each type of animal, like `makeCat()`, `makeDog()`, and `makeBird()`. But this would be a lot of code, and it would be hard to keep track of.

The factory method pattern is a way of creating different kinds of objects without having to write a separate function for each one. It works by having a single factory function that takes an input parameter, like the type of object to create. The factory function then delegates the creation of the object to a subclass of the factory.

In JavaScript, the factory method pattern can be implemented using a class called Factory. The Factory class has a static method called `create()` that takes an input parameter and returns a new object of the specified type. The `create()` method then delegates the creation of the object to a subclass of the `Factory` class.

Here is an example of how to use the factory method pattern to create a factory that makes different kinds of animals in JavaScript:

```js
const Factory = class {
    static create(type) {
        if (type === "cat") {
            return new CatFactory().create()
        } else if (type === "dog") {
            return new DogFactory().create()
        } else if (type === "bird") {
            return new BirdFactory().create()
        } else {
            throw new Error("Invalid type")
        }
    }
}

const catFactory = new CatFactory()
const cat = catFactory.create()
console.log(cat) // { type: "cat", name: "Garfield" }

const dogFactory = new DogFactory()
const dog = dogFactory.create()
console.log(dog) // { type: "dog", name: "Sparky" }

const birdFactory = new BirdFactory()
const bird = birdFactory.create()
console.log(bird) // { type: "bird", name: "Tweety" }
```



## What really is the difference between Simple Factory and Factory Method?

The factory method pattern is a more flexible way of creating different kinds of objects than the simple factory pattern. It allows you to create new types of objects without having to modify the factory function.

Sure. Let's say you want to create a factory that makes different kinds of pizzas. You could have a separate function for each type of pizza, like `makePepperoniPizza()`, `makeHawaiianPizza()`, and `makeVegetarianPizza()`. But this would be a lot of code, and it would be hard to keep track of.

The simple factory pattern can be used to create this factory. The factory function would take an input parameter, like the type of pizza to create, and return a new object of the specified type. For example, the `makePizza()` function might look like this:

```js
const makePizza = (type) => {
  switch (type) {
    case "pepperoni":
      return new PepperoniPizza();
    case "hawaiian":
      return new HawaiianPizza();
    case "vegetarian":
      return new VegetarianPizza();
    default:
      throw new Error("Invalid type");
  }
}
```

This is a simple factory pattern, but it has a few limitations. First, it's not very flexible. If we want to add a new type of pizza, we have to modify the `makePizza()` function. Second, it's not very reusable. If we want to use the factory to create other objects, we have to copy and paste the `makePizza()` function.

The factory method pattern can solve these limitations. The factory method pattern defines a factory interface, but leaves the implementation of the factory to subclasses. This allows us to create different types of factories without having to modify the factory interface. For example, we could create a `PizzaFactory` class that implements the factory interface, and then create subclasses of `PizzaFactory` for each type of pizza.

The `PizzaFactory` class might look like this:

```js
const PizzaFactory = class {
  create() {
    throw new Error("This method must be implemented by a subclass")
  }
}
```

The `PepperoniPizzaFactory` class would be a subclass of `PizzaFactory`, and it would implement the `create()` method to return a new `PepperoniPizza` object:

```js
const PepperoniPizzaFactory = class extends PizzaFactory {
  create() {
    return new PepperoniPizza()
  }
}
```

The `HawaiianPizzaFactory` class would be another subclass of `PizzaFactory`, and it would implement the `create()` method to return a new `HawaiianPizza` object:

```js
const HawaiianPizzaFactory = class extends PizzaFactory {
  create() {
    return new HawaiianPizza()
  }
}
```

The factory method pattern is a more flexible and reusable way to create different kinds of objects than the simple factory pattern. It allows us to create new types of objects without having to modify the factory function, and it allows us to use the factory to create other objects.
