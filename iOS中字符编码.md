---
title: iOS中字符编码
tags: iOS
notebook: iOS
---

### iOS下的编码

1. iOS使用UTF-8编码
    1. 一个汉字或中文符号占3个字节
    2. 一个emoji表情占4个字节
2. 使用UTF-16计算
    1. 一个汉字或中文符号占2个字节（1个码元）
    2. 一个emoji表情占4个字节（2个码元）

### 字符串长度

1. iOS使用UTF-16码元(2个字节)来计算字符串长度
    1. length
    2. characterAtIndex:
    3. getCharacters:range:
    4. index
2. 处理字符串时候要获取到字符的真正范围，防止把字符拆开（emoji或2个码元的字符即组合字符序列）
    1. [str substringFromIndex:[str rangeOfComposedCharacterSequenceAtIndex:index].location]
    2. [str substringToIndex:NSMaxRange([str rangeOfComposedCharacterSequenceAtIndex:index])]
    3. [str substringWithRange:[str rangeOfComposedCharacterSequencesForRange:range]

### 参考

1. [link1](https://www.jianshu.com/p/1b3ecbc9b5c1)
2. [link2](https://juejin.im/post/5dc3b9a46fb9a04a95289a84#heading-16)
3. [NSString与Unicode](https://objccn.io/issue-9-1/)
