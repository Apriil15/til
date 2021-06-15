# 什麼是 SOLID

- single responsibility principle

  修改一個類別只能有一個理由，一個類別不能包山包海

- open closed principle

  藉由寫新的 code 來新增功能，而不是去修改已經寫完的 code，擴充彈性才會好

- liskov substitution principle

  子類別要能夠轉型成父類別

- interface segregation principle

  介面不能太大。比如說有一個 interface 有 10 個方法，結果實現時只有用到 5 個方法，代表這個 interface 設計地不夠好

- dependency inversion principle

  類別要相依於抽象，例如 DI 的實踐方式
