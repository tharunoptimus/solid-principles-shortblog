---
sidebar_position: 2
---

# Iterator

![Iterator](./img/iterator.png)

Imagine you have a box of chocolates. You want to eat all the chocolates, but you don't want to have to reach into the box every time you want to eat one.

The iterator pattern is like that. It allows you to iterate over a collection of objects without having to know how the collection is implemented. In this case, the collection is the box of chocolates, and the iterator is the spoon. The spoon allows you to eat the chocolates without having to reach into the box.

In JavaScript, you can implement an iterator using a class. The iterator class would have methods for moving to the next element in the collection, and for getting the current element in the collection. For example, the `ChocolateIterator` class might have methods called `hasNext()` and `next()`.

Here is an example of how to implement an iterator using a class in JavaScript:

```js
class ChocolateIterator {
    constructor(chocolates) {
        this.chocolates = chocolates
        this.currentChocolate = 0
    }

    hasNext() {
        return this.currentChocolate < this.chocolates.length
    }

    next() {
        if (!this.hasNext()) {
            throw new Error("No more chocolates")
        }
        const chocolate = this.chocolates[this.currentChocolate]
        this.currentChocolate++
        return chocolate
    }
}

const chocolates = ["KitKat", "Snickers", "Twix"]
const iterator = new ChocolateIterator(chocolates)

while (iterator.hasNext()) {
    const chocolate = iterator.next()
    console.log(chocolate) // "KitKat", "Snickers", "Twix"
}
}
```

In this code, the `ChocolateIterator` class is the iterator. It has methods for moving to the next element in the collection, and for getting the current element in the collection. The `hasNext()` method returns `true` if there is another chocolate in the collection, and `false` otherwise. The `next()` method returns the next chocolate in the collection.

The iterator pattern allows us to iterate over a collection of objects without having to know how the collection is implemented. This can be useful when we want to make our code more modular and easier to test.