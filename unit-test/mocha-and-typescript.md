# Mocha and TypeScript

- 安裝相關套件

```powershell
npm install --global mocha
npm install @types/mocha --save-dev

npm install chai --save-dev
npm install @types/chai --save-dev

npm install assert --save-dev
npm install @types/assert--save-dev
```

要測試的 code

- 路徑：index.ts

```tsx
export function sum(x: number, y: number): number {
  return x + y;
}
```

測試寫法

- 路徑：test/test.ts

```tsx
import { sum } from "../index";
import assert from "assert";
import * as chai from "chai";

describe("index.ts", () => {
  it("sum by assert", () => {
    assert.strictEqual(3, sum(1, 2));
  });

  it("sum by chai", () => {
    chai.expect(sum(2, 5)).to.equal(7);
  });
});
```

- package.json

```json
// scripts 加入
"test": "mocha --require ts-node/register test/*.ts"
```

最後以 `npm test` 執行

## Reference

[使用 TypeScript 撰寫 mocha 測試](https://medium.com/twelvefish/%E4%BD%BF%E7%94%A8-typescript-%E6%92%B0%E5%AF%AB-mocha%E6%B8%AC%E8%A9%A6-a4eda437fa53)

[Mocha - the fun, simple, flexible JavaScript test framework](https://mochajs.org/)
