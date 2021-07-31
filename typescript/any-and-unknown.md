# Any & Unknown

相同地方：

- 都可以接受任意型別

不同地方：

- any 可以 assign 給任何型別
- unknown 只能 assign 給 any or unknown
- any 可以任意操作屬性 or 方法
- unknown 要執行`型別斷言`或`型別檢查`才能操作屬性 or 方法且通過編譯

## Any

- any 可以被 assign 任意型別

```tsx
// any 可以被 assign 任意型別
let a: any = "test";
console.log(a);

a = 87;
console.log(a);

a = true;
console.log(a);
```

- 宣告時不指定型別，就會是 any

```tsx
// 等同於 let something: any;
let something;

something = true;
console.log(something);

something = 98;
console.log(something);
```

- any 的問題

```tsx
let a: any = 19;

let str: string = a;

// 編譯時期沒事，但執行時期會錯
console.log(str.toLowerCase());
```

## Unknown

- 只能 assign 給 `unknown` or `any`

```tsx
let a: unknown = 19;

// assign 給 unknown & any
let b: unknown = a;
let c: any = a;

// 會報錯!!
let str: string = a;
```

- 沒有推斷是什麼型別之前，禁止操作屬性與方法

```tsx
let a: unknown = "123";

if (typeof a === "string") {
  console.log(a.toUpperCase()); // 推斷後可以用方法
}
```
