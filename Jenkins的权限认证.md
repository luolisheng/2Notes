---
title: Jenkins的权限认证
tags: 
notebook: luolisheng 的笔记本
---

```
// 可查看终端里用户
dscacheutil -q group

ssh -vT git@source.enncloud.cn:iComeTeam/iComeKernelIOS.git
ssh -vv git@source.enncloud.cn

```

### 安装

1. 直接下载安装Jenkins
    1. 会创建jenkins用户: /User/Shared/jenkins
    2. 会在jenkins用户下运行，导致很多权限问题

2. 使用homebrew安装
    1. 会在当前用户目录下生成一个.jenkins文件夹:~/.jenkins/
    2. 所有任务和工作空间都在该文件夹下，没有权限问题

### 参考

1. [link1](https://blog.51cto.com/wzlinux/2160109)
2. [安装](https://www.zhaolong.net.cn/2020/05/14/Server-2020-05-14-Mac-%E4%BF%AE%E6%94%B9-Jenkins-%E8%BF%9B%E7%A8%8B%E9%BB%98%E8%AE%A4%E7%94%A8%E6%88%B7%E8%A7%A3%E5%86%B3%E6%9D%83%E9%99%90%E9%97%AE%E9%A2%98/)
3. [安装](https://vic.kim/2019/05/21/Mac%E4%B8%8BJenkins%E6%90%AD%E5%BB%BA/)
