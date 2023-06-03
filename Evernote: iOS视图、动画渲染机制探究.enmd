---
title: iOS视图、动画渲染机制探究
tags: ["iOS"]
notebook: iOS
---

iOS上视图和动画渲染是在另一个进程（BackBoard）上做的
1. 在App内部有4个阶段
	1. 布局
	2. 创建backing image
	3. 准备
	4. 提交
	
2. App外部有两个阶段
	1. 根据 layer 的各种属性（如果是动画的，会计算动画 layer 的属性的中间值），用 OpenGL 准备渲染
	2. 渲染这些可视的 layer 到屏幕

### 参考

1. [link1](http://bugly.qq.com/bbs/forum.php?mod=viewthread&tid=297)