##### 应用已经提交到应用商店中，即使苹果使用了新的硬件开发者也不需要提交新的应用

1. Bitcode是LLVM编译器中间代码的编码
	- LLVM前端可以理解编程语言
	- LLVM后端能够理解如何展示用户下载应用的可执行版本
	- Bitcode介于这两者之间

2. LLVM将源码转变成Bitcode，再将Bitcode转换成可执行应用。这样可以让它轻易增加支持新的语言(前端)和新的CPU(后端).
虽然Bitcode不能在任何平台上运行，但是它可转化成任何被支持的CPU架构。