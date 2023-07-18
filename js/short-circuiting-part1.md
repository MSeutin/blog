# JS Short Circuiting to Shorten your Code - Part 1 (Logical OR)
There are 2 ways to use short-circuiting in JS, using the `||` (logical OR) or using the `&&` (logical &&).

## Logical OR `||`
The following example is similar to a use case I used in a code challenge recently.  Let's declare two objects, `person1` and `person2`:
```js
// person1 has an age property
let person1 = {
  name: 'michael',
  lastName: 'smith',
  age: 30
}

// person2 does not have an age property
let person2 = {
  name: 'bob',
  lastName: 'wilson'
}
```
We may receive `person1` or `person2` as arguments to a function and not know which one has the property `age` defined.
If we have to do some arithmetics on `age` we need a number, but `person2.age` will return `undefined`, so here is a way to assign a default number to any object that lacks the `age` property:
```js
// short-circuiting with || to provide default values for age
let age1 = person1.age || 0
let age2 = person2.age || 0

console.log(`age1: ${age1}, age2: ${age2})
// OUTPUT: age1: 30, age2: 0

console.log(`person2.age is not defined: ${person2.age}`)
// OUTPUT: person2.age is not defined: undefined
```
We can replace any `undefined` age property with the number `0`.

## How It Works
