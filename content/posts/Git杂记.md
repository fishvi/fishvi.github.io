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
