# Pick & Record

## Pick

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

## Record

- 將兩個 type 組成一個分別是 key，value 的新 type

```tsx
type CatName = "A" | "B" | "C";

type CatInfo = {
  age: number;
  breed: string;
};

// Record<CatName, CatInfo> 是一個物件
// key 是 CatName，value 是 CatInfo
const cats: Record<CatName, CatInfo> = {
  A: { age: 5, breed: "AAA" },
  B: { age: 10, breed: "BBB" },
  C: { age: 15, breed: "CCC" },
};
```
