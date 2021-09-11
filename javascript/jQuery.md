# jQuery

- 要把 jQuery loading 進來

  可以用 CDN 的方式：[https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js](https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js)

- 主要用 `selector` 來做 query

```tsx
<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
  </head>
  <body>
    <p id="test">Hello live</p>

    <script src="./dist/index.js"></script>
  </body>
</html>
```

- index.js

```tsx
const result = $("#test").html();

console.log(result); // Hello live
```
