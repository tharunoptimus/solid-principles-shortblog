---
sidebar_position: 1
---

# Builder Pattern

![Builder](./img/builder.png)

Let's say you want to build a sandcastle. You need to have all the right materials, like sand, water, and a bucket. You also need to know how to put them together in the right way.

The builder pattern is a way of building complex objects like sandcastles. It separates the construction of the object from its representation. This means that you can focus on building the object without worrying about how it will be represented.

In JavaScript, the builder pattern is implemented using a class called `Builder`. The `Builder` class has methods for setting the properties of the object you want to build. For example, a `SandcastleBuilder` class might have methods for setting the color of the sand, the shape of the castle, and the size of the moat.

Once you have set all the properties of the object, you can call the `build()` method on the `Builder` class. This will create the object and return it to you.

Here is an example of how to use the builder pattern to build a sandcastle in JavaScript:

```js
const SandcastleBuilder = class {
    constructor() {
        this.color = "white"
        this.shape = "round"
        this.size = "small"
    }

    setColor(color) {
        this.color = color
    }

    setShape(shape) {
        this.shape = shape
    }

    setSize(size) {
        this.size = size
    }

    build() {
        return new Sandcastle(this.color, this.shape, this.size)
    }
}

const sandcastleBuilder = new SandcastleBuilder()
sandcastleBuilder.setColor("blue")
sandcastleBuilder.setShape("square")
sandcastleBuilder.setSize("large")

const sandcastle = sandcastleBuilder.build()
console.log(sandcastle) // { color: "blue", shape: "square", size: "large" }

```
