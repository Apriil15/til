# Never

用途：

1. 無窮迴圈

```tsx
function infiniteLoop(num: number): never {
  while (true) {
    console.log(num);
  }
}
```

2. throw exception

```tsx
function generateError(message: string): never {
  throw new Error(message);
}
```
