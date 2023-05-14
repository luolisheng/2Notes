###使用hexo和Github Pages搭建博客

1. 根据官网教程安装hexo
 	- [link](https://hexo.io/zh-cn/docs/index.html)
2. 创建Github Pages

3. 本地创建文件夹初始化hexo
	- hexo init
	- npm install
	- 具体见官网
	
4. 修改_config.yml文件
	- `
	deploy:
	type: git
  	repo: git@github.com:{username}/{username}.github.io.git
  branch: master
  	`
  	- 注意yml文件的格式
  	
 5. 绑定域名
 6. 使用https
 7. 主题
 8. Google Analytics
 
 ---
 遇到的问题

 1. 本地不需要clone{username}.github.io。否则再本地clone{username}.github.io中执行'hexo init'会出问题。单独创建代码仓库来管理博客。
 
 2. 之前安装过hexo但是运行时候出现hexo: command not found，没有指定nodejs所致。
 	- nvm ls
 	- nvm use v4.1.4
 
 3. hexo d发布时提示'ERROR Deployer not found: git'
 	- npm install hexo-deployer-git --save
 	
 ---
 参考
 1. [link1](http://gold.xitu.io/entry/56657fe160b202595a6f8ef6)
 2. [link2](http://wonder4.me)
 3. [link3](http://androidren.com/index.php?qa=263&qa_1=bash-hexo-command-not-found)
 4. [link4](http://my.oschina.net/wolflion/blog/521283#OSC_h3_2)
