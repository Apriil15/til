# Commander.js

## 為什麼這學這個？

因為專案有用到，不學之後沒辦法改 XD

## Notes

- index.ts

  ```tsx
  import { Command } from "commander";

  const program = new Command();

  program.version("0.0.1");

  // $ npm run start -- say Sam 87 64 98
  // $ ts-node index.ts say Sam 87 64 98
  program
    .command("say <name> [scores...]")
    .description("say something")
    .alias("s")
    .action((name, scores) => {
      console.log(name);
      console.log(scores);
    });

  // $ npm run start -- --accountID 123987 --password 12354689
  // $ ts-node index.ts --accountID 123987 --password 12354689
  program
    .option("-a, --accountID <accountID>", "account id", "0")
    .option("-p, --password <password>", "password", "")
    .action((arg) => {
      console.log(arg); // { accountID: '123987', password: '12354689' }
      console.log("accountID: " + arg.accountID);
      console.log("password: " + arg.password);
    });

  program.parse(process.argv);
  ```

- package.json

  ```json
  {
    "name": "lab-commander",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
      "start": "ts-node index.ts"
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "dependencies": {
      "commander": "^8.1.0",
      "ts-node": "^10.2.0",
      "typescript": "^4.3.5"
    },
    "devDependencies": {
      "@types/node": "^16.6.1"
    }
  }
  ```

### Remark

如果用 npm 來操作指令，要加上 `--` 才能將 arg 傳進來

## 後記

原本先找 YouTube 看教學，好像版本太舊，照著做有問題，最後還是直接看 document

之前還在寫 Golang 時有想要學 [cobra](https://github.com/spf13/cobra)，這次剛好學到不同語言的解決方案

## Reference

[commander](https://www.npmjs.com/package/commander)
