---
sidebar_position: 5
---

# Template Method

![Template Method](./img/template.png)

Imagine you are making a cake. You have a recipe that tells you the steps to follow, but you can choose to add your own personal touches to the cake. For example, you can add chocolate chips, nuts, or sprinkles.

The template method pattern is like that. It allows you to define the skeleton of an algorithm, and then let subclasses override the specific steps of the algorithm. In this case, the algorithm is the cake recipe, and the subclasses are the different types of cakes you can make.

Here is an example of how to implement the template method pattern using a class in JavaScript:

```js
class Cake {
    constructor(flavor) {
        this.flavor = flavor
    }

    bake() {
        this.preHeatOven()
        this.mixIngredients()
        this.pourBatterIntoPan()
        this.bakeCake()
        this.coolCake()
    }

    preHeatOven() {
        console.log("Preheat oven to 350 degrees Fahrenheit")
    }

    mixIngredients() {
        console.log("Mix together flour, sugar, eggs, and butter")
    }

    pourBatterIntoPan() {
        console.log("Pour batter into greased and floured cake pan")
    }

    bakeCake() {
        console.log("Bake cake for 30 minutes")
    }

    coolCake() {
        console.log("Cool cake for 10 minutes before frosting")
    }

    frostCake() {
        console.log("Frost cake with your favorite frosting")
    }
}

class ChocolateCake extends Cake {
    frostCake() {
        console.log("Frost cake with chocolate frosting")
    }
}

class VanillaCake extends Cake {
    frostCake() {
        console.log("Frost cake with vanilla frosting")
    }
}

const chocolateCake = new ChocolateCake("chocolate")
const vanillaCake = new VanillaCake("vanilla")

chocolateCake.bake()
chocolateCake.frostCake()

vanillaCake.bake()
vanillaCake.frostCake()
```

In this code, the `Cake` class is the abstract class. It defines the skeleton of the algorithm, but it leaves the specific steps of the algorithm to be implemented by the subclasses. The `ChocolateCake` class and the `VanillaCake` class are concrete implementations of the `Cake` class. They override the `frostCake()` method to frost the cake with their favorite frosting.

The template method pattern allows us to decouple the algorithm from the implementation. This can make our code more modular and easier to test.


## How is Template Method different from Strategy?

Sure. The template method pattern and the strategy pattern are both behavioral design patterns. They are both used to decouple the algorithm from the implementation. However, they differ in how they achieve this decoupling.

The template method pattern defines the skeleton of an algorithm, and then lets subclasses override the specific steps of the algorithm. This is like a cake recipe that tells you the steps to follow, but you can choose to add your own personal touches to the cake.

The strategy pattern defines a family of algorithms, and lets the client code choose which algorithm to use. This is like a video game that lets you choose your character's strategy.

Here is an example of how to implement the template method pattern using a class in JavaScript:

```js
class Cake {
    constructor(flavor) {
        this.flavor = flavor
    }

    bake() {
        this.preHeatOven()
        this.mixIngredients()
        this.pourBatterIntoPan()
        this.bakeCake()
        this.coolCake()
    }

    preHeatOven() {
        console.log("Preheat oven to 350 degrees Fahrenheit")
    }

    mixIngredients() {
        console.log("Mix together flour, sugar, eggs, and butter")
    }

    pourBatterIntoPan() {
        console.log("Pour batter into greased and floured cake pan")
    }

    bakeCake() {
        console.log("Bake cake for 30 minutes")
    }

    coolCake() {
        console.log("Cool cake for 10 minutes before frosting")
    }

    frostCake() {
        console.log("Frost cake with your favorite frosting")
    }
}

class ChocolateCake extends Cake {
    frostCake() {
        console.log("Frost cake with chocolate frosting")
    }
}

class VanillaCake extends Cake {
    frostCake() {
        console.log("Frost cake with vanilla frosting")
    }
}

const chocolateCake = new ChocolateCake("chocolate")
const vanillaCake = new VanillaCake("vanilla")

chocolateCake.bake()
chocolateCake.frostCake()

vanillaCake.bake()
vanillaCake.frostCake()
```

In this code, the `Cake` class is the abstract class. It defines the skeleton of the algorithm, but it leaves the specific steps of the algorithm to be implemented by the subclasses. The `ChocolateCake` class and the `VanillaCake` class are concrete implementations of the `Cake` class. They override the `frostCake()` method to frost the cake with their favorite frosting.

The template method pattern allows us to decouple the algorithm from the implementation. This can make our code more modular and easier to test.

Here is an example of how to implement the strategy pattern using a class in JavaScript:

```js
class Strategy {
    bake() { }
}

class ChocolateStrategy extends Strategy {
    bake() {
        console.log("Bake chocolate cake")
    }
}

class VanillaStrategy extends Strategy {
    bake() {
        console.log("Bake vanilla cake")
    }
}

class Cake {
    constructor(strategy) {
        this.strategy = strategy
    }

    bake() {
        this.strategy.bake()
    }
}

const chocolateCake = new Cake(new ChocolateStrategy())
const vanillaCake = new Cake(new VanillaStrategy())

chocolateCake.bake() // "Bake chocolate cake"
vanillaCake.bake() // "Bake vanilla cake"
```

In this code, the `Strategy` interface defines the family of algorithms. The `ChocolateStrategy` class and the `VanillaStrategy` class are concrete implementations of the `Strategy` interface. The `Cake` class takes a strategy as a constructor argument. The `bake()` method calls the `bake()` method on the strategy object.

The strategy pattern allows us to choose different algorithms at runtime. This can be useful when we want to change the behavior of our code without having to modify the code itself.