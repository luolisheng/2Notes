---
title: iOS捕捉系统截屏
tags: iOS
notebook: iOS
---

1. 订阅系统截屏通知UIApplicationUserDidTakeScreenshotNotification

2. 代码截图如下

```
    #import <QuartzCore/QuartzCore.h>
    if ([[UIScreen mainScreen] respondsToSelector:@selector(scale)]) {
        UIGraphicsBeginImageContextWithOptions(self.window.bounds.size, NO, [UIScreen mainScreen].scale);
    } else {
        UIGraphicsBeginImageContext(self.window.bounds.size);
    }

    [self.window.layer renderInContext:UIGraphicsGetCurrentContext()];
    UIImage *image = UIGraphicsGetImageFromCurrentImageContext();
    UIGraphicsEndImageContext();
    NSData *imageData = UIImagePNGRepresentation(image);
    if (imageData) {
        [imageData writeToFile:@"screenshot.png" atomically:YES];
    } else {
        NSLog(@"error while taking screenshot");
    }
```
