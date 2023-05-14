### 之前用法

1. 编码 [data base64Encoding]; 编码之后可以直接工具解码转换成图片，并且不带有类型 data:image/png;base64
2. 这样编码之后直接上传的图片，后端无法识别。原因是编码之后图片中含有‘＝ ＋’等一些特殊字符，发到后段之后就会变成空格，所以要将这些特殊的字符进行UTF8编码，发送的时候再转换为nsdata，同样要使用utf-8编码

```
 NSString* newImgStr = (__bridge NSString *) CFURLCreateStringByAddingPercentEscapes(kCFAllocatorDefault,
                      (CFStringRef)theImgStr,
                      NULL,
                      CFSTR(":/?#[]@!$&’()*+,;="),
                      kCFStringEncodingUTF8);

 NSData *data = [newImgStr dataUsingEncoding:NSUTF8StringEncoding];
```

### 新的用法
1. 编码 [data base64EncodedStringWithOptions:0]; 编码之后可以直接工具解码转换成图片，并且不带有类型 data:image/png;base64
2. 这样编码之后直接上传的图片，后端可以识别。原因要验证是否实在网路发送时候已经做过处理了？

### 最后
1. 在客户端上是不需要类型data:image/png;base64这部分的，后段做了图片格式验证的话就要主动带上

```
 NSString* imgStr = [NSString stringWithFormat:(%@%@), @"data:image/png;base64,", base64Str];
```

2. 后端返回的数据要去除类型才能展示出来

### 参考
1. [link1](http://blog.csdn.net/wang790492446/article/details/27309367)
2. [link2](http://blog.csdn.net/sjl_leaf/article/details/48179299)
3. [link3](http://www.cnblogs.com/jiangyazhou/archive/2012/03/15/2398423.html)
4. [验证工具](http://www.vgot.net/test/image2base64.php?)

