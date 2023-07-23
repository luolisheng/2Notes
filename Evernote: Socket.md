---
title: Socket
tags: ["iOS"]
notebook: iOS
---

  1. OSI七层模型。
  	* <en-media type="image/jpeg" hash="ae1aa91d754eb94d91a8ae7899a386cd"/>  

  3. TCP/IP五层模型。
  	* <en-media type="image/jpeg" hash="4696a7ea395500dafd2a4d687fd20ecc"/>  

  5. TCP/IP协议中的应用层处理七层模型中的第五层、第六层和第七层的功能。
  6. TCP/IP协议族包括运输层、网络层、链路层。
  7. TCP/UDP区别
    * TCP：面向连接、传输可靠(保证数据正确性,保证数据顺序)、用于传输大量数据(流模式)、速度慢，建立连接需要开销较多(时间，系统资源)。
    * UDP：面向非连接、传输不可靠、用于传输少量数据(数据包模式)、速度快。
    * TCP是一种流模式的协议，UDP是一种数据报模式的协议。
    	* TCP面向连接必须和服务器进行三次握手。在连接持续的过程中，socket中收到的数据都是由同一台主机发出的，知道保证数据是有序的到达就行了。
    	* UDP不需要和服务器连接，只要知道接收端的IP和端口，将数据报投递出去。任何主机都可以向接收端发送数据。这时候，如果一次能读取超过一个报文的数据，则会乱套。比如，主机A向发送了报文P1，主机B发送了报文P2，如果能够读取超过一个报文的数据，那么就会将P1和P2的数据合并在了一起，这样的数据是没有意义的

### 参考

  1. [详解1](http://www.jianshu.com/p/3e4f3de18e3b)
  2. [详解2](http://www.cnblogs.com/goodcandle/archive/2005/12/10/socket.html)
  3. [详解3](http://www.kuqin.com/shuoit/20150308/345099.html)
  3. [link2](https://github.com/ChenYilong/iOSBlog/blob/master/Tips/%E5%A4%A7%E8%AF%9DSocket.md)
  4. [link3(流socket和数据报socket)](http://blog.sina.com.cn/s/blog_436499570100zkku.html)
  5. [link4](http://www.admin10000.com/document/2937.html)
  6. [心跳包](https://zhidao.baidu.com/question/433173583116867724.html)
  7. [七层/五层](http://www.ha97.com/3215.html)
  8. [TCP粘包](http://blog.csdn.net/ce123_zhouwei/article/details/8976006)
  9. [SocketAPI](http://www.cnblogs.com/kesalin/archive/2013/04/13/cocoa_socket.html)

  

