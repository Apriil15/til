# HTTP & Socket & WebSocket

## HTTP

- 非持久化、單向
- 建立連線後只允許瀏覽器向伺服器 request 後，伺服器才能 response
- 想要即時通訊時，需要靠`輪詢`在特定的時間間隔（如 1 秒），不斷由瀏覽器向伺服器傳送 request
- HTTP request 的 header 很長，為了傳輸一個很小的資料，需要付出巨大的代價

## Socket

- 是應用層與 TCP / IP 協議族通訊的中間軟體抽象層，它是應用層跟傳輸層之間的一組介面，把複雜的 TCP / IP 協議族封裝在裡面
- 利用 TCP / IP 協議建立 TCP 連線
- 任何一個 Socket 都給予一個特殊號碼（IP number + TCP port），使用者之間只要記住對方的 Socket 號碼，便可以直接通訊

## WebSocket

- 目的：即時通訊、替代輪詢
- 應用層協議，基於 TCP
- 建立握手時，通過 HTTP 傳輸，建立之後不用
- 雙向通訊，模擬 Socket 協議
