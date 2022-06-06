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

最简单的方法，reset，一共有三种：

- `git reset --hard`：将当前分支的 HEAD 指向某个指定的 commit，并且将当前分支的工作目录恢复到该 commit 的状态，并且把当前分支的所有未提交的修改撤销。
- `git reset --soft`：将当前分支的 HEAD 指向某个指定的 commit，并且将当前分支的工作目录恢复到该 commit 的状态，但是不撤销未提交的修改。
- `git reset --mixed`：将当前分支的 HEAD 指向某个指定的 commit，并且将当前分支的工作目录恢复到该 commit 的状态，但是不撤销未提交的修改，同时也不撤销当前分支的工作目录中的文件。

默认是 `--mixed` 模式

```bash
git reset --hard HEAD^ # 回退到上一个版本，并且撤销未提交的修改
git reset --hard HEAD~2 # 回退到前2个版本，并且撤销未提交的修改
```

查看 log，找到对应版本号，再回退

```bash
git log --pretty=format:'%h %ad %s' --graph --date=short
git reset --hard ef9e8b # 回退到 ef9e8b 版本
```

恢复 reset

```bash
git reflog # 查看 reflog 就可以知道回退版本的 commit id
git reset --hard "" # 恢复到指定的版本
```
