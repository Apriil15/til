# 刪掉 remote 已經刪掉的 local branch

通常實作一個 feature 或修 bug 都會開一個 branch，push 到 remote 接著被 merge，時間一拉長這些 branch 留在 local 就會顯得有點亂，這時可以善用 `prune` 指令來清理

- 顯示 local 這邊在 remote 已經刪掉的 branch

```bash
git remote prune origin --dry-run
```

- 刪掉 local 這邊在 remote 已經刪掉的 branch

```bash
git remote prune origin
```
