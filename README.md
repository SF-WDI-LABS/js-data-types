<!--
Creator: SF WDI instructors; most recent edits by Michelle Ferreirae
Location: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# JavaScript Data Types

### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

JavaScript is the most complete, capable language usable across browsers. It lets us change the content of a page programmatically (on the fly) instead of being stuck with just what's written in the HTML code.  It enables complex user interactions.

The need to process information drives programming languages.  JavaScript's data types define how it can store and manipulate information. They're the building blocks of everything that can be done in JavaScript.

### What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- Identify JavaScript data types.
- Declare variables in the Chrome developer tools.
- Get and set the values of variables.
- Use built-in methods to manipulate arrays and perform math operations.

### Where should we be now?
<!-- call out the skills that are prerequisites -->
*Before this workshop, developers should already be able to:*

- Open the Chrome developer tools (for example, with Command Option J).


## Primitives

A primitive value is represented at the lowest level of implementation of a programming language. All primitives are immutable, meaning they can't be changed.

JavaScript has **6 primitive data types**:

  * **string:** words or phrases (in quotes)
  * **number:** integer, floating point number (decimal), `NaN`<sup>+</sup>
  * **boolean:** `true` or `false`
  * **`null`:** non-existent object (used for blanking out variables)
  * **`undefined`:** empty variable
  * **symbol:** reusable identifier for object properties ([only in ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol))


One of JavaScript's quirks is having both `null` and `undefined`. As a rule of thumb, you should let JavaScript decide when something is `undefined`.  You should use `null` wherever you want to "blank out" a variable so that it has no value.



<!-- | Type | Example(s) | Falsey Value(s) |
| :--- | :-----  | :-- |
| **string** | `'lightyear'`, `"867-5309"` | `''` or `"" ` |
| **number** | `3.1415`, `31` | `0`, `-0`, `NaN`<sup>+</sup> |
| **boolean** | only `true` or `false` | `false` |
| **null** | only `null` | `null` |
| **undefined** | only `undefined` | `undefined` |
| **symbol** | `Symbol("first")` | &nbsp; | -->

<sup>+</sup>`NaN` is a special global value meaning "Not A Number". `NaN` is the returned value when numerical evaluations fail, e.g. `8/"hello"`.

<details>
  <summary>Check for Understanding</summary>
  <p>
    Whiteboarding on your table, write what primitive type you would expect each piece of data about a person to be represented as.
    <ol>
      <li>name</li>
      <li>gaStudent, whether or not they are a student at GA</li>
      <li>age</li>
      <li>streetNumber</li>
      <li>streetName</li>
      <li>city</li>
      <li>state</li>
      <li>zipCode</li>
      <li>phoneNumber</li>
    </ol>
  </p>
</details>

### Expressions and Operations

An expression is code that evaluates to some value.

Expressions can include data (like `4` or `true`) and operators (like `=`, `*`, `!`), object and array lookup, and function calls.

Expressions let us process data in useful ways.

```js
1 + 1;
//=> 2

2 - 1;
//=> 1
```

Another commonly used operation in coding is the modulo operator, `%`. It finds the remainder after diving left side by right side.

```js
18 % 100;
//=> 18

5 % 2;
//=> 1
```

In JavaScript, you can also use a `+` operation on strings. This is called **string concatenation**.  In JavaScript, it changes non-strings that you add into strings.

```js
"Hello, " + "world!";
//=> "Hello, world!"

"WDI " + 33;
//=> "WDI 33"
```

These are fairly standard features across high-level programming languages.

### Variables

Variables are labeled locations for storing data. You can create a variable with the reserved word `var`, with or without giving it an initial value:

```js
var numForks;
var lunchTime = 1215;
```

Instead of writing `1215` over and over in code, a program can access the information by variable name:

```js
lunchTime
//=> 1215
```

If the value needs to change, the variable can be updated using the assignment operator `=`.

```js
lunchTime = '12:15';
```

Note that you can also freely change the type of data a variable is storing.

#### Check for Understanding
Working with a partner and whiteboarding on your table, write what type each variable has, as well as what the value of the final expression would be.

1.
```js
  var a = 3;
  var b = 7;
  a+b;
```
2.
```js
  var a = "Hello";
  var b = "name";
  a + " " + name;
```
3.
```js
  var a = "Hello";
  var b = 5;
  a + " " + b;
```
4.
```js
  var a = true;
  var b = "The truth is ";
  b + a;
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
//=> ["Moe", "Larry", "Curly"]
```

#### Array Manipulation

**Creating** an array (literal):

```js
var fruits = ["Apple", "Banana", "Cherry", "Durian", "Elderberry",
"Fig", "Guava", "Huckleberry", "Ice plant", "Jackfruit"];
```

**Getting** an element by index:

```js
fruits[0]; //=> "Apple"
fruits[3]; //=> "Durian"
```

**Setting** the value at an index:

```js
fruits[3] = "Grape";
```

#### Array Properties and Methods

**Finding the number of elements**, in the **length** property:

```js
fruits.length; //=> 10
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
fruits.unshift("Apricot"); //=> 11
```

**Adding** an element to the **end**:  

```js
fruits.push("Kiwi"); //=> 12
```

**Removing** an element from the **front**:

```js
fruits.shift(); //=> "Apricot"
```

**Removing** an element from the **end**:  

```js
fruits.pop(); //=> "Kiwi"
```

**Finding** the index of an element:  

```js
fruits.indexOf("Jackfruit"); // 9
fruits[9]; //=> "Jackfruit"
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
//=> 16

// returns a random decimal number between 0 and 1
Math.random();
//=> 0.229375290430

// rounds a floating point number to an integer
Math.round(2.5);
//=> 3
```


### `typeof`

Use JavaScript's [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) method to check the type of a variable or value.

### Independent Practice

Practice with this [training](https://github.com/SF-WDI-LABS/js-data-types-training).  


### Closing Thoughts

For web developers, it's critically important to be able to work with JavaScript objects.  JavaScript's features are mostly built into objects like `Date`, `Math`, and `document`. We'll cover objects in more detail tomorrow.

The most important things to practice right now are:

- getting and setting values from within complex structures that include nested arrays and strings.
- learning to read documentation.

### Resources

* [JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
