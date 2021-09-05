# Web 中使用 JS 的方式

- 加入 `script` 就可以寫 JS 惹
- 可以直接在 script 裡面寫，或是用 `src`
- body 中的 script 一般會寫在 `</body>` 之前，這樣才不會找不到 element

Example

```jsx
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Document</title>

    <script>
      console.log('head')
    </script>
  </head>
  <body>
    <p>Hello world</p>

    <script src="./src/index.js"></script>
    <script>
      console.log('body')
    </script>
  </body>
</html>
```

- ./src/index.js

```jsx
const result = document.querySelector("p").textContent;
console.log(result);
```
