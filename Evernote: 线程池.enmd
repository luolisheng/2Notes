### 自定义线程池
1. [link1](https://www.cnblogs.com/yangang92/p/5485868.html)
2. [link2](https://everettjf.github.io/2018/08/12/a-simple-cpp-thread-pool/)

### 线程池确定线程数量

##  线程池中线程数量跟所要处理的任务性质相关
1. 任务性质：
	1. CPU密集型任务（科学计算）
		* 尽可能配置少的线程，如CPU个数+1
	2. IO密集型任务（文件处理）
		* 尽可能配置多的线程，如两倍CPU个数+1
		* IO操作需要大量内存和存储，CPU大部分时间只是在等待处理信号，不要让CPU闲下来
	3. 混合型任务
		* 拆分任务分别处理
2. 任务的优先级：高中低
3. 任务执行时长：长中短
4. 任务的依赖性：是否依赖其他系统资源（数据库连接）
	* 某任务依赖数据库返回结果，等待时间越长CPU空闲时间越长，应该加大线程数量
	* 线程等待时间占比越高，说明CPU空闲时间越多，应该加大线程数量
	* 线程CPU时间占比越高，说明CPU比较繁忙，应该减少线程数量

1. [link1](https://blog.csdn.net/bian_qing_quan11/article/details/78030016)
2. [link2](https://blog.csdn.net/huangjin0507/article/details/51879705)
