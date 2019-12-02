---
title: pod库添加资源文件
tags: ["iOS"]
notebook: iOS
---


### 不使用.xcassets

1. 使用resource_bundles

```
spec.resource_bundles = {
    'MapBox' => ['MapView/Map/Resources/*.png'],
    'OtherResources' => ['MapView/Map/OtherResources/*.png']
  }

```
图片会打包到对应的bundle中，bundle单独放到main bundle下

2. 使用resources

```
spec.resources = ['Images/*.png', 'Sounds/*']

```
图片会打包到mian bundle中

### 使用.xcassets

1. 使用resource_bundles

```
spec.resource_bundles = {
    'MapBox' => ['MapView/Map/Resources/*.xcassets'],
    'OtherResources' => ['MapView/Map/OtherResources/*.xcassets']
  }

```

xcassets会打包到对应的bundle中的Assets.car，bundle单独放到main bundle下

2. 使用resources

```
spec.resources = ['Images/*.xcassets', 'Sounds/*.xcassets']

```
xcassets中的图片会被拷贝出来复制到到mian bundle下Assets.car

### 图片加载使用bundle

只要图片不在main bundle下，加载图片都需要指定bundle

### 参考

1. [link1](https://juejin.im/post/5a77fb8df265da4e99576702)
2. [link2](https://www.jianshu.com/p/cb5a43bce796)
3. [link3](https://vongloo.me/2018/03/17/Pod-Resource/)