# SQL Injection 概念

## 何謂 SQL Injection

用戶輸入的參數，意外變成 SQL 語法被使用

## 如何防止 SQL Injection

1. Prepared Statement

   db server 不會將參數當作 SQL 語法使用，會在編譯後，才去套用參數並執行

2. 參數化查詢

   C# 可以用 `Parameters`
