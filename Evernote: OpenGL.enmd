---
title: OpenGL
tags: ["iOS"]
notebook: iOS
---

===
1. GLKViewController渲染runloop mode不是NSRunLoopCommonModes，而是NSDefaultRunLoopMode，
	因此在UIKit中使用GLKViewController，当滑动界面时，OpenGL是不会渲染的。
	为了解决这个问题，可以使用HJGLKViewController替换GLKViewController，HJGLKViewController中默认渲染RunLoop使用NSRunLoopCommonModes模式

2. 使用CADisplayLink来刷新GLKView时候也要注意设置CADisplayLink的runloop

### 参考

1.[link1](https://www.raywenderlich.com/5223/beginning-opengl-es-2-0-with-glkit-part-1)
2.[link2](https://www.raywenderlich.com/5235/beginning-opengl-es-2-0-with-glkit-part-2)