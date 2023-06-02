### 一：关键点
1. 照片以相机的坐标系来保存
2. 浏览的时候会根据照片中存储的方向进行旋转，转到适合观看的角度
3. 方向信息存储在图片文件头Exif中，**`Orientation`值提供了想要正常观看图像时应该旋转的方向**
4. PNG格式图像没有

### 二：方向值代表的意义

![1368|500](https://feihu.me/img/posts/orientation-eight-values.png)

原始存储照片及行列
![原始|500](https://feihu.me/img/posts/orientation-row0-column0.png)

旋转过之后的
![|500](https://feihu.me/img/posts/orientation-value.png)


iPhone上的情况是横向，即Home键在右侧
![默认|500](https://feihu.me/img/posts/orientation-zero-degree.png)
iOS和安卓的差异
1. 安卓img和canvas显示图片不会自动处理方向，需要手动旋转图片；要保持选择后的图片和相册看到的一致
2. iOS13.4+系统会自动处理方向，低于13.4系统需要手动旋转图片

### 三：参考

1. [link1](http://feihu.me/blog/2015/how-to-handle-image-orientation-on-iOS/)
2. [link2](https://www.jianshu.com/p/a542751d4ba3)
3. [iOS13.4兼容](https://evestorm.github.io/posts/13740/)
4. [阿里云](https://help.aliyun.com/document_detail/44691.html?spm=a2c4g.11186623.6.1160.1c5d149dByJ2yu)