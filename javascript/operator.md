# 運算子

## Optional chaining operator: `?.`

理想上要是這樣

```jsx
const response = {
  rows: [
    {
      name: "John",
    },
  ],
};

if (response.rows[0].name === "John") {
  console.log("Get John");
}
```

但實際上可能會是這樣，會報錯

`TypeError: Cannot read property 'name' of undefined`

```jsx
const response = {
  rows: [],
};

// response.rows[0] 為 undefined
if (response.rows[0].name === "John") {
  console.log("Get John");
}
```

可以這樣做處理，一層一層判斷

```jsx
const response = {
  rows: [],
};

// 先判斷 response.rows[0] 存不存在，存在再繼續判斷
if (response.rows[0] && response.rows[0].name === "John") {
  console.log("Get John");
} else {
  console.log("it is ok");
}
```

但如果物件有多層巢狀估計會被搞死 XD

因此要這樣寫！！！

```jsx
const response = {
  rows: [],
};

// 有 rows 再找 [0] 再找 name，只要有沒找到就回傳 undefined
if (response.rows?.[0]?.name === "John") {
  console.log("Get John");
} else {
  console.log("it is ok");
}
```

## ||

- return 第一個 `true`，沒有則 return 最後一個
- `null`、`undefined`、`0`、`""` → 這些都是 `false`

```jsx
console.log(null || undefined || "" || 12); // 12
console.log(null || undefined || 0 || undefined); // undefined
```

## ??

- return 第一個 `defined`（非 null / undefined），沒有則 return 最後一個

```jsx
// 要看情境去思考要用哪個
console.log(0 ?? 12); // 0
console.log(0 || 12); // 12

console.log(undefined ?? null); // null
```

## &&

- return 第一個 `false`，沒有則 return 最後一個

```jsx
console.log(1 && 2 && null && 4); // null
console.log(1 && 2 && 3 && undefined); // undefined
```

## Reference

[Week8 - 不想再看到 undefined 的 TypeError 嗎，你可以試看看 JS 的 Optional chaining operator [Server 的終局之戰系列] - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10230756)
