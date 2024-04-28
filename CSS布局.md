---
title: CSS布局
tags: ['H5','h5']
notebook: luolisheng 的笔记本
---

一个完整的 Web 页面是由一个一个 HTML 元素组成，每个元素都是一个盒子，如何摆放这些盒子是通过「布局」来决定的。Web的默认布局方式是流式布局（Nomal flow），只要不修改 CSS 的布局属性（display、float、position），HTML 元素就会按照默认布局方式来摆放这些「盒子」

## 常用布局(脱离流式布局)

1. float:类似于行内元素，会一个挨着一个进行布局，可以从左边或右边开始布局
2. position:使元素脱离流式布局，放到指定位置
    - static:默认值，流式布局
    - relative:相对布局，相对的基准是元素在流式布局的位置
    - absolute:绝对布局，相对的基准是最近一个使用 position 不为 static 的父元素
    - fixed:固定在可视区域的某一个位置
    - sticky:当滑动到某个位置时悬停在某个位置
3. display
    - flex:一维布局
    - grid:二维布局
    - table:表格
4. muti-column

## 元素盒子模型(display)

1. 块级盒子
	1. 尽可能大的利用可用空间
	2. 独占一行
	3. 可以使用width、height改变大小
	4. 使用padding、margin、border会影响其他元素位置
	5. 使用了盒子模型的所有特性
2. 行内盒子
	1. 不会独占一行显示，一个接一个排列
	2. 使用width、height无效
	3. padding、margin 和 border 会起作用，但不会影响其它元素（垂直方向上）
	4. 只使用盒子模型的部分特性

## 块级盒子模式(box-sizing)

1. 只对块级元素生效，行内元素无效
2. 标准盒子模型
	1. 设置的width 和 height 是 content 的宽高
	2. 添加padding 和 border 的时候，会增加盒子的整体大小
	3. margin不会计入盒子的大小，它只是表示外部的边距
3. 另一种模型：border-box
	1. 设置的 width 和 height 是盒子的宽高
	2. 内容 content 的宽需要减去 border 和 padding 的宽
	3. margin不会计入盒子的大小，它只是表示外部的边距

## 参考

1. [link1](https://mp.weixin.qq.com/s/oDNuyEdgUPweSZiOWnriQA)
2. [position](https://mp.weixin.qq.com/s/RFlSDGIq7ERm2CWCzpQCJQ)