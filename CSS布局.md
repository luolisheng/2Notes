---
title: CSS布局
tags: 
notebook: luolisheng 的笔记本
---

一个完整的 Web 页面是由一个一个 HTML 元素组成，每个元素都是一个盒子，如何摆放这些盒子是通过「布局」来决定的。Web的默认布局方式是流式布局（Nomal flow），只要不修改 CSS 的布局属性（display、float、position），HTML 元素就会按照默认布局方式来摆放这些「盒子」

## 常用布局

1. float:类似于行内元素，会一个挨着一个进行布局，可以从左边或右边开始布局
2. position:使元素脱离流式布局，放到指定位置
    - static:默认值，流式布局
    - relative:相对布局，相对的基准是元素在流失布局的位置
    - absolute:绝对布局，相对的基准是最近一个使用 position 不为 static 的父元素
    - fixed:固定在可视区域的某一个位置
    - sticky:当滑动到某个位置时悬停在某个位置
3. display
    - flex:一维布局
    - grid:二维布局
    - table:表格
4. muti-column


## 参考

1. [link1](https://mp.weixin.qq.com/s/oDNuyEdgUPweSZiOWnriQA)
