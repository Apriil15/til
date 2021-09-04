# BOM

- 確認 window 是否關閉

  ```jsx
  if (window.closed) {
    // do something
  } else {
    // do something
  }
  ```

- 上一頁、下一頁

  ```jsx
  window.history.back();
  window.history.forward();
  ```

- 目前可用寬度、高度

  ```jsx
  window.innerWidth;
  window.innerHeight; // (不包括工具列)
  ```

- 跳出引導列印頁面

  ```jsx
  print();
  ```

## 視窗

- 打開新視窗

  ```jsx
  // 打開新視窗
  open();

  // 打開新視窗並到特定 URL
  open("https://www.google.com/");
  ```

- 關閉視窗 (只適用於新開的視窗)

  ```jsx
  close();
  ```

## 彈出視窗

- 彈出視窗

  ```jsx
  alert("Hello world!");
  ```

- 彈出視窗 (有`確定`、`取消`)

  ```jsx
  const answer = confirm("Hello world");

  if (answer === true) {
    // do something
  } else {
    // do something
  }
  ```
