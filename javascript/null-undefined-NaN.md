# null / undefined / NaN

null

- 空值
- type 為 object
- 是一個有效的 JSON

undefined

- 沒這個變數，或是變數沒 assign
- type 為 undefined

NaN

- Not a Number
- type 為 number

共同點

- null / undefined / NaN 在判斷式裡都是 `false`

範例

```tsx
console.log(typeof null); // object
console.log(typeof undefined); // undefined
console.log(typeof NaN); // number

console.log(NaN + 19); // NaN
console.log(typeof (NaN + 19)); // number

console.log(NaN + "123"); // NaN123
console.log(typeof (NaN + "123")); // string
```
