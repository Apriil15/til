# DOM

learn some basic DOM

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <p id="test1">paragraph</p>

    <p class="test2">t1</p>
    <p class="test2">t2</p>
    <p class="test2">t3</p>

    <script src="./src/index.js"></script>
  </body>
</html>
```

- ./src/index.js

```jsx
// getElementById
console.log(document.getElementById("test1").innerText); // paragraph

// getElementsByClassName 會拿到 array
const result = document.getElementsByClassName("test2");
for (const item of result) {
  console.log(item.innerText); // t1 t2 t3
}

// document.body
document.body.style.color = "green";

// createElement, createTextNode, appendChild
const newParagraph = document.createElement("p");
const text = document.createTextNode("i have a pen");
newParagraph.appendChild(text);

document.body.appendChild(newParagraph);
```
