---
title: 制作动态、静态framework和静态库(.a)
tags: iOS
notebook: iOS
---

### 动态库、静态库、framework区别

1. 静态库 常见的是 .a
2. 动态库常见的是 .dll(windows)，.dylib(mac)，so(linux)
3. framework(in Apple): Framework是Cocoa/Cocoa Touch程序中使用的一种资源打包方式；可以将代码文件、头文件、资源文件、说明文档等集中在一起，方便开发者使用。framework其实是资源打包的方式，和静态库动态库的本质是没有关系的

### 静态库

1. 静态库是编译好的一个或多个.o的集合
2. 链接器只会将静态库中被使用部分(.o)合并到可执行文件中去
3. 链接器会用函数的实际地址来代替函数引用(汇编指令)
4. 静态库会被拷贝到可执行文件中去

### 动态库

1. 动态库分动态链接库和动态加载库两种的，这两个最本质的区别还是加载时间
    * 动态链接库：当可执行文件被加载，动态库也随着被加载到内存中
    * 动态加载库：当需要的时候再使用 dlopen 等通过代码或者命令的方式来加载
2. 动态链接是使用了Procedure Linkage Table (PLT)。首先这个 PLT 列出了程序中每一个函数的调用，当程序开始运行，如果动态库被加载到内存中，PLT会去寻找动态的地址并记录下来，如果每个函数都被调用过的话，下一次调用就可以通过PLT直接跳转了
3. 自己创建的动态库会被拷贝到app包中的Frameworks文件夹，当可执行文件被加载，动态库也随着被加载到内存中

### 区别

1. 动态库是动态的，所以你事先不知道某个函数的具体地址, 因此动态链接器在链接函数的时候需要做大量的工作；而静态库编译时候就已经确定
2. 动态库静态库还是有点区别的是，每一个函数的调用还是需要通过一张PLT
3. 动态库启动或运行时候加载到独立于app的内存中
4. 静态framework = .a + .h + bundle
5. 动态framework = .dylib/.tbd + .h + bundle
6. 大量使用动态库会拖慢启动时间
    * 态链接器需要在程序启动时候去执行链接过程，把所有未定义的符号找到，把空的地址全部确定。
    * 就是说把静态链接做的事情放到运行时去做，只会变慢。
    * 统的SDK可以用共享内存的方式减少向虚拟内存映射的时间，但是符号链接的过程必然不会少的。
7. 静态库可以简单理解为一堆目标文件(.o/.obj)的打包体(并非二进制文件)，而动态库可以简单理解为 一个没有main函数的可执行文件

### 从源代码到app

1. 预处理（Pre-process）：把宏替换，删除注释，展开头文件，产生 .i 文件
2. 编译（Compliling）：把之前的 .i 文件转换成汇编语言，产生 .s文件
3. 汇编（Asembly）：把汇编语言文件转换为机器码文件，产生 .o 文件
4. 链接（Link）：对.o文件中的对于其他的库的引用的地方进行引用，生成最后的可执行文件（同时也包括多个 .o 文件进行 link）

### 编译选项

1. -ObjC：链接器会加载静态库中所有的Objective-C类和Category（导致可执行文件变大）；当静态库只有Category时-ObjC会失效，使用-all_load
2. -all_load：链接器会加载静态库中所有的Objective-C类和Category
3. -force_load：加载特定静态库的全部类，需要指定静态库；当两个静态库存在同样的符号时，使用-all_load会出现duplicate symbol的错误，此时可以选择将其中一个库-force_load

### 参考

1. [link3](http://www.cnblogs.com/apem/p/4569502.html)
2. [link4](https://www.gitbook.com/book/leon_lizi/-framework-/details)
3. [link5](https://github.com/Damonvvong/DevNotes/blob/master/Notes/framework.md)
4. [link6](https://github.com/Damonvvong/DevNotes/blob/master/Notes/framework2.md)
5. [编译链接过程](https://wukaikai.tech/2019/08/12/iOS%E7%A8%8B%E5%BA%8F%E5%91%98%E7%9A%84%E8%87%AA%E6%88%91%E4%BF%AE%E5%85%BB-%E5%89%8D%E8%A8%80%EF%BC%88%E9%9B%B6%EF%BC%89/)
6. [MachO文件结构分析](https://www.xuyanlan.com/2019/02/24/macho-analysis/)
7. [动态库隔离](https://www.tqwba.com/x_d/jishu/201966.html)
8. [编译选项](https://cloud.tencent.com/developer/article/1620026)
9. [编译选项](https://www.cnblogs.com/rayshen/p/5160218.html)
10. [framework动态更新](https://www.cnblogs.com/xiaonanxia/p/5126395.html)
11. [动态静态相互依赖](https://zhang759740844.github.io/2016/10/17/%E6%89%93%E5%8C%85%E9%9D%99%E6%80%81%E5%BA%93/)

### Embedded Binaries/Frameworks VS Linked Framework and Libraries

1. embedded frameworks are placed within an app’s sandbox and are only available to that app.
2. system frameworks are stored at the system-level and are available to all apps.

### 参考

1. [link1](https://googleapple.com/Embedded-Binaries-%E5%92%8C-Linked-Frameworks-and-Libraries%E7%9A%84%E5%8C%BA%E5%88%AB.html)
2. [link2](https://stackoverflow.com/questions/32675272/when-should-we-use-embedded-binaries-rather-than-linked-frameworks-in-xcode)
