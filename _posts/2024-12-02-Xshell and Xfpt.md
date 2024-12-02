---
layout: mypost
title: Xshell and Xftp
categories: [小技巧]
---

learning resource: 
https://www.bilibili.com/video/BV1AS411A7aF?spm_id_from=333.788.recommend_more_video.0&vd_source=917336f407022762079ae1d9a0b669fd

购买阿里云服务器会得到ip地址，用户名，密码三个内容


利用Xshell 来远程登陆一个服务器

1. Download two application from official website 

2. Open Xshell, new, 

名称：写服务器的名字，可以自己起（如果是自己购买的话）
主机：填写相应的ip地址
端口号：22（链接服务器的端口一般都是22）
请输入登陆的用户名：root（阿里云服务器，课题组的服务器是什么就填什么名）
密码：

3. root用户给自己开通一个普通账号
sudo useradd -m anxuan -d /home/anxuan -s /bin/bash
sudo passwd anxuan 
设置自己的密码
确认自己的密码

4. 用普通账户再登陆自己的Xshell
名称：阿里云anxuan
主机：填写相应的ip地址
端口号：22（链接服务器的端口一般都是22）
请输入登陆的用户名：anxuan
密码：自己设置的密码


Xshell的使用
通过使用Linux的基本命令：命令 + 参数
ls 查看当前目录下的文件
ls -lht

rm 删除
rm 文件名

less查看文件内容
less 文件名
less -N 文件名  可以查看行号
退出按Q键

mkdir新建文件夹
mkdir 文件夹名
mkdir -p A/a 再A文件夹下创建a文件

pwd 显示当前完整的路径
cd 进入文件夹
cd ~ 进入起始文件夹
cd ../ 返回上一层文件夹中

bash 安装软件
bash 文件名

