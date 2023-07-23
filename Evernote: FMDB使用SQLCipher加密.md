---
title: FMDB使用SQLCipher加密
tags: ["iOS"]
notebook: iOS
---

1.修改FMDatabase.m源码来setKey

2.使用FMDatabase、FMDatabaseQueue在数据库Open之后setKey

###参考
1.[link1](http://yl33643.github.io/blog/2015/09/02/ios-fmdb/)
2.[link2](http://www.jianshu.com/p/c62bb5939512)
3.[link3](http://www.tomatopeter.com/blog/2014/08/31/fmdb-part-3/)
4.[link4](http://stackoverflow.com/questions/33473991/ios-sqlcipher-fmdb-intransaction-file-is-encrypted-or-is-not-a-database)