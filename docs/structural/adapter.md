---
sidebar_position: 1
---

# Adapter

![Adapter](./img/adapter.png)

Imagine you have a banana and an apple. You want to eat both of them, but you only have a banana peeler. You can't use the banana peeler to peel the apple, because the apple has a different shape than the banana.

The adapter pattern is like that. It allows you to use an object that is incompatible with another object. In this case, the banana peeler is incompatible with the apple, but the adapter pattern allows us to use them together.

In JavaScript, you can implement an adapter using a class. The adapter class would have methods for interacting with both the banana and the apple. For example, it might have a method for peeling the banana and a method for slicing the apple.

Here is an example of how to implement an adapter using a class in JavaScript:

```js
class FruitAdapter {
    constructor(banana, apple) {
        this.banana = banana
        this.apple = apple
    }

    peelBanana() {
        return this.banana.peel()
    }

    sliceApple() {
        return this.apple.slice()
    }
}

const banana = new Banana()
const apple = new Apple()
const adapter = new FruitAdapter(banana, apple)

console.log(adapter.peelBanana()) // "peeled banana"
console.log(adapter.sliceApple()) // "sliced apple"
```

In this code, the `FruitAdapter` class is the adapter. It has methods for interacting with both the banana and the apple. The `peelBanana()` method calls the `peel()` method on the `banana` object, and the `sliceApple()` method calls the `slice()` method on the `apple` object.

The adapter pattern allows us to use objects that are incompatible with each other. This can be useful when we want to use old code with new code, or when we want to use code from different libraries.