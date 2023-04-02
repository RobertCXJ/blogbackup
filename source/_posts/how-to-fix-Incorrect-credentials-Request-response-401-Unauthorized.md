---
title: how to fix Incorrect credentials. Request response. 401 Unauthorized
tags: [debug,git]
date: 2023-03-23 23:01:22
updated: 2023-03-23 23:01:22
categories: 
- debug
---

使用GitHub生成的token登录idea时，无法登录，报了如标题错误

<!--more-->

这是因为生成token时未勾选相应的权限

请务必勾选以下权限

```
repo - select everything
gist - select everything
org - select only read:org
```

勾选以后即可使用GitHub登录idea了
