---
title: 深拷贝和浅拷贝 copy、mutableCopy
tags: ["iOS"]
notebook: iOS
---

### 拷贝针对容器类型、对象、自定义类型的，但是字符串也实现了copying和mutablecopying协议

1. 浅拷贝复制容器，深拷贝复制容器及其内部元素
2. 所有系统容器类的copy或mutableCopy方法，都是浅拷贝(单层深复制)
3. copy 与 mutableCopy 不等同于浅拷贝与深拷贝

### 集合的深复制

1. initWithArray:copyItems、initWithDictionary:copyItems
2. 集合进行归档(archive)，然后解档(unarchive)

### Array、Dictionry

@interface NSArray : NSObject : NSCopying, NSMutableCopying, NSSecureCoding, NSFastEnumeration

- (id)copy;            //浅复制，不重新创建容器，共用内部元素
- (id)mutableCopy;     //浅复制(单层深复制)，重新创建容器，共用内部元素
  
@end
  
@interface NSMutableArray : NSArray

- (id)copy;           //浅复制(单层深复制)，重新创建容器，共用内部元素
- (id)mutableCopy;    //浅复制(单层深复制)，重新创建容器，共用内部元素
  
@end

### 参考
1. [link1](https://www.zybuluo.com/MicroCai/note/50592)
2. [link2](http://blog.csdn.net/qq_18425655/article/details/51325921)

