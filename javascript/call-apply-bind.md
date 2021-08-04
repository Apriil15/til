# call / apply / bind

主要是針對 function 裡面的 this 做綁定

- call、apply 皆是回傳 function 執行結果
- bind 回傳的是綁定後的新 function

```tsx
// 宣告兩個物件
const objA = {
  name: "A",
};
const objB = {
  name: "B",
  writeName: function (age: number) {
    console.log(`${this.name}:${age}`);
  },
};

// 常見寫法
objB.writeName(17); // B:17

// writeName裡面的 this 為 objA
objB.writeName.call(objA, 19); // A:19

// apply 第二個參數為 array
objB.writeName.apply(objA, [20]); // A:20

// 把 objA 跟 22 綁到 writeName，並回傳一個 function
// 設定 this 為 objA，且多傳入一個參數，所以呼叫時沒辦法再傳參數
const func = objB.writeName.bind(objA, 22);
func(); // A:22

// 只綁定 this 不綁定其他參數，呼叫的時候再給
const func1 = objB.writeName.bind(objA);
func1(24); // A:24
```

## Reference

[[筆記][JavaScript]使用 call()、apply()、bind()設定函式中的「this」 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10198035)
