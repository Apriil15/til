# 設定 JS、TS 方法的括號自動補齊

原本的自動補齊要再自己加括號

![](https://i.imgur.com/djB9YyI.png)

解決辦法：

`ctrl + shift + p` 輸入 `settings.json` 打開設定檔，並加入以下參數

```json
"javascript.suggest.completeFunctionCalls": true,
"typescript.suggest.completeFunctionCalls": true
```

或是打開 VS code 的設定，輸入 `suggest.completeFunctionCalls`，將選項打勾

![](https://i.imgur.com/XHVNQui.png)

就會自動補齊括號惹！

![](https://i.imgur.com/teIu4g8.png)
