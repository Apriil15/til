# 如何使用 Array 的 filter / find / map / reduce

以下使用 TypeScript，但基本上都一樣。

- filter: 符合的都回傳

```tsx
const numbers: number[] = [1, 2, 3, 4, 5];

const result: number[] = numbers.filter((number) => number > 3);

console.log(result); // 4 5
```

- find: 回傳符合的第一個

  都不符合會回傳 undefined

```tsx
const numbers: number[] = [1, 2, 3, 4, 5];

const result: number | undefined = numbers.find((number) => number > 3);

console.log(result); // 4
```

- map: 傳一個 function 進去，並透過回傳的值，回傳新的陣列

```tsx
const numbers: number[] = [1, 2, 3, 4, 5];

const result = numbers.map((number) => number * 2);

console.log(result); // [ 2, 4, 6, 8, 10 ]
console.log(numbers); // [ 1, 2, 3, 4, 5 ] 原本的 array 不會改變
```

- reduce

  第一個參數傳一個 function，這邊為累加

  第二個參數為初始值 (可不寫，初始值會變成 array 的第一個值)

```tsx
const numbers: number[] = [1, 2, 3, 4, 5];

// 10 + 1 + 2 + 3 + 4 + 5
const result: number = numbers.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  10
);

console.log(result); // 25
```
