---
title: ANDROID
tags: ["Android"]
notebook: Android
---

### ANDROID_HOME环境变量（三种安装方式）
1. downloaded from website and intall to Applications folder
	* /Applications/ADT/sdk
2. installed using Homebrew(brew cask install android-sdk)
	* /usr/local/Caskroom/android-sdk/{YOUR_SDK_VERSION_NUMBER}
3. installed with Android Studio
	* /Users/{YOUR_USER_NAME}/Library/Android/sdk

### 加入环境变量
1. export ANDROID_HOME={YOUR_PATH}
2. export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
3. source ~/.bash_profile

### 安装Gradle
1. AS新建工程后自动下载gradle
2. 下载位置 
	* Mac: ~/.gradle/wrapper/dists
	* Win: C:\Documents and Settings<用户名>.gradle\wrapper\dists

### Android工程
1. Import Project
2. 检查buildToolsVersion版本
	* 每个Module下的build.gradle的buildToolsVersion都要安装
	* buildToolsVersion版本小于minSdkVersion也会出错
	* 根目录下build.gradle中gradle插件版本
	* Gradle Wrapper中gradle的版本

### 参考
1. [link1](https://stackoverflow.com/questions/19986214/setting-android-home-enviromental-variable-on-mac-os-x)
2. [link2](http://stormzhang.com/devtools/2014/12/18/android-studio-tutorial4/)
3. [lin3](http://stormzhang.com/devtools/2015/01/05/android-studio-tutorial5/)
4. [提高篇](http://www.open-open.com/lib/view/open1466732917214.html)
