# Object.entries()

- 會取得二維的 array，裡面的 array 會是物件的 key、value
- 可以搭配 `map` 方法，來轉成物件

```tsx
const obj = {
  A: 12,
  B: 34,
  C: 56,
  D: 78,
};

console.log(Object.entries(obj));
// [ [ 'A', 12 ], [ 'B', 34 ], [ 'C', 45 ], [ 'D', 67 ] ]

// entries 搭配 map 轉成物件
const transformObj = Object.entries(obj).map(([key, value]) => {
  return { name: key, age: value };
});

console.log(transformObj);
// [
//   { name: 'A', age: 12 },
//   { name: 'B', age: 34 },
//   { name: 'C', age: 45 },
//   { name: 'D', age: 67 }
// ]
```
