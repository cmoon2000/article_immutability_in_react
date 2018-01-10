immutable giành cho tối ưu hóa

liên quan `shouldComponentUpdate()`

bản chất là đi so sánh prop/state hiện tại với prop/state trước đó

Vòng đời (theo thứ tự ⏲):

    + 1. change state undirectly (of course🧛‍)
    + 2. shouldComponentUpdate

🤔 immutable should be shallow or deep copy???

Some keys:

  + The basic principle in React rendering optimization is to let React know that it doesn’t need to render again because we know the resulting DOM will have no changes.

  + mutability make code more implicit

```js
// mutability
var object = { x: 2, y: 4 };
performSomething(object);
object.x; // ?
object.y; // ?

// immutability
var object = { x: 2, y: 4 };
var result = performSomething(object);
object.x; // 2
object.y; // 4
result // ?
```

  + The only value in JavaScript that is not equal to itself. Just try NaN === NaN in your console

  + Pure Functions

    We refer to functions that don’t affect anything in the outside scope as pure functions. As long as a function only takes primitive values as parameters and doesn’t use any variables in its surrounding scope, it is automatically pure, as it can’t affect anything in the outside scope. All variables created inside are garbage-collected as soon as the function returns.