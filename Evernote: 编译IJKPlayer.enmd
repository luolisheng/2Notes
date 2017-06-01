1. 选择编解码器
	1. cd config
	2. rm module.sh
	3. ln -s module-default.sh|module-lite-hevc.sh|module-lite.sh module.sh
	
2. 初始化
	1. cd ../
	2. sh init-ios-openssl.sh
	3. sh init-ios.sh

3.  编译
	1. cd ios
	2. sh compile-openssl.sh clean
	3. sh compile-ffmpeg.sh clean
	4. sh compile-openssl.sh all
	5. sh compile-ffmpeg.sh all