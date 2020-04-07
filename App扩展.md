---
title: App扩展
tags: iOS
notebook: iOS
---

### 简介

1. 扩展让App间数据交换成为可能，用户可以在 app 中使用其他应用提供的功能，而无需离开当前的应用
2. 基于安全和性能的考虑，每一个扩展运行在一个单独的进程中，它拥有自己的 bundle ， bundle 后缀名是.appex
3. 几种类型的扩展
    * Action Extension，用在UIActivityViewController中的第二行的Action List
    * Custom Keyboard，提供给开发者自定义键盘的权限
    * Document Provide，提供文档的远程存取服务
    * Photo Editing，提供照片和视频的编辑服务
    * Today，提供在Toady Widget里面展示应用数据的服务
    * Share，用在UIActivityViewController中的第一行的APP List提供iOS实体内容的分享服务
    * iOS9新增扩展
4. 原理
    * 一个Extension开发和发布必须依托于一个宿主应用(Container App)
    * 一个Extension允运行不会依赖于宿主应用，它是一个独立的二进制包并且可以独立运行
    * 用户需要通过一个主应用(Host App)打开Extension
    * App Extension的生命周期不同于APP，是有固定的流程，由系统启动并且关闭的
        1. ![app_extensions_lifecycle](http://upload-images.jianshu.io/upload_images/1216322-80ef0376c6d824ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 一个App Extension作为一个桥梁，将宿主应用和主应用连接起来进行交互,而这个交互流程针对宿主应用和主应用是不一样的
        1. App Extension可以和主应用直接交互，需要通过主应用唤醒App Extension
        2. App Extension并不能和宿主应用直接交互，App Extension不依赖于宿主应用可以独立运行。
            * App Extension只可以通过固定的几个API来和宿主应用分享内容
            * 只用Today Extension可以通过URL Scheme方式打开宿主应用
            * ![detailed_communication](http://upload-images.jianshu.io/upload_images/1216322-3fb501c8a93ad3ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
5. 每一个App Extension和APP一样都包含一个Info.plist文件，用来描述Share Extension的基本配置信息
    * CFBundleDisplayName： 扩展显示名称
    * NSExtension：扩展主要配置
6. Share Extension
    * NSExtension：配置分享支持的内容类型和数量
    * NSExtensionPrincipalClass：配置自己的主界面
    * extensionContext相关操作
        * self.extensionContext.inputItems遍历查找资源
            * 除了文本内容，其他类型的内容都是作为附件存储的，附件又是封装在一个叫NSItemProvider的类型中
            * 加载资源是异步过程
            * 结构如图
                * ![extensionContext.inputItems](https://upload-images.jianshu.io/upload_images/1804600-a4324fc2bdd4ffad.png?imageMogr2/auto-orient/strip|imageView2/2/format/webp)
        * self.extensionContext取消关闭分享操作
    * 对默认分享界面进行扩展，类似微信分享
    * 使用NSExtensionPrincipalClass替换默认分享界面，但是不能往下页面进行跳转了
    * 扩展和宿主应用共用代码
        * .m中开放给扩展target
        * .m中嵌套其他.m，考虑使用共用的framework
    * 扩展中使用第三方库
        * Podfile中新建target配置
    * 扩展图标设置
7. App Groups
    * 尽管App Extension的bundle包含在宿主App的bundle中，但两者之间仍不能直接相互访问资源，需要通过App Groups创建共享域
    * App Groups开发者账号配置
        1. 创建App Group ID
        2. 创建宿主App ID，开启Groups功能并关联Group ID
            * 创建或更新profie
        3. 创建Share Extension ID，开启Groups功能并关联Group ID
            * 创建或更新profie
    * 数据共享方式
        * NSUserDefaults
            * initWithSuiteName:@"groupid"方法来初始化一个NSUserDefaults对象
        * NSFileManager
            * containerURLForSecurityApplicationGroupIdentifier:@"groupid"方法可以获得AppGroup的共享目录
        * CoreData
            * CoreData是基于NSFileManager取得共享目录后来实现数据共享的
            * 先使用NSFileManager取得共享目录，然后再指定共享目录为存储数据文件的目录

### 参考˜

1. [link1](https://serazheng.github.io/2016-06-27-Swift%E4%BD%BF%E7%94%A8Share%20Extension%E5%AE%9E%E7%8E%B0%E6%9B%B4%E5%A4%9A%E7%9A%84%E5%86%85%E5%AE%B9%E5%88%86%E4%BA%AB/)
2. [link2](https://www.jianshu.com/p/863ce6729455)
3. [调试](https://www.jianshu.com/p/cca733aca3c6)
4. [link3](https://blog.csdn.net/flg1554112450/article/details/80743441)
5. [link4](https://www.shenhongbang.cc/jiluShareExtensiondekaifa.html)
