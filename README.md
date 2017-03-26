<!--
Creator: SF WDI instructors
Last edited by: Brianna
Location: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# JavaScript Data Types

### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

**Why JavaScript?**

JavaScript is the most complete, capable language usable across browsers. It lets us change the content of a page programmatically (on the fly) instead of being stuck with just what's written in the HTML code.  It enables complex user interactions.


**Why learn data types?**

The need to process **information** drives programming languages.  JavaScript's data types define how it can store and manipulate information. They're the building blocks of everything that can be done in JavaScript.

For web developers, it's also critically important to be able to work with JavaScript objects.  JavaScript's features are mostly built into objects like `Array`, `Function`, and, for web, `document`.


### What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- Identify JavaScript data types.
- Declare variables in the Chrome developer tools.
- Get and set the values of variables.
- Differentiate between primitive and reference values.
- Explain constants as a special kind of variable.


### Where should we be now?
<!-- call out the skills that are prerequisites -->
*Before this workshop, developers should already be able to:*

- Open the Chrome developer tools (for example, with Command Option J).
- Use JavaScript to perform basic arithmetic operations in the developer tools.


## Primitives

A primitive value is represented at the lowest level of implementation of a programming language.

JavaScript has **6 primitive data types**:

  * **string:** words or phrases (in quotes)
  * **number:** integer, floating point number (decimal), `NaN`<sup>+</sup>
  * **boolean:** `true` or `false`
  * **`null`:** non-existent object (used for blanking out variables)
  * **`undefined`:** empty variable
  * **symbol:** reusable identifier for object properties ([only in ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol))


One of JavaScript's quirks is having both `null` and `undefined`. As a rule of thumb, you should let JavaScript decide when something is `undefined`.  You should use `null` wherever you want to "blank out" a variable so that it has no value.



<!--
| Type | Example(s) | Falsey Value(s) |
| :--- | :-----  | :-- |
| **string** | `'lightyear'`, `"867-5309"` | `''` or `"" ` |
| **number** | `3.1415`, `31` | `0`, `-0`, `NaN`<sup>+</sup> |
| **boolean** | only `true` or `false` | `false` |
| **null** | only `null` | `null` |
| **undefined** | only `undefined` | `undefined` |
| **symbol** | `Symbol("first")` | &nbsp;--&nbsp; |

<sup>+</sup>`NaN` is a special global value meaning "Not A Number". `NaN` is the returned value when numerical evaluations fail, e.g. `8/"hello"`.
-->

**Check for Understanding**: Whiteboarding on your table, write what primitive type you would expect each piece of data about a person to be represented as:

<ol>
  <li>`name`</li>
  <li>`isGaStudent`, whether or not they are a student at GA</li>
  <li>`age`</li>
  <li>`streetNumber`</li>
  <li>`streetName`</li>
  <li>`city`</li>
  <li>`state`</li>
  <li>`zipCode`</li>
  <li>`phoneNumber`</li>
</ol>

### Expressions and Operations

An expression is code that evaluates to some value.

Expressions can include data (like `4` or `true`) and operators (like `=`, `*`, `!`), object and array lookup, and function calls.

Expressions and operators let us process data in useful ways.

```js
1 + 1;
// 2

2 - 1;
// 1
```

Another commonly used operator in coding is the modulo operator, `%`. It finds the remainder after diving left side by right side.

```js
18 % 100;
// 18

7 % 2;
// 1
```

In JavaScript, you can also use a `+` operator on strings. This is called **string concatenation**.  In JavaScript, it can change non-strings into strings if one of the sides is a string already.

```js
"Hello, " + "world!";
// "Hello, world!"

"WDI " + 33;
// "WDI 33"
```

These are fairly standard features across high-level programming languages.

### Variables

Variables are labeled locations for storing data. They save programmers time.

If you have a variable called `lunchTime`, then instead of writing `1230` over and over in code, a program can access the information by variable name:

```js
lunchTime
// 1230   
```

