# Table of Contents
- [What is JS?](#what-is-js)
- [How to run JS code](#how-to-run-js-code)
- [How to add JS code](#how-to-add-js-code)
- [Values, Types and Operators](#values-types-and-operators)

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

# Values, Types and Operators
- [Values](../Computer%20Science/General%20Knowledge.md#values) (from CS/'General Knowledge'.md).

## Types
1. **Numbers**

See also: [Numbers](../Computer%20Science/General%20Knowledge.md#Numbers)

- Numeric values
- JS uses a fixed number of bits, 64 of them, to store a single number value. There are so many patterns you can make with **64 bits**, which means that number of different numbers that can be represented is **limited**. --> You can represent 2<sup>64</sup> different integers (whole numbers) (due to how common 64-bit architecture CPUs are).
- However, some bits are delegated to indicate **the sign of the number and the position of the decimal point**. You can only store 2<sup>53</sup> numbers (9 quadrillion - 10<sup>15</sup>).
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

2. **Strings**

Ref: [Strings](../Computer%20Science/General%20Knowledge.md#strings)

```javascript
"This is a string."
'Single quotation mark works, too.'
`Backticks works, too. They are also called "template literals."`
`You use backticks to embed values, such as ${variable} or ${100 / 2 + 5}.`
"backslash (\) is for escaping character.\nI open a new line here. Only the default console can express the opening up of a new line. For the DOM, you may need the <br> element."
"Escaping the escaping backslash character. Add another backslash like this \"\\n"\."
```
- Strings have to be modeled as a series of bits to be able to exist inside the computer. JS does this based on the Unicode Standard. This standard assigns a number to virtually every character you would ever need 