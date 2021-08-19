# Promise

- Promise 的參數為一個 callback function
- Promise 後面可以接 `then`、`catch`、`finally`
- Promise.all / Promise.race 都是 concurrently 執行 Promise array

紀錄 Promise 寫法

```tsx
function run(name: string): Promise<string> {
  const random = Math.random() > 0.6;

  return new Promise((resolve, reject) => {
    if (random) {
      // 一段時間後得到結果
      setTimeout(() => {
        const result = `${name} ok`;
        resolve(result); // 會回傳 result
      }, 1000);
    } else {
      reject(new Error("error"));
    }
  });
}

run("Sam")
  .then((result) => {
    console.log(result); // Sam ok
  })
  .catch((err: Error) => {
    console.log(err);
  });
```
