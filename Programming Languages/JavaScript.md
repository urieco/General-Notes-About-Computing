# Table of Contents
[How to run JS code](#how-to-run-js-code)
[How to add JS code](#how-to-add-js-code)

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
