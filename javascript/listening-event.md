# 監聽事件

- 滑鼠

  - onclick: 左鍵點擊
  - ondbclick: 左鍵連點
  - onmousedown: 左鍵 or 右鍵點擊
  - onmouseover: 滑鼠移入 element 時
  - onmouseout: 滑鼠從 element 移出時

- 鍵盤

  - onkeydown: 用在偵測目前按的是哪個鍵
  - onkeypress: 任一鍵被按下（無法適用所有按鍵），如果要監聽按下鍵盤用 `onkeydown` 即可
  - onkeyup: 放開任何一鍵

- 視窗

  一般會寫在 `<body>` 內

  - onerror: loading 檔案 or 圖片錯誤時
  - onload: 畫面 loading 完時
  - onscroll: 捲動畫面時
  - onresize: 視窗大小改變時

- 表單

  - onselect: 選取區塊內文字時
  - onchange: 改變區塊內內容，且離開區塊時
  - onfocus: 滑鼠移進區塊時
  - onblur: 滑鼠離開區塊時
  - onsubmit: 點擊提交時
