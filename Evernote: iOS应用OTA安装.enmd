---
title: iOS应用OTA安装
tags: ["iOS"]
notebook: iOS
---

### 自建证书

```
iOS7.1之后不再支持http方式，使用OpenSSL自建证书
```
1. 生成CA私钥
	* openssl genrsa -out ca.key 2048
2. 用CA私钥产生CA自签署证书
	* openssl req -new -x509 -days 365 -key ca.key -out ca.crt
	* Common Name填写便于识别的名字即可
	* 到这里已经完成自己的CA证书了，只不过没有人认可，签署的所有其他证书无人认可
3. 生成服务器证书私钥 
	* openssl genrsa -out server.key 2048
4. 生成服务器证书请求文件
	* openssl req -new -key server.key -out server.csr
	* Common Name要填写服务器域名或ip
	* organizationName要和填写的CA证书的organizationName一致
5. CA根证书签署服务器证书
	* 创建demoCA文件夹
		* demoCA下创建index.txt，内容为空
		* demoCA下创建serial文件，内容填写01
		* demoCA下创建newcerts文件夹
	* openssl ca -in server.csr -out server.crt -cert ca.crt -keyfile ca.key -config /System/Library/OpenSSL/openssl.cnf
		* 使用/System/Library/OpenSSL/openssl.cnf
6. 把CA证书安装到设备，通用->关于本机->证书信任设置 里打开信任

### 使用puma配置ssl
```
ssl_key_path = ENV.fetch("SSL_KEY_PATH") { "/Users/luolisheng/Downloads/iOS_Samples/app-host/config/ssl/server.key" }
ssl_crt_path = ENV.fetch("SSL_CERT_PATH") { "/Users/luolisheng/Downloads/iOS_Samples/app-host/config/ssl/server.crt" }

if ENV.fetch("RAILS_ENV") { "?" } == "development"
  threads 1, threads_max
  ssl_bind '192.168.36.188', '3001', {
    key: ssl_key_path,
    cert: ssl_crt_path,
    verify_mode: 'none'
  }
else
end
```

### 参考
1. [link1](https://www.jianshu.com/p/35ca63ec0d8e)
2. [link2](https://github.com/pluosi/app-host)
3. [link3](https://www.jianshu.com/p/54312134ac9d)
2. [link4](https://github.com/bumaociyuan/ios-ipa-server)
4. [ssl_puma.rb](https://gist.github.com/tadast/9932075)
5. [Chrome证书问题](https://github.com/mrdulin/blog/issues/32)