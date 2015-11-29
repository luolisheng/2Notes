#### 符号表

1. Xcode项目编译后(build)，在生成的二进制文件.app统计的目录下生成的dSYM文件。  
dSYM文件其实是一个目录，在子目录中包含了一个16进制的保存函数地址映射信息的中转文件，所有Debug的symbols都在这个文件中(包括文件名、函数名、行号等)，所以也称之为调试符号信息文件。一般地，Xcode项目每次编译后，都会生成一个新的.dSYM文件。

2. 每次归档后生成文件在/Users/<用户名>/Library/Developer/Xcode/Archives 对应的目录下。

3. 使用make编译生成.o文件，不会生成dSYM文件，可使用dsymutil工具从.o中提取符号信息。

#### 文件对应

1. 每次编译后app文件和dSYM文件成对出现，并且两者有相同的UUID来表示是同一次的生成的。

2. crash文件也有自己的UUID，和app、dSYM文件UUID相同，只要这三个文件的 UUID 一致，我们就可以通过他们解析出正确的错误函数信息了。

3. 查看UUID
	- 查看 xx.app 文件的 UUID，terminal 中输入命令 ： dwarfdump --uuid xx.app/xx (xx代表你的项目名)
	- 查看 xx.app.dSYM 文件的 UUID ，在 terminal 中输入命令：dwarfdump --uuid xx.app.dSYM 
	- crash 文件内第一行 Incident Identifier 就是该 crash 文件的 UUID

#### 参考
- [link1](http://answerhuang.duapp.com/index.php/2014/07/06/dsym_tool/)
- [link2](http://bugly.qq.com/blog/?p=119)
- [检测工具](http://bugly.qq.com)
