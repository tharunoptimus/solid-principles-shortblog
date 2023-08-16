---
sidebar_position: 4
---

# Strategy

![Strategy](./img/strategy.png)

Imagine you are playing a video game and you want to choose a strategy. You can choose to be a warrior, a mage, or a rogue. Each strategy has its own strengths and weaknesses. The warrior is strong but slow, the mage is weak but fast, and the rogue is balanced.

The strategy pattern is like that. It allows you to choose different algorithms at runtime. In this case, the algorithms are the different strategies. The `Strategy` interface would define the common methods for all the strategies. For example, the `Strategy` interface might have methods called `attack()` and `defend()`.

Here is an example of how to implement the strategy pattern using a class in JavaScript:

```js
class Strategy {
    attack() { }
    defend() { }
}

class Warrior extends Strategy {
    attack() {
        console.log("The warrior attacks!")
    }

    defend() {
        console.log("The warrior defends!")
    }
}

class Mage extends Strategy {
    attack() {
        console.log("The mage attacks!")
    }

    defend() {
        console.log("The mage defends!")
    }
}

class Rogue extends Strategy {
    attack() {
        console.log("The rogue attacks!")
    }

    defend() {
        console.log("The rogue defends!")
    }
}

const warrior = new Warrior()
const mage = new Mage()
const rogue = new Rogue()

const player = {
    strategy: warrior,
}

player.strategy.attack() // "The warrior attacks!"
player.strategy.defend() // "The warrior defends!"

player.strategy = mage

player.strategy.attack() // "The mage attacks!"
player.strategy.defend() // "The mage defends!"

player.strategy = rogue

player.strategy.attack() // "The rogue attacks!"
player.strategy.defend() // "The rogue defends!"

```

In this code, the `Strategy` interface is the abstract class. The `Warrior`, `Mage`, and `Rogue` classes are concrete implementations of the `Strategy` interface. The `player` object has a property called `strategy` that stores the current strategy. The `player` object can change its strategy at runtime.

The strategy pattern allows us to decouple the algorithm from the object that is using the algorithm. This can make our code more modular and easier to test.