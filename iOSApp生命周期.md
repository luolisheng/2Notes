---
title: iOSApp生命周期
tags: iOS
notebook: iOS 
---

#### 一、iOSApp五种状态

1. 5种状态
    1. Not running
        * App还没有启动或者已经被系统终止
    2. Inactive
        * App正在前台运行，但此时还不能接收事件
        * 这是一个短暂的过渡状态，会很快进入Active或Background状态
    3. Active
        * App正在前台运行，能接收事件
    4. Background
        * App处于后台，但还能执行代码；通常只能保持5秒
        * 可以通过beginBackgroundTaskWithExpirationHandler申请延长后台时间，延长时间不超过600秒
    5. Suspended
        * App处于后台，依然在内存中但不能执行代码
        * 当系统内存低是可能会被逐出内存
2. App在5种状态间的转换流程图
    ![转换流程图](http://zxfcumtcs.github.io/img/StatechangesiOSapp.png)
3. App生命周期有关的几个时间规则
    ![时间规则](http://zxfcumtcs.github.io/img/apptimelimit.png)

#### 二、Launch​ Options Keys

1. 无论App在前台启动还是后台启动，能参与控制启动的两个点分别是appdelegate的两个回调；在这两回调中要确认App因何启动，还要准备app在启动过程中需要的数据和展示的UI
    1. application:willFinishLaunchingWithOptions:
    2. application:didFinishLaunchingWithOptions:
        * 此方法返回后UIKit才会将window显示在屏幕上
2. launchOptions记录了app启动原因以及相应的参数信息
    1. nil：直接点icon启动
    2. UIApplicationLaunchOptionsURLKey：App因openUrl启动
    3. UIApplicationLaunchOptionsSourceApplicationKey：App因openUrl启动，启动App的bundle id
    4. UIApplicationLaunchOptionsRemoteNotificationKey
        * App响应远程推送消息在前台启动
        * App响应静默推送消息在后台启动
    5. UIApplicationLaunchOptionsLocalNotificationKey：App响应本地推送前台启动
    6. UIApplicationLaunchOptionsLocationKey：APP因为一个位置相关的事件而启动
        * 地理围栏越界App在后台启动
    7. UIApplicationLaunchOptionsBluetoothCentralsKey：蓝牙在后台启动App来初始化中心设备
    8. UIApplicationLaunchOptionsBluetoothPeripheralsKey：蓝牙在后台启动App来初始化周边设备
    9. UIApplicationLaunchOptionsShortcutItemKey：3D Touch启动App
    10. 其他启动Key
        * UIApplicationLaunchOptionsUserActivityDictionaryKey
        * UIApplicationLaunchOptionsUserActivityTypeKey
        * UIApplicationLaunchOptionsCloudKitShareMetadataKey
3. 前台启动App
    * 状态：not running --> inactvie --> active
    * 系统创建一个新的进程已经主线程 --> 主线程上调用main函数 --> UIApplicationMain
        1. application:willFinishLaunchingWithOptions:
        2. application:didFinishLaunchingWithOptions:
        3. 展示UI
4. 后台启动App
    * 状态：后台启动进入background --> 处理事件 --> Suspended
    * 系统创建一个新的进程已经主线程 --> 主线程上调用main函数 --> UIApplicationMain
        1. application:willFinishLaunchingWithOptions:
        2. application:didFinishLaunchingWithOptions:
        3. 不展示UI
    * 后台事件类型
        * 系统接收到silent push
        * 系统启动 app 执行 background fetch 任务
        * background transfer 相关的事件，如任务完成、失败或需要鉴权等
        * newsstand apps、location apps、audio apps以及bluetooth apps收到相应的事件
    * **App能在后台启动的前提是用户没有在任务中心强制将app kill掉(iOS8 下的location apps除外)？？待验证**
5. 判断前台启动还是后台启动：application:[will | did]FinishLaunchingWithOptions
    * UIApplicationStateInactive：前台启动
    * UIApplicationStateBackground：后台启动

#### openURL打开App

1. 前台启动App
    * application:[will | did]FinishLaunchingWithOptions两个函数中判断能否处理该url
    * 两个函数都返回YES，进入application:openURL:sourceApplication:annotation:
2. 后台启动App
    * Background --> Active

#### 临时中断

1. 电话、打开通知中心、打开控制中心
    * App依然在前台运行，但其状态转换为inactive，不能接收touch events，可以继续接收notifactions以及其他events
    * 调用applicationWillResignActive:回调
2. 忽略临时中断操作
    * 调用applicationDidBecomeActive:回调


#### 参考

1. [link1](http://zxfcumtcs.github.io/2014/10/26/iosapplifecycle/)
