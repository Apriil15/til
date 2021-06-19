# SELECT ... FOR UPDATE

主要情境用在：要對 SELECT 的資料進行 UPDATE

假設有兩個 processes:

- A process: SELECT 完，會進行 UPDATE
- B process: UPDATE

有可能在 A process SELECT 結束，尚未進行 UPDATE 的時候，B process 進行 UPDATE，這時候資料可能就會出現問題，因此這個語法會在 SELECT 完對那些資料 lock，在 UPDATE 完才會 unlock