This is more to type, but it saves time if you ever have to go back to your code and change when lunch is. Instead of searching for `1230` everywhere it appears, you can just change the value where `lunchTime` starts storing it, and everything else in scope will 'see' the change.

There are 4 ways to create a variable in JavaScript.


#### ES5 Variable Creation: global and `var`

1. Just assign a value to a name using the assignment operator `=`:

  ```js
  document = 'main';
  ```

   Creating a variable this gives it **global scope**, meaning it can be accessed very widely, including anywhere in its file.  This is considered a **bad practice** because it's almost always a mistake, or it leads to mistakes like accidentally overwriting an external variable with the same name.

2. Create a variable with the reserved word `var`, with or without giving it an initial value:

  ```js
  var vegetable;
  var protein = 'tofurkey';
  ```

  Variables created with `var` have function-level scoping, which means they're defined anywhere inside the function where they're created. If they're not inside a function, they're global. But at least with `var` we have the option to keep things more organized and modular.

The two strategies above have been around as long as JavaScript. Variables created without any reserved word or with the reserved word `var` have a cool extra property called **hoisting**.  No matter where in their scope they're given a value, they start out inside that scope as `undefined`.

That'll be clearer with an example.

**You do**: Examine the code sample below.  What do you think will be logged to the console each time?  After you make a guess, run the code in your developer tools.


```js
function add(a, b) {
  console.log('above declaration', sum);
  var sum = a + b;
  console.log('below declaration', sum);
  return sum;
}
console.log(add(2,3));
console.log('outside function scope', sum);
```

Using `var` was the best way to create variables in ES5, but in ES6 two new strategies were introduced.


#### ES6 Variable Creation: `let` and `const`

1. Create a variable with the reserved word `let`, with or without giving it an initial value:

  ```js
  let highScorer;
  let highScore = 0;
  ```

  The reserved word `let` works very similarly to `var`, except that variables created with `let`:
    * have **block scope** instead of function scope
    * do not get hoisted
    * can't be redeclared at the same scope level (the value can change, though)


2. Create a constant with the reserved word `const`, and give it an initial value:

  ```js
  const 0;
  ```

  The reserved word `let` works very similarly to `var`, except that variables created with `let`:
    * have **block scope** instead of function scope
    * do not get hoisted
    * can't be redeclared at the same scope level (the value can change, though)


####Check for Understanding
Working with a partner and whiteboarding on your table, write what type each variable has, as well as what the value of the variable `c` would be.

1.
```js
  var a = 3;
  var b = 7;
  var c = a + b;
```
2.
```js
  var a = "Hello";
  var b = "name";
  var c = a + " " + name;
```
3.
```js
  var a = "Hello";
  var b = 5;
  var c = a + " " + b;
```
4.
```js
  var a = true;
  var b = "The truth is ";
  var c = b + a;
```

### Objects

Primitive data types are not enough for most programming purposes. Objects are **reference data types** that allow us to group primitives together.

Instead of storing a value, variables holding objects store a reference to a location in memory, and the computer looks it up when needed.


  ```js
  var shirt = { size: "L", color: 'green', clean: false };
  ```

Objects store information in key-value pairs. The key acts like a label, and the value is the data or behavior associated with that label.

`Object` is the most basic reference type in JavaScript. Every other non-primitive we'll use -- `Array`, `Function`, `Date` -- is actually built out from the basic `Object` type.


#### Object Manipulation

**Creating** an object literal:

```js
var person = { name: 'Bill', height: '5 feet, 9 inches', age: 34 };
```

**Getting** the value associated with a key:

```js
// this is called bracket notation:
person['age']; // 34
// this is called dot notation:
person.age;    // 34

// what if key doesn't exist?
person['hasGlasses']; // undefined
```

**Adding** a key-value pair:

```js
person['hairColor'] = 'blonde';
person.hairColor = 'blonde';
// { name: 'Bill', height: '5 feet, 9 inches', age: 34, hairColor: 'blonde' }
```

**Setting** the value for a key:

