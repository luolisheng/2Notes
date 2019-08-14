---
title: iOS URL缓存
tags: ["iOS"]
notebook: iOS
---

### 详解

1. 使用系统自身缓存来设计一套缓存机制；这套缓存无需自己编写内存和磁盘存储，无需自行检查缓存过期策略就能轻松实现数据缓存。
2. 内存缓存建议使用NSCache，提供了缓存过高自动删除功能
3. 默认缓存策略
	1. 先检查本地是否有缓存
	2. 如本地没有缓存直接请求网络
	3. 本地有缓存，检查缓存是否过期
		1. 没有过期则直接使用缓存
		2. 过期则发起请求，服务端对比资源Last-Modified/Etags。不同则返回新数据，相同返回304继续使用缓存。
			
4. 使用默认缓存策略，客户端不用做任何设置，只需服务端响应头加上Cache-Control:max-age:xxx、ETag或Last-Modified
5. 不想使用默认缓存策略，每次都去检查资源是否变更 
	1. 设置NSMutableURLRequest的cachePolicy:NSURLRequestReloadIgnoringCacheData，每次要请求服务器进行校验。
	2. 手动给请求头加上If-None-Match或者If-Modified-Since
6. 从CDN请求资源时候，若CDN本身也有缓存，可在url后面添加随机数来让CDN重新请求。如xxxxx.jpg?1

### 参考
1. [iOS架构设计-URL缓存](https://www.cnblogs.com/kenshincui/p/6944834.html)
2. [NSURLCache](https://nshipster.cn/nsurlcache/#http-%E7%BC%93%E5%AD%98%E8%AF%AD%E4%B9%89)
3. [使用两行代码就能完成80%的缓存需求](https://github.com/ChenYilong/ParseSourceCodeStudy/blob/master/02_Parse%E7%9A%84%E7%BD%91%E7%BB%9C%E7%BC%93%E5%AD%98%E4%B8%8E%E7%A6%BB%E7%BA%BF%E5%AD%98%E5%82%A8/iOS%E7%BD%91%E7%BB%9C%E7%BC%93%E5%AD%98%E6%89%AB%E7%9B%B2%E7%AF%87.md)