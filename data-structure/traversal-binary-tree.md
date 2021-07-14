# 遍歷 Binary Tree

三種方式：pre-order、in-order、post-order，都是以 parent node 相對於 child node 的順序

```
   4
  ／＼
 2    6
／＼ ／＼
1  3 5  7
```

- pre-order: 中 → 左 → 右，4213657
- in-order: 左 → 中 → 右，1234567
- post-order: 左 → 右 → 中，1325764
