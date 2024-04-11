# Table of Contents
- [What is JS?](#what-is-js)
- [How to run JS code](#how-to-run-js-code)
  + "use strict"
- [How to add JS code](#how-to-add-js-code)
- [Variables](#variables)
  + `let`
  + `const`
  + Why not `var`?
- [Values, Types and Operators](#values-types-and-operators)
  + Numbers, Special Numbers (NaN, Infinity)
  + BigInt
  + Strings
  + Boolean (true/false)
  + `null`
  + `undefined`

# What is JS?
- Invented in 1995
- A method to add programs to web pages in the Netscape Navigator browser. Netscape management decided that the best option was to devise a new language, with syntax similar to Java and less like Scheme or other extant scripting languages. 
- The 'Java' in the name was a hot new language back then and the name "JavaScript" was chosen as a marketing ploy. **JavaScript is not similar to Java** .
- ECMAScript = JavaScript.
- It is ridiculously liberal in what it allows. 
- *Web browsers* are not the only platforms on which JS is used. Some *database management system (DBMS)*, such as MongoDB and CouchDB, use JS as their scripting and query language. *Node.js* also provides an environment for programming JS outside of the browser (server-side).

# How to run JS code
- Console tab in the Inspect (Q) option of the browser.
- Node.js runtime in the Command Prompt.

## "use strict"
- Backwards compatibility won't break existing code, but it has allowed any mistake or imperfect decision made by JS's creators got stuck in the language forever. 
- ES5 (2009) added new features to the language and modified some of the existing ones. To keep the old code working, most such modifications are off by default. You need to explicitly enable them with a special directive: `'use strict'`. 
- `"use strict"` or `'use strict'` works either way. You should put it at the very top. 
- There is no way to cancel it. Once we enter strict mode, there's no going back when the script is run. 
- `"use strict"` is block-scoped. 

```javascript
// For old browsers:
(function() {
  'use strict';

  // ...your code here...
})()
```

- Modern JS with 'classes' and 'modules' `"use strict"` automatically, you can omit it if your script is only classes and modules. 

# How to add JS code
1. Inline JavaScript
```html
<button onclick="alert('Hello')">Click me</button>
```

2. Internal JavaScript
```html
<body>
  <script>
    function greet() {
      alert('Hello');
    }
  </script>
  <button onclick="greet()">Click me</button>
</body>
```
- You can also declare ```<script>``` block after the ```<button>```

3. External JavaScript
```html
<head>
  <script type="text/javascript" src="js/script.js" defer>...</script>
</head>
```
- ```async``` attribute (replacing ```defer```): The script is downloaded in parallel to parsing the page, and **executed as soon as it is available (before parsing completes)**.
- ```defer``` attribute: The script is downloaded in parallel to parsing the page, and **executed after the page has finished parsing**.
- If neither ```async``` or ```defer``` is present: The script is downloaded and executed immediately, blocking parsing until the script is completed. 
<br>
<br>

**DO NOT DO THIS:** No sane man should do this. Just add another ```<script src>```.
```html
<body>
  <script>
    var scriptElement = document.createElement('script');
    scriptElement.src = 'script.js';
    document.head.appendChild(scriptElement);
  </script>
</body>
```

# Variables
- A variable is a 'named storage' for data.
- Without `"use strict"`, you can do assignments (x = 1) without ever declaration.
- Don't reuse variables too much (assigning them again and again), it will be more time-consuming to debug.
- `let` (declaration) reserved keyword and other types of keywords are case-sensitive. `let` !== `Let` and `let` !== `LET`. `Let` and `LET` don't work. 

**`let`**
```javascript
let x;              // declare variable 'x'
x = 'Message';      // input data into it
x = 'New message';  // throw out the old data and put in new data
console.log(x);     // print value of 'x' to console

let messageA = 'a', messageB = 'b', // You can declare multiple variables
    messageC = 'c',
    messageD = 'd';                 // Some utilize each new line for one new variable. However, good coding practices will advise against this due to poor readability.

let noteA = 'a';
let noteB = 'b';
let noteC = 'c';    // You should advocate for this

let id = 12;
let id = 13;        // Error, you can't declare a variable twice                   
```
- So-called 'pure functional programming languages' like Scala, Haskell Erland forbid changing variable's value. Once the value is stored, it's there forever. 

**`const`**
```javascript
const port = 8888;  // Make a constant
const PI = 3.14159265;
const COLOR_RED = '#F00';
```
- There is a widespread practice to use constants as aliases for difficult-to-remember values that are known prior to execution. Such constants are named using capital letters and underscores.

**Why not `var`?**

Ref: [javascript.info](https://javascript.info/var)
- `var` has no block scope. `var` ignores code blocks, it shouldn't be used in global `if` block or global `for` block. 
- `var` is either function-scoped or global-scoped.
```javascript
if (1) {
  var leak = 'var variable';
  let noLeak = 'let variable';
}

console.log(leak);   // print out 'var variable'
console.log(noLeak); // 'noLeak' is not defined
```
- `var` tolerates redeclarations. Later redeclarations will overwrite the previous ones.
- `var` variables can be declared below their usage, or 'hoisted' ('raised') to the top of the function. Declarations are hoisted, but assignments (x = 1) are not (Although JS allows the usage of variable without even declaring, it's generally a bad practice)
```javascript
x = 5; // Assign 5 to x

var elem = document.getElementById("demo");   // Find an element
elem.textContent = x;                     // Display x in the element

var x; // Declare x 
```
- IIFE: In the past, programmers had to invent a way to emulate block-level visibility and it led to "immediately-invoked function expressions". This method is old and unrefined.
```javascript
(function () {
  var message = "Hello";
  console.log(message); // "Hello"
})();
```

## Naming convention
1. Letters, digits, or $name and _name.
2. The first character must not be a digit.
3. camelCase: e.g. myVeryLongVariableName.
4. Case matters: e.g. apple !== APPLE.
5. Stay away from abbreviations or short names like `a`, `b` and `c`, unless you know what you are doing.
6. Make names maximally descriptive and concise (unlike `data` or `value`).
7. Agree on terms within your team and in your mind. If a site visitor is caleld `user` then we should name related variables: `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.
8. Non-Latin letters are allowed, but not recommended.
9. Reserved names (keywords) are forbidden (most of them are single words like return, continue, break, function... you can avoid this by using two or more words every time). Reserved names shouldn't be used next to each other.
10. Hard-coded values for constants are usually depicted by names in uppercase and separated by underscores. Ex: COLOR_RED ("#F00") or PI (3.14159265). A hard-coded value is known before execution time.

# Values, Types and Operators
- [Values](../Computer%20Science/General%20Knowledge.md#values) (from CS/'General Knowledge'.md).

## Types
1. **Numbers**

See also: [Numbers](../Computer%20Science/General%20Knowledge.md#Numbers)

- Numeric values
- JS uses a fixed number of bits, 64 of them, to store a single number value. There are so many patterns (distinct sequences of 1's and 0's) you can make with **64 bits**, which means that number of different numbers that can be represented is **limited**. You can represent (2<sup>64</sup> - 1) different positive integers (whole numbers) (due to how common 64-bit architecture CPUs are).
- However, some bits are delegated to indicate **the sign of the number and the position of the decimal point**. You can only store numbers within the range from (2<sup>53</sup> - 1) to  -(2<sup>53</sup> - 1) for integers. 
  + To be really precise, the 'number' type can store larger integers (up to 1.7976931348623157 * 10<sup>308</sup>), but outside of the safe integer range +/-(2<sup>53</sup> - 1), there'll be a precision error, because not all digits fit into the fixed 64-bit storage. So an "approximate" value may be stored. For example, these two numbers (right above the safe range) are the same:

  ```javascript
  console.log(9007199254740991 + 1); // 9007199254740992
  console.log(9007199254740991 + 2); // 9007199254740992

  // All odd integers greater than (2^53 - 1) can't be stored at all in the 'number' type. 
  ```

- Whole numbers (integers) calculation, under 9 quadrillion, is always precise, not with fractional numbers thanks to [floating-point number problem](../Computer%20Science/General%20Knowledge.md##the-floating-point-number-problem). 

**Arithmetic**: See [Arithmetic](../Computer%20Science/General%20Knowledge.md#arithmetic-and-operators)
- Operators (+, -, *, /, % - Remainder or modulo...)
- Without parentheses, the order in which they are applied is determined by the precedence of the operators. 

**Special Numbers**: 
- Infinity and - Infinity (Negative Infinity). `Infinity - 1` is still Infinity.
- NaN (Not a Number):
  + `0 / 0 = NaN`
  + `Infinity - Infinity = NaN` 
  + Any operation that doesn't yield a meaningful result. 

```javascript
alert(1 / 0);               // Infinity
alert(Infinity);            // Infinity
alert('not a number' / 2);  // NaN
alert( NaN + 1);            // NaN
```

> **Note**: Mathematical operations are safe, we can do anything: divide by zero, treat non-numeric strings as numbers, etc. The script will never stop with a fatal error ("die"). At worst, we'll get `NaN` as the result.

2. **BigInt**
- `BigInt` type was recently added to the language to represent integers of arbitrary length. 

```javascript
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

> `BigInt` is supported in Firefox/Chrome/Edge/Safari, but not in IE. 

3. **Strings**

See also: [Strings](../Computer%20Science/General%20Knowledge.md#strings)

```javascript
"This is a string."
'Single quotation mark works, too.'
`Backticks works, too. They are also called "template literals."`
`You use backticks to embed values, such as ${variable} or ${100 / 2 + 5}.`
"backslash (\) is for escaping character.\nI open a new line here. Only the default console can express the opening up of a new line. For the DOM, you may need the <br> element."
"Escaping the escaping backslash character. Add another backslash like this \"\\n"\."
```
- Strings have to be modeled as a series of bits to be able to exist inside the computer. JS does this based on the Unicode Standard. This standard assigns a number to virtually every character you would ever need.
- Strings cannot be subtracted, multiplied or divided, but can be 'added' or 'concatenated' using the + operator. Be careful!

```javascript
console.log('con' + 'cat' + 'e' + 'nate' + '/nnewline'); 
/*
concatenate
newline
*/
```

- There is no *character* type in JS (like in C and Java with 'char' type). A string may consist of zero characters (be empty), one character or many of them. 

4. **Boolean (logical type)**
- Only two values: `true` or `false`.

```javascript
isEven(2);              // true
file.isChecked = true;  

let isGreater = 4 > 1;  // true
```

5. **The "null" value**
- The special `null` value does not belong to any of the types described above. It forms a separate type of its own which contains the `null` value:

```javascript
let age = null; // 'age' is unknown 
```

- `null` is not a 'reference to a non-existing object'or a 'null pointer' like in some other languages.
- It's just a special value which represents 'nothing', 'empty' or 'value unknown'. 

6. **The "undefined" value**
- The special value `undefined` also stands apart. It makes a type of its own, just like `null`. 
- The meaning of `undefined` is 'value is not assigned'.
- When a variable is declared, it is assigned `undefined` by default:

```javascript
let age;
console.log(age);     // shows 'undefined'

let name = undefined; // you can explicitly assign 'undefined' to a variable
```
- To refer to a variable as 'empty' or 'unknown', we should use `null` instead of explicitly assigning `undefined` to the variable. 
