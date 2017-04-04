# Notes about IT in whole

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
