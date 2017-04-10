# Notes about IT in whole

## Best practices

#### About indentions [link](http://jrsinclair.com/articles/2017/indentation-is-the-enemy-less-complex-javascript/)
When you see an indented piece of code, there is something you have to remember while you read that code. We call this something context. And the more levels of indentation, the more context you have to keep in mind. Each level of indentation adds cognitive load. Each level of indentation intertwines some extra stuff. Each level of indentation indicates added complexity. Indentation is not the real enemy. The real enemy is complexity. Much of the complexity introduced by control structures in our code doesn’t need to be there.

#### About abstraction [link](http://jrsinclair.com/articles/2017/indentation-is-the-enemy-less-complex-javascript/)
Moving up a level of abstraction allows us to express what we want to do with more clarity. Most of the time we are burying complexity, rather than removing it completely. But that still has enormous benefits. Even if I write my own version of `pluck()`, if I use it more than once, then I’ve removed complexity in at least two places. The complexity is now concentrated into one function. And I’ve also increased the expressiveness of my code. Squishing complex code into one function is much better than smearing it everywhere.

## Generative testing

In a generative test the engineer describes the shape of the data, and then defines the properties that the results should have, and the test runner provides randomized data to check against. The key part is to define a property that can be verified, in other words we need to define a function that should always returns true for any given input.

Example:
```javascript
    const add = (a, b) => a + b
    (a, b) => a + b === add(a, b) // this is useless
    const zeroProperty = x => add(x, 0) === x
    const commutativeProperty = (x, y) => add(x, y) === add(y, x)
    const result = add(4, 0) + add(0, 4) === add(4, 4)
    const result = x => decodeSomething(encodeSomething(x)) === x // another good example
```


