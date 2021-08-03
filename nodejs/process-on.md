# 監聽事件 process.on

- 用 `process.on` 註冊監聽事件，當事件發生會執行註冊的 callback

```tsx
process.on("exit", () => {
  // write your logic when exit
  console.log("exit");
});

process.on("uncaughtException", (err) => {
  // error handler
  console.log(err.message);
});

console.log("start");

throw new Error("hi i'm an Error");
```
