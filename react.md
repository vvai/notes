# React and redux notes

## General

* Don't mutate old state in reducers, use spread operator

## setState() [link](https://medium.com/javascript-scene/setstate-gate-abc10a9b2d82)
`setState()` does not immediately mutate `this.state` but creates a pending state transition. Accessing `this.state` after calling this method can potentially return the existing value. To fix it, use a second form of `setState()` that accepts a function rather than an object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument:

```javascript
// Correct
this.setState((prevState, props) => ({
  count: prevState.count + props.increment
}));
```
This is basically a reducer, where `prevState` acts like an accumulator, and `props` acts as the source for the new update data. Like reducers from Redux, you can reduce with this function using any standard reduce utility (including `Array.prototype.reduce()`). Also like Redux, the reducer should be a pure function.

## Stateless components

```javascript
const Greeting = ({ name }, context) =>
  <div style={context.style}>{name}</div>;

Greeting.propTypes = {
  name: PropTypes.string.isRequired
}
Greeting.defaultProps = {
  name: "Guest"
}
```
