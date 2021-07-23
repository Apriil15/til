# == vs ===

== (double equals)

- 會先轉成同型別，再比較值
- 空字串會轉成 0
- 非數字的字串會轉成 NaN (Not a Number)

=== (triple equals)

- 確認 value & type

案例：

```jsx
console.log(0 == ""); // true ('' 會轉成 0)
console.log(1 == "1"); // true

console.log(1 === "1"); // false
```
