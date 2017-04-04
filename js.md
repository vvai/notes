# JS notes

## Immutable techniques

```javascript
const arr = [1, 2, 3, 4, 5]
const updatedArr = [...arr] // shallow copy of array
const updatedArr2 = [...arr, 6] // shallow copy with new item
const updatedArr3 = [...arr.slice(0,2), ...houses.slice(3)] // shallow copy without element
const updatedArr3 = [...arr.slice(0,2), 13, ...houses.slice(3)] // shallow copy with updated element

const obj = {
  name: 'something',
  age: 26,
  skills: ['nothing']
}
const copyObj = { ...obj, age: 27 } // shallow copy and update
copyObj.skills = [...copyObj.skills, 'still nothing']
```
