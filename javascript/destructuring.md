# Destructuring 解構

- 把 value 從 `array` 或 `object` 拿出來，然後 assign 給變數
- 算是一種精簡的寫法

---

- Array

  - 基本用法

  ```tsx
  let foo = ["one", "two", "three"];

  // 從 array 中提取值，然後按照對應的位置，指定給相應的變數
  let [first, second, third] = foo;

  console.log(first); // "one"
  console.log(second); // "two"
  console.log(third); // "three"
  ```

  - 可以跳過

  ```tsx
  let foo = ["one", "two", "three"];

  let [first, , third] = foo;

  console.log(first); // "one"
  console.log(third); // "three"
  ```

  - 搭配 spread operator

  ```tsx
  let foo = ["one", "two", "three"];

  let [, ...test] = foo;
  console.log(test); // [ 'two', 'three' ]
  ```

- Object

  - 基本用法

  ```tsx
  let restaurant = {
    name: "那一天義法餐館",
    chef: "阿華師",
    menu: {
      duck: "法式櫻桃鴨胸",
      pig: "噶瑪蘭黑豚",
      rice: "檸檬奶油煙燻鮭魚燉飯",
    },
  };

  // 以前的寫法
  // let name = restaurant.name;
  // let chef = restaurant.chef;

  // 解構賦值的寫法
  let { name, chef } = restaurant;
  console.log(name); // 那一天義法餐館
  console.log(chef); // 阿華師
  ```

  - 重新賦予變數的名稱

  ```tsx
  let restaurant = {
    name: "那一天義法餐館",
    chef: "阿華師",
    menu: {
      duck: "法式櫻桃鴨胸",
      pig: "噶瑪蘭黑豚",
      rice: "檸檬奶油煙燻鮭魚燉飯",
    },
  };

  let { name, chef: bestChef } = restaurant;
  console.log(name); // 那一天義法餐館
  console.log(bestChef); // 阿華師
  ```

  - 當作參數傳進 function

  ```tsx
  function love({ a = "沒有人", b = "你" }) {
    console.log(`${a} 愛 ${b}`);
  }

  love({ a: "我", b: "睡覺" }); // 我 愛 睡覺
  love({}); // 沒有人 愛 你
  love({ b: "工作" }); // 沒有人 愛 工作
  love({ b: "世界紅茶", a: "我" }); // 我 愛 世界紅茶
  love({}); // 沒有人 愛 你
  ```

  - 搭配 rest operator

  ```tsx
  const student = {
    name: "Sam",
    age: 12,
    score: 66,
  };
  const { name, ...restObj } = student;
  console.log(name); // Sam
  console.log(restObj); // { age: 12, score: 66 }
  ```

## Reference

[Day10【ES6 小筆記】物件的解構賦值-以一間好吃的餐廳為例（Object Destructuring） - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10214721)
