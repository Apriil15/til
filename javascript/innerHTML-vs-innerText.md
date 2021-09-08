# innerHTML vs innerText

- innerHTML

  會包括裡面的 HTML element

- innerText

  只會有 text

```html
<!DOCTYPE html>
<html lang="en">
  <head> </head>
  <body>
    <p id="paragraph">Hello <strong>world!</strong></p>

    <script src="./src/index.js"></script>
  </body>
</html>
```

./src/index.js

```jsx
const result = document.getElementById("paragraph");

console.log(result.innerHTML); // Hello <strong>world!</strong>
console.log(result.innerText); // Hello world!
```
