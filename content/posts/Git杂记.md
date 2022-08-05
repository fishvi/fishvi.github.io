---
title: "Git杂记"
date: 2022-07-27T19:03:16-07:00
draft: false
---
## Git配置
初始配置
```
git config --global user.name [name]
git config --global user.email [email]
```

查看配置
```
git config --global --list
```

## 克隆仓库
```
git clone [repository-url]
```

## 远程仓库
添加远程仓库
```
git remote add [name] [repository-url]
```

查看远程仓库信息
```
git remote -v
```

## 提交改动文件至暂存区
改动文件包括：增加、修改、删除的文件
```
git add --all
```

## 撤销
撤销并删除当前的所有更改，包括已经add的
```
git reset --hard
git clean -df
```

撤销已经push到远程仓库的提交, commit是所要撤销的commit的**上一个commit**
```
git log
git reset --soft [commit]
git push origin main --force
```

## 修改commit信息
修改最近一次commit信息
```
git commit --amend
git commit --amend --author="[name] <[email]>"
git push origin main --force
```

修改某几次commit信息, commit是所要更改的commit的**上一个commit**, 会进入到编辑窗口, 将所要更改的commit前的pick更改为edit，保存并退出，然后按照提示依次进行每一个commit的更改操作
```
git rebase -i [commit]
...
git commit --amend
git commit --amend --author="[name] <[email]>"
git rebase --continue
...
git push origin main --force
```

修改第一次commit信息, 无法通过前述方法进行重设，**只能清空所有commit**, 再重新提交第一次commit
```
git update-ref -d HEAD
```