```js
person['hairColor'] = 'green';
person.hairColor = 'green';
// { name: 'Bill', height: '5 feet, 9 inches', age: 34, hairColor: 'green' }
```


**Semi-removing** a value:  

Use `null` as a marker for an empty value.

```js
person.hairColor = null;
```


**Fully removing** a key-value pair (rare):

```js
delete person.height;
// { name: 'Bill', age: 34, hairColor: 'green' }
```

Finding **keys** in the object (rare):

```js
var keys = Object.keys(person);
// ['name', 'age', 'hairColor']
```


**Looping** through Objects (rare):

One way to loop through objects in JavaScript is to use `for ... in` loops:

```js
for (key in person){
  // this next condition is required because of the prototype chain, which we haven't talked about quite yet
  if (person.hasOwnProperty(key)){  
    console.log(key, ": ", person[key]);
  }
}
// the order is not guaranteed, but this console logs:
//   'name': 'Bill'
//   'age': 34
//   'hairColor': null
```





### Arrays
When we're working with data, we generally need to work with more than just primitives. Arrays store collections of data in **sequential** order.  Arrays are an example of a **reference data type** that allows us to group primitives together.
Arrays are great for:

* Storing collections of one kind of data
* Ordered lists
* Enumerating data, i.e. using an index to find items
* Quickly reordering data

```js
var friends = ["Moe", "Larry", "Curly"];
// ["Moe", "Larry", "Curly"]
```

####Array Manipulation

**Creating** an array (literal):

```js
var fruits = ["Apple", "Banana", "Cherry", "Durian", "Elderberry",
"Fig", "Guava", "Huckleberry", "Ice plant", "Jackfruit"];
```

**Getting** an element by index:

```js
fruits[0]; // "Apple"
fruits[3]; // "Durian"
```

**Setting** the value at an index:

```js
fruits[3] = "Grape";
```

#### Array Properties and Methods

**Finding the number of elements**, in the **length** property:

```js
fruits.length; // 10
```

> Note that length is a property, NOT a method, for JavaScript arrays!

**Looping** through Arrays:

```js
  for (var i=0; i<fruits.length; i++){
    console.log(fruits[i]);
  }
  console.log('Blastoff!');
```

**Adding** an element to the **front**:

```js
fruits.unshift("Apricot"); // 11
```

**Adding** an element to the **end**:  

```js
fruits.push("Kiwi"); // 12
```

**Removing** an element from the **front**:

```js
fruits.shift(); // "Apricot"
```

**Removing** an element from the **end**:  

```js
fruits.pop(); // "Kiwi"
```

**Finding** the index of an element:  

```js
fruits.indexOf("Jackfruit"); // 9
fruits[9]; // "Jackfruit"
```

![img](http://www.purfresh.com/images/im_fruit_row.jpg)


Check out MDN's [Array documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) for more information on arrays. In particular, all of the methods listed in the [Array instances](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Array_instances) section are available to use with JavaScript arrays. Commonly used array methods include `join`, `sort`, and `reverse`.


### Working with Other Objects
This is a quick introduction to how to access some useful tools in JavaScript. Tomorrow, we'll go in-depth on objects, how they work, and how to create and use them; for now, it's important to get comfortable working with `Math`functions.

#### `Math`

In order to perform certain number operations, JavaScript has a `Math` object with some very useful methods.

```js
// 2^4
Math.pow(2, 4)
// 16

// returns a random decimal number between 0 and 1
Math.random();
// 0.229375290430

// rounds a floating point number to an integer
Math.round(2.5);
// 3
```


### `typeof`

Use JavaScript's [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) method to check the type of a variable or value.

### Independent Practice

Practice with this [training](https://github.com/sf-wdi-labs/js-data-types-training).  


### Closing Thoughts

For web developers, it's critically important to be able to work with JavaScript objects.  JavaScript's features are mostly built into objects like `Date`, `Math`, and `document`. We'll cover objects in more detail tomorrow.

The most important things to practice right now are:

- getting and setting values from within complex structures that include nested arrays and objects.
- learning to read documentation.

### Resources

* [JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
