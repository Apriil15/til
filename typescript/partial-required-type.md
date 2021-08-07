# Partial / Required type

- Partial: 屬性都變成 `option`
- Required: 屬性都變成`必須`

```ts
type Student = {
  name?: string;
  age: number;
};
type PartialStudent = Partial<Student>;
type RequiredStudent = Required<Student>;

const student: Student = { age: 20 };
const partialStudent: PartialStudent = {};
const requiredStudent: RequiredStudent = { name: "Sam", age: 27 };
```
