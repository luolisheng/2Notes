Mac上叫Squirrel

### 数据同步

需要同步的是两类数据
1. 第一类：输入法自动生成的用户数据（`/Users/<用户名>/Library/Rime`下的`<词典名>.userdb`文件夹）。包括实际上屏的词汇及次数
2. 第二类：“用户词典”（`<词典名>.dict.yaml`）以及“自定义短语”（`custom_phrase.txt`）。需要用户自己维护
	1. 优先级：自定义短语＞用户数据＞用户词典
3. 第三类：输入发配置文件 `*.custom.yaml`。通过sync_dir文件夹同步，手动拷贝到目标设备Rime文件夹里，再重新部署

### 同步方式

1. 第一类：输入法自带‘用户数据同步’功能。将用户不同设备间的数据进行同步和合并；通过合理算法叠加。
2. 第二类：需要用户自行同步。

### 参考
1. [配置同步](https://utgd.net/article/20231)
2. [配置项](https://www.xiebruce.top/1235.html#i-6)
3. [配置项](https://www.chilisdy.site/post/software/rime-config/)
4. [表情](https://github.com/rime/rime-emoji)
5. [雾凇拼音](https://dvel.me/posts/rime-ice/#%e5%a4%9a%e8%ae%be%e5%a4%87%e5%90%8c%e6%ad%a5)