# appendChild 使用

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
    <div id="div1">
      <p>Hello live</p>
    </div>

    <br />

    <p id="p1">Hello liveII</p>

    <button onclick="change()">button</button>

    <script src="./src/index.js"></script>
  </body>
</html>
```

畫面如圖：

![https://i.imgur.com/pGSNAea.png](https://i.imgur.com/pGSNAea.png)

---

1. 點擊後，`Hello liveII` 被移到上面了

   appendChild 其實就是把一個 node 移到某個父節點下

```jsx
const div = document.getElementById("p1");

function change() {
  document.getElementById("div1").appendChild(div);
}
```

![https://i.imgur.com/1SRvRTG.png](https://i.imgur.com/1SRvRTG.png)

---

2. 如果想保留原來的節點可以使用 `cloneNode`

   但是一直點擊按鈕，會發現只有第一次有用。因為已經把它移到父節點下了，後續的點擊只是一直把 `Hello liveII` 移到相同的位置，所以視覺上沒效果

```jsx
const div = document.getElementById("p1").cloneNode(true);

function change() {
  document.getElementById("div1").appendChild(div);
}
```

![https://i.imgur.com/e1xcg5b.png](https://i.imgur.com/e1xcg5b.png)

---

3. 想要一直點擊按鈕有效果的話，就要移到 function 內。這樣每次都會 clone 一份新的，然後 append 到父節點內

```jsx
function change() {
  const div = document.getElementById("p1").cloneNode(true);
  document.getElementById("div1").appendChild(div);
}
```

![https://i.imgur.com/PbUPG4c.png](https://i.imgur.com/PbUPG4c.png)
