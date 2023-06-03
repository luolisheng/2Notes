
### NSTimer的几个问题

1. 循环引用问题
	- NSTimer会强引用target，同时Runloop会引用没有invalidate的NSTimer
2. Runloop问题
	- NSTimer依赖于Runloop的机制进行工作，默认运行在Runloop的default mode中
	- ScrollView在用户滑动时，主线程Runloop会转到UITrackingRunLoopMode，此时NSTimer就不会运行。想让NSTimer不失效，要将NSTimer设置成运行在NSRunLoopCommonModes
3. 线程问题
	- NSTimer不能在子线程中使用，要想使用久需要自己激活和管理
4. 动态修改时间间隔
5. 不支持闭包

### 参考

1. [link1](https://github.com/100mango/zen/blob/master/%E6%89%93%E9%80%A0%E4%B8%80%E4%B8%AA%E4%BC%98%E9%9B%85%E7%9A%84Timer/make%20a%20timer.md)