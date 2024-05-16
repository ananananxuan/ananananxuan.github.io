---
layout: mypost
title: git bash ssh
categories: [小技巧]
---

ssh
1. 定义
- 计算机加密登陆的协议
- 使用非对称密钥实现身份认证


2. 作用
- 一般用于远程加密登陆认证
- 当远程机器拥有公钥，本地持有私钥，登陆就不用输入密码

3. 配置ssh
- 检查已有密钥
```
$ cd ~/.ssh
$ ls
```
- 生成密钥,可以将其复制到github设置中的ssh
```
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```
- 复制公钥到远程机器
```
$ ssh-copy-id -i ~/.ssh/id_25519.pub user@host
```
- 测试 
```
$ ssh user@host
```
   
`