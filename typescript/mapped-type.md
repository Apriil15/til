# Mapped Type

## Index Signatures Type

```tsx
type Student = {
  // key 只是一個變數名稱，可以自己命名
  [key: string]: string;
};

// 可以是任意
const s1: Student = {
  firstName: "Sam",
};
const s2: Student = {
  lastName: "Wang",
};
```

## Mapped Type

- `[property in ...]` 可以想成 `for ... of`

```tsx
// 兩者效果相同
type Student1 = {
  firstName: string;
  lastName: string;
};
type Student2 = {
  // key 只是一個變數名稱，可以自己命名
  // key 會被限定在定義範圍
  [key in "firstName" | "lastName"]: string;
};

const s2: Student2 = {
  firstName: "Sam",
  lastName: "Wang",
};
```

- `keyof` 就是把物件的 key 取出來

```tsx
type Student = {
  age: number;
  name: string;
};

type StudentMethod = {
  [key in keyof Student]: () => void;
  // 等同此寫法，優點是哪天 Student 屬性修改了，這邊如果沒跟著改，就會 error 提醒
  // age: () => void
  // name: () => void
};

const studentMethod: StudentMethod = {
  age: () => {},
  name: () => {},
};
```

- 也可以把 key 當 value

```tsx
type Student = {
  age: number;
  name: string;
};

type StudentKeyMap = {
  [key in keyof Student]: key;
};
// 等同此寫法
type StudentKeyMap2 = {
  age: "age";
  name: "name";
};
```

- 搭配 `as` 來自定義 key name

```tsx
type Student = {
  age: number;
  name: string;
};

type StudentMethod = {
  // Capitalize 轉成大寫
  [key in keyof Student as `set${Capitalize<key>}`]: () => void;
};

const studentMethod: StudentMethod = {
  setAge: () => {},
  setName: () => {},
};

// 改寫法的話
// [key in keyof Student as `set${key}`]: () => void
// key 會變成這樣 setage, setname
```

## Reference

[認識 TypeScript 中的型別魔術師：Mapped Type](https://pjchender.blogspot.com/2021/08/typescript-mapped-type.html)
