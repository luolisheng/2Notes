---
title: Swift和Objective混编
tags: ["iOS"]
notebook: iOS
---

### 混编方式

1. OC项目中引入Swift源码

2. OC项目中引入Swift动态framework(只测试了纯Swift编码的framework)
	* Always Embed Swift Standard Libraries设为YES
	* 动态的framework要放在Embedded Binaries下
	* Apple目前不允许开发者构建内含Swift代码的静态库，所以要往OC项目中集成第三方Swift代码的时候就只能通过动态框架framework的形式了

3. Swift类要继承自NSObject并生成.h文件给OC项目使用。

#### 参考
1. [引入Swift源码1](http://zcill.com/2016/01/23/%E5%9C%A8OC%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8swift%E5%86%99%E7%9A%84%E7%AC%AC%E4%B8%89%E6%96%B9%E5%BA%93/)
2. [引入Swift源码2](http://mengxiangyue.com/2016/01/11/OC%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8Swift/)
3. [引入动态库1](http://andelf.github.io/blog/2014/07/07/use-swift-dynamic-library/)
4. [引入动态库2](http://davidleee.com/2016/05/12/Use-Swift-framework-in-OC-project/)
5. [引入动态库3](http://www.jianshu.com/p/13ee670f21ac)
6. [引入动态库4](http://www.hangge.com/blog/cache/detail_1425.html)
7. [link](http://www.jianshu.com/p/42891fb90304)
