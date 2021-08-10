# Object.assign()

基本上就是把物件複製到 target，但要注意方式為 `Shallow Copy`（潛拷貝）

- 把後面的物件複製到前面的 target，重複的後面會蓋掉前面

```tsx
const obj = Object.assign({ foo: 0 }, { foo: 1 }, { foo: 2 });
console.log(obj); // { foo: 2 }
```

- 建構子中使用

```tsx
class A {
  name: string;
  age!: number;
  score!: number;
  constructor(b: B) {
    Object.assign(this, b); // B 的屬性會複製到 A
    this.name = "test";
  }
}

class B {
  age!: number;
  score!: number;
}

const b: B = { age: 27, score: 81 };
const a: A = new A(b);

console.log(a); // { age: 27, score: 81, name: 'test' }
```

- shadow copy

```tsx
// b 的 value 為 object，複製的是參考
let obj1 = {
  a: "a",
  b: {
    c: "c",
  },
};

let obj2 = Object.assign({}, obj1);
obj2.b.c = "ccc";

// 會跟著更動
console.log(obj1); // { a: 'a', b: { c: 'ccc' } }
```
