---
title: App程序间文档共享
tags: ["iOS"]
notebook: iOS
---

#### UIDocumentInteractionController

1. 能预览（仅限本地）
	1. 注册应用程序支持的文件类型，配置Info.plist文件
	2. 打开支持的文件，其他应用分享过来的
	3. [功能二：预览文件](https://juejin.im/post/5a3118a9f265da43133d259b)
	
2. 能分享、能操作（显示选项菜单）
	1. presentOpenInMenu（打开）
	2. presentOptionsMenu（打开和操作）
	3. [分享菜单中显示预览(QL)](https://serazheng.github.io/2015-12-05-%E9%80%9A%E8%BF%87UIDocumentInteractionController%E9%A2%84%E8%A7%88%E5%92%8C%E5%88%86%E4%BA%AB/)
3. 一次只能预览一个文件
4. 顶部导航无法定制
	1. [参考](https://www.jianshu.com/p/73048dbe6a7d) 

#### QLPreviewController

1. 只能预览（仅限本地）
2. 不能分享
3. 一次能预览多个文件
4. 顶部可以定制

#### UIActivityViewController

1. 不能预览
2. 能分享、能操作（显示选项菜单）
	1. 自定义服务，添加Share和Action
	2. 原生服务定制化，去除原生Share和Action
3. 只能模态和popover方式展示

### 参考

1. [系列](https://serazheng.github.io/2015-11-25-iOS%E5%AE%9E%E7%8E%B0App%E4%B9%8B%E9%97%B4%E7%9A%84%E5%86%85%E5%AE%B9%E5%88%86%E4%BA%AB/)
2. [link2](https://juejin.im/post/5a3118a9f265da43133d259b)
3. [link3](https://serazheng.github.io/2015-12-05-%E9%80%9A%E8%BF%87UIDocumentInteractionController%E9%A2%84%E8%A7%88%E5%92%8C%E5%88%86%E4%BA%AB/)
4. [link4](https://www.jianshu.com/p/73048dbe6a7d)