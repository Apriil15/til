# CSRF 概念

- cross site request forgery 跨站請求偽造
- 因為 http 的 stateless 特性，再加上人類的惰性使然，產生了 cookie & session，攻擊者依循這個脈絡，又產生 CSRF 攻擊

CSRF 例子：
假設我們登入 A 網站後，利用 cookie 或 session，不用每次都再重新驗證。但逛 B 網站時，偷偷複製了你的 cookie，然後就可以用這個 cookie 打 A 網站的 API 做壞事。

怎麼防範：

1. 檢查 http referer 欄位
   - http 有 referer 欄位，紀錄 request 從哪裡來，只要不是 A 網站來的，一概不受理
   - 但這方法還是有被偽造的風險
2. CSRF token
3. 加上圖形驗證碼、簡訊驗證碼

## Reference

例子蠻不錯的

[CSRF 攻擊原理](https://medium.com/@Tommmmm/csrf-%E6%94%BB%E6%93%8A%E5%8E%9F%E7%90%86-d0f2a51810ca)
