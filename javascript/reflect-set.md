# Reflect.set()

- 專案有這寫法，紀錄用

readonly 的屬性在建構子時可以設定，其他時候是不能修改的

但可以用 `Reflect.set()` 來修改

```tsx
class Student {
  readonly name!: string;

  constructor(name: string) {
    this.name = name;
  }

  // 要對 readonly 的屬性作改變可以這樣處理
  setName(name: string) {
    Reflect.set(this, "name", name);
  }
}

const student = new Student("Sam");
student.setName("Kappa");
console.log(student);
```
