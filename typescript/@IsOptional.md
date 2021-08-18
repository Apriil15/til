# @IsOptional()

今天在找驗證錯誤的 bug，發現有點誤解 `IsOptional` 的用法，看 code 的註解還是不太懂，`missing` 到底是指什麼

- source code 的註解

```tsx
import { ValidationOptions } from "../ValidationOptions";
/**
 * Checks if value is missing and if so, ignores all validators.
 */
export declare function IsOptional(
  validationOptions?: ValidationOptions
): PropertyDecorator;
```

看官方的文件才發現，有種想發個 PR 的衝動 XDD

- Checks if given value is empty (`=== null, === undefined`) and if so, ignores all the validators on the property.

測試範例

```tsx
import { IsNumber, IsOptional, validateSync } from "class-validator";

class SomeClass {
  @IsOptional() // 如果 value 是 null / undefined -> 就不驗證
  @IsNumber({ allowNaN: false })
  something: number | null;

  constructor(something?: number | null) {
    this.something = something ?? null;
  }
}

const a = new SomeClass(); // something 為 null -> 不驗證
console.log(validateSync(a).length); // 0

const b = new SomeClass(NaN); // something 為 NaN -> 會驗證 -> 驗證沒過
console.log(validateSync(b).length); // 1
```
