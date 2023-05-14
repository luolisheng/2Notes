---
title: SDWebImage、http304
tags: ["iOS"]
notebook: iOS
---

### 参考

1. [link1](https://juejin.im/post/5adeede8518825672f19839a)
2. [link2](https://segmentfault.com/a/1190000004084801)
3. [link3](https://mp.weixin.qq.com/s?__biz=MzI1MTE2NTE1Ng==&mid=2649517293&idx=1&sn=6fd88aadc274c8d14192ebff057ec8b8&chksm=f1efec66c698657065a13599294a244bcd8972b20c56d110d7044299e19d700486ec91801aa1#rd)
4. [SD中NSURLCache与自身缓存机制处理](https://juejin.im/post/5d76162bf265da03b120738d)

### options:SDWebImageRefreshCached的作用

1. 同时加载缓存（内存、磁盘）和网络
2. 首次请求网络不带有If-None-Match（If-Modified-Since），服务器返回ETag（Last-Modified）
3. 非首次请求网络带有If-None-Match，服务端根据If-None-Match判断静态资源是否更新

### SDWebImageDownloader中

1. SDWebImageDownloaderUseNSURLCache
	1. 使用此标志NSURLCache与默认缓存一起使用，默认情况下禁用NSURLCache避免重复缓存
	
2. SDWebImageDownloaderIgnoreCachedResponse
	1. 当image是从NSURLCache获取到的时候，直接返回nil


### UIImageView+WebCache中

1. SDWebImageRefreshCached
	1. 即使已缓存映像，也请遵守HTTP响应缓存控件，并在需要时从远程位置刷新映像。
    2. 磁盘缓存将由NSURLCache而不是SDWebImage处理，从而导致性能略有下降。
    3. 适合同一URL更新图像