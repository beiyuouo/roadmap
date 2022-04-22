# Git

速记一下 Git 的常用指令

## 快速删库跑路

```bash
git checkout --orphan new

git add -A
git commit -am "Initial commit"

git branch -D main
git branch -m main

set https_proxy=127.0.0.1:10809
set http_proxy=127.0.0.1:10809

git push origin main --force
```
