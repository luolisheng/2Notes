---
title: Xcode12编译架构
tags: iOS
notebook: iOS
---

### 简介

1. Xcode11使用Valid Architecture(VALID_ARCHS)
2. Xcode12使用排除的体系结构（EXCLUDED_ARCHS）
3. Xcode12为模拟器同时构建x86_64和arm64版本(for ARM Mac)；在某些情况下，使用xcodebuild指定generic
4. Xcode11中x86_64是默认添加不用手动填写
5. Xcode11将arm64转换为模拟器x86_64，若排除arm64则不能在模拟器运行
    1. Xcode12编译的SDK再Xcode11链接时，Build Settings和Pod配置文件中会多EXCLUDED_ARCHS选项，EXCLUDED_ARCHS会排除arm64
    2. 删除Target下Build Settings下EXCLUDED_ARCHS中arm64
    3. 删除Pods中Targets Support Files中XXX.debug.xcconfig->EXCLUDED_ARCHS中arm64
6. Xcode12使用旧版Xcode编译的SDK
    1. Xcode12会为模拟器编译x86_64 arm64俩个版本 (Build Active Architecture Only = NO)
    2. 可以找到旧版SDK的arm64版本，但是旧版SDK是针对设备的而不是针对模拟器，所以链接会出错 (M1 run xcode in Rosetta可解决)
    3. 解决办法：排除模拟器的arm64；Any iOS Simulator SDK = arm64
    4. xcodebuild -workspace iComeKernel.xcworkspace -scheme iComeKernel -destination "generic/platform=iOS Simulator" EXCLUDED_ARCHS="arm64 i386"

### 参考

1. [link1](https://medium.com/@khushwanttanwar/xcode-12-compilation-errors-while-running-with-ios-14-simulators-5731c91326e9)
2. [link2](https://apontious.com/2020/08/23/arm-wrestling-your-ios-simulator-builds/)
3. [link3](https://medium.com/@johny.urgiles/wrestling-with-xcode-12-and-arm64-6c7977922abb)
4. [组合架构](https://juejin.cn/post/6883055840039813128)
5. [合并库](https://www.jianshu.com/p/5f896321b1ea)
6. [link](https://stackoverflow.com/questions/63607158/xcode-12-building-for-ios-simulator-but-linking-in-object-file-built-for-ios)
7. [link](https://milanpanchal24.medium.com/xcode-12-building-for-ios-simulator-but-linking-in-object-file-built-for-ios-file-for-8c0cc28ec832)
8. [修改pod源码](https://www.jianshu.com/p/88180b4d2ab7)
