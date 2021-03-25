---
title: git拉取远程分支到本地
date: 2021-03-24T16:00:00Z
tags:
- git
categories: ''

---

> 参考： https://blog.csdn.net/carfge/article/details/79691360

首先，进入本地仓库

1. 将本地仓库与远程仓库建立链接

```
git remote add origin git@github.com:user/repo.git
```

2. 远程分支拉取到本地

```
git fetch origin dev-op(远程分支名称)
```

3. 在本地创建新分支dev并切换到该分支

```
git checkout -b dev-op(本地分支名称) origin/dev-op(远程分支名称)
```

4. 把远程分支dev-op上的内容拉取到本地仓库

```
git pull origin dev-op(远程分支名称)
```