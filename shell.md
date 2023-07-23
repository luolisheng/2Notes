##### shell 语法
1. 变量
	- 赋值符号两边没有空格，值不加引号 	eg:	name=luolisheng
	- 值中间有空格时要加上引号		  	eg:	name="luo li sheng"
	- 获取变量时要用$					eg:	echo $name
	- 变量中使用其他变量				eg:	name2="${name} ${name}"

2. echo输出
	－ 加参数-n可省略结尾的换行符号		eg: echo -n "Enter you name:"