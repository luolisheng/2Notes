1. 安全区域
	* 系统根据安全区域来自动调整scrollview的偏移量
	* 安全区域帮助我们将view放置在整个屏幕的可视部分
	* 可以使用additionalSafeAreaInsets去扩展安全区域
	* safeAreaInsets属性反映了view距离该view的安全区域的边距
2. iOS11 scrollview内容和边缘距离是由adjustedContentInset属性决定
	* adjustContentInset表示contentView.frame.origin偏移了scrollview.frame.origin多少，由系统推算得来
	* 计算方式由contentInsetAdjustmentBehavior来决定
3. UIScrollViewContentInsetAdjustmentAutomatic
	* adjustedContentInset = safeAreaInset + contentInset
	* 不管是否可以滚动
4. UIScrollViewContentInsetAdjustmentScrollableAxes
	* 在滚动方向上：adjustedContentInset = safeAreaInset + contentInset
	* 不可在滚动方向上：adjustedContentInset = contentInset
5. UIScrollViewContentInsetAdjustmentNever
	* adjustedContentInset = contentInset
6. UIScrollViewContentInsetAdjustmentAlways
	* adjustedContentInset = safeAreaInset + contentInset

### 参考
1. [link1](https://mp.weixin.qq.com/s/W1_0VrchCO50owhJNmJnuQ)
2. [link2](https://mp.weixin.qq.com/s/AZFrqL9dnlgA6Vt2sVhxIw)
