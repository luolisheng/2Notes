---
title: position与anchorPoint
tags: ["iOS"]
notebook: iOS
---

1. positon是layer中的anchorPoint在superLayer中的坐标点
2. 单独修改potion或anchorPoint都不会影响另一个
3. frame、position与anchorPoint有以下关系
	* frame.origin.x = position.x - anchorPoint.x * bounds.size.width;
	* frame.origin.y = position.y - anchorPoint.y * bounds.size.height;

### 参考

1. [link1](http://wonderffee.github.io/blog/2013/10/13/understand-anchorpoint-and-position/)
2. [link2](http://wonderffee.github.io/blog/2013/10/14/understand-anchorpoint-and-position-with-instance/)