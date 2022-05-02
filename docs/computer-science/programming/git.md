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

## 版本回退

最简单的方法

```bash
git reset --hard HEAD^ # 回退到上一个版本
git reset --hard HEAD~2 # 回退到前2个版本
```

查看 log，找到对应版本号，再回退

```bash
git log --pretty=format:'%h %ad %s' --graph --date=short
git reset --hard ef9e8b # 回退到 ef9e8b 版本
```