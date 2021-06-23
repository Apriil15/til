# TCP 與 UDP 的差異

- 皆屬於 OSI 的 `傳輸層`

# TCP

- Transmission Control Protocol
- 分三種狀態：

  - 連線（三次握手）

    A to B: 我要建立連線囉

    B to A: 好喔

    A to B: 知道了

    ![https://i.imgur.com/EkyjT1J.png](https://i.imgur.com/EkyjT1J.png)

  - 傳輸

    - 二次握手
    - 有兩種形式
    - 第一種：一去一回，沒回則重發

      ![https://i.imgur.com/Oys3mZ7.png](https://i.imgur.com/Oys3mZ7.png)

    - 第二種：一次發多個

      ![https://i.imgur.com/Vp8XQJr.png](https://i.imgur.com/Vp8XQJr.png)

  - 斷線（四次握手）

    A to B: 我要斷線囉（A 不再送訊息了，還是可以收訊息）

    B to A: 好喔

    B to A: 那我不回傳訊息囉

    A to B: 好喔（B 斷線）

    （大約 4 分鐘後正式斷線，資源釋放）

    ![https://i.imgur.com/xgPkRIw.png](https://i.imgur.com/xgPkRIw.png)

# UDP

- User Datagram Protocol
- 特性
  - 不可靠，射後不理，把資料傳過去就對了，有沒有拿到不重要
  - 到達順序可能不一致

![https://i.imgur.com/W8E1e2y.png](https://i.imgur.com/W8E1e2y.png)

# Reference

[30-11 之 TCP 與 UDP 協議 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10205476)
