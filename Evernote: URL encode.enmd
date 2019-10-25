---
title: URL encode
tags: []
notebook: luolisheng 的笔记本
---

### 
1. 非法字符在不同的操作系统有不同的解析，规定使用percent encode编码，对非法字符的编码结果为三个字节（%+16进制字符*2）
2. percent编码是在对非法字符采用某种编码（约定为UTF8）字符流转成字节流后，逐字节加上%构成percent编码
3. 使用NSURLComponents拼装URL，设置NSURLQueryItem参数时候不需要自己做encode；同时queryItems时也不需要自己decode

### 参考
1. [link1](http://www.cnblogs.com/hushuai-ios/p/5500162.html)
2. [link2](https://juejin.im/post/5b2b22ad51882574ab71d6ec)
