# 用 VS Code 來 debug

- `tsconfig.json` 新增以下參數

  ```json
  {
    "compilerOptions": {
      "outDir": "./dist",
      "rootDir": "./src",
      "sourceMap": true,
      "moduleResolution": "node"
    }
  }
  ```

  編譯 `rootDir` 到 `outDir`

- `package.json` 新增以下參數

  ```json
  "build": "tsc"
  ```

- .vscode 資料夾裡面的 `launch.json` 新增以下參數

  preLaunchTask: 呼叫 package.json 的 build

  ```json
  "sourceMaps": true,
  "preLaunchTask": "npm: build",
  ```

## Reference

[How to debug TypeScript with VS Code](https://pkief.medium.com/how-to-debug-typescript-with-vs-code-9cec93b4ae56)
