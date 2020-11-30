---
title: Xcode12
tags: iOS
notebook: iOS 
---

### 简介

1. Xcode11使用Valid Architecture(VALID_ARCHS)
2. Xcode12使用排除的体系结构（EXCLUDED_ARCHS）
3. Xcode12为模拟器同时构建x86_64和arm64版本
4. Xcode11中x86_64是默认添加不用手动填写，Xcode12需要手动填写
5. Xcode11将arm64转换为模拟器x86_64，若排除arm64则不能在模拟器运行
    1. Xcode12编译的SDK再Xcode11链接时，Build Settings和Pod配置文件中会多EXCLUDED_ARCHS选项，EXCLUDED_ARCHS会排除arm64
    2. 删除Target下Build Settings下EXCLUDED_ARCHS中arm64
    3. 删除Pods中Targets Support Files中XXX.debug.xcconfig->EXCLUDED_ARCHS中arm64

### 参考

1. [link1](https://medium.com/@khushwanttanwar/xcode-12-compilation-errors-while-running-with-ios-14-simulators-5731c91326e9)
2. [link2](https://apontious.com/2020/08/23/arm-wrestling-your-ios-simulator-builds/)
3. [link3](https://medium.com/@johny.urgiles/wrestling-with-xcode-12-and-arm64-6c7977922abb)
4. [组合架构](https://juejin.cn/post/6883055840039813128)
5. [合并库](https://www.jianshu.com/p/5f896321b1ea)
