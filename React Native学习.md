---
title: React Native学习
tags: React Native
notebook: iOS
---

### 一、创建新项目

1. 如果你之前全局安装过旧的react-native-cli命令行工具，请使用npm uninstall -g react-native-cli卸载掉它以避免一些冲突。
2. 使用init命令创建项目默认会使用最新的react native版本，可指定版本创建项目npx react-native init MyApp --version 0.44.3

### 二、核心组件和原生组件

1. RN使用React和设备本级功能来构建应用程序。
2. 在RN中，可以使用React组件通过JS调用原生视图；运行时，RN为组件创建相应的原生视图。
3. RN允许构建自己的原生组件，满足程序需求。
4. RN自带基本的组件可直接使用。
5. React基础组件是web组件，RN基础组件是原生组件。
6. 组件的生命周期
    1. componentDidMount
    2. shouldComponentUpdate
    3. componentWillUnmount
    4. componentDidCatch

### 三、属性和状态

1. props是在父组件中指定，一经指定在组件的生命周期中不再改变。
2. 需要改变的数据要使用state，一切状态变化都是state变化
    1. state的修改必须要通过setState()方法
    2. setState是个merge合并操作，只修改指定状态不影响其他
    3. setState是异步操作，修改不会马上生效
    4. 每次调用setState时，组件都会重新执行render方法重新渲染

### 四、样式

1. RN中使用JS来写样式；所有核心组件都接受名为style的属性；基本遵循CSS的命名，使用驼峰命名法。
2. style属性可以是普通JS对象，也可以是个数组。
3. 使用StyleSheet.create来集中定义组件样式。

### 五、宽高

1. RN中的width和height尺寸是无单位的、设备像素密度无关的逻辑像素点
2. 弹性宽高(flex)
    1. 弹性布局可以使组件在可用的空间中动态的扩张和收缩，不同屏幕上提供一致的布局结构。
    2. 父容器的尺寸不为零弹性布局才有效。如果父容器没有固定宽高也没有弹性布局则父容器尺寸为零。
3. 相关属性值
    1. flex
        1. flex决定元素在主轴上如何填满可用区域； 只能指定一个数字值
        2. 主轴默认为column（竖直轴）
    2. flexDirection
        1. 决定布局的主轴方向
    3. justifyContent
        1. 决定子元素沿主轴的排列方式(flex-start、center、flex-end、space-around、space-between、space-evenly)
    4. alignItems
        1. 决定子元素沿次轴的排列方式（flex-start、center、flex-end、stretch）
    5. alignSelf
        1. 决定子元素本身在父容器中的对齐方式
        2. 可覆盖父容器中的alignItems项
    6. flexWrap
        1. 决定当子元素沿主轴布局从父容器溢出时布局情况
        2. 默认情况下不允许包装只有一行，如果允许包装设置alignContent指定多行展示效果
    7. alignContent
        1. 决定当父容器开启flexWrap时子元素沿次轴的排列方式(flex-start、center、flex-end、stretch、space-around、space-between、space-evenly)
    8. flexGrow\flexShrink\flexBasis
    9. width\height
        1. auto
        2. pixels：可能不是最终样式
        3. percentage：父容器的宽高比
    10. position(绝对和相对布局)
        1. 决定了元素在父容器中的位置，默认是relative
        2. relative
            1. 根据元素正常流动定位，相对与兄弟节点布局
            2. 根据top，right，bottom，和left设置偏移量
        3. absolute
            1. 元素不会参与正常的布局流程，它的布局与兄弟姐妹无关；相对于父容器进行布局
            2. 根据top，right，bottom，和left设置偏移量

### 六、文本输入

1. TextInput
    1. onChangeText
    2. onSubmitEditing

### 七、触摸事件

1. Button
2. Touchable 系列组件
3. ScrollView
    1. ScrollView中的所有组件都会被渲染，较长的滚动列表使用FlatList
4. FlatList
    1. 显示一个垂直滚动列表，元素结构近似数据不同
    2. 适用于长列表且元素个数可增删，优先渲染屏幕上的可见元素
5. SectionList
    1. 显示分组数据并且带有分组标签

### 八、网络

1. 使用Fetch API来访问网络
2. 不能使用jQuery，jQuery使用了很多浏览器中才有但是RN中没有的东西
3. WebSocket单个TCP连接上全双工通信

### 参考

1. [中文官网](https://reactnative.cn/docs/getting-started)
2. [JSCore](https://tech.meituan.com/2018/08/23/deep-understanding-of-jscore.html)
3. [ES6 class](https://segmentfault.com/a/1190000007179203)
4. [构造函数](https://juejin.im/post/5a694be551882573541c8f29)
5. [React DevTools](https://zh-hans.reactjs.org/blog/2019/08/15/new-react-devtools.html)
6. [调试](https://juejin.im/post/5ca899acf265da3097287681#heading-13)
7. [调试](https://www.barretlee.com/blog/2019/03/18/debugging-in-vscode-tutorial/)
8. [link](http://blog.cnbang.net/tech/3461/)