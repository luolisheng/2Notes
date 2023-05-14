---
title: iOS图片压缩上传
tags: ["iOS"]
notebook: iOS
---

### 详解

1. 压概念
	1. 文件体积变小，尺寸不变，像素数不变，质量下降
	2. UIImageJPEGRepresentation，大幅降低图片数据量，建议0.3～0.7
	3. UIImagePNGRepresentation，压缩质量不大
2. 缩概念
	1. 文件尺寸变小，像素数变少，体积变小
	2. 当图片本身尺寸较大时，设置压缩质量较低时，会出现图片点位像素不足，模糊不清。所以要先缩小图片的尺寸

### 参考

  1. [link1](http://superdanny.link/2016/01/28/iOS-Upload-Image/)
  2. [link2](https://juejin.im/entry/57b46a841532bc0063e6f416)
  3. [link3](https://superdanny.link/2016/01/28/iOS-Upload-Image/)

  

