# Pick 用法

- 從一個型別中`取出子集`當成一個型別
- 可以增加閱讀性

```tsx
type Info = {
  name: string;
  age: number;
  account: string;
  password: string;
  phoneNumber: string;
};

// 從 Info 裡面取出 password，phoneNumber 成為一個新的 type
type Secret = Pick<Info, "password" | "phoneNumber">;

const secret: Secret = {
  password: "password",
  phoneNumber: "0987654321",
};
```
