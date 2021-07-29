ttcp
====

Test TCP, from: http://en.wikipedia.org/wiki/Ttcp


# How to use


测试环境：

>Linux ubuntu 4.15.0-142-generic #146~16.04.1-Ubuntu SMP Tue Apr 13 09:27:15 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux

----

1. 开启接受端

```bash
./ttcp -4r 
```

默认端口5001

2. 开发送端

```bash
./ttcp -4t 127.0.0.1 -p 5001
```

### 查看手册

https://www.cyberciti.biz/faq/linux-unix-creating-a-manpage/

```
man ./ttcp.1 
```

![image-20210729100720644](https://i.loli.net/2021/07/29/dzD1b8264VyFAnO.png)

参考文章：https://www.cyberciti.biz/faq/linux-unix-creating-a-manpage/

执行运行的结果和命令：

PC1:

```bash
dd if=/dev/zero bs=1MB count=1000|./ttcp -4t 127.0.0.1 
```

PC2:

```bash
./ttcp -4r
```

res:

```basic
ttcp-t: buflen=8192, nbuf=2048, align=16384/0, port=5001  tcp  -> 127.0.0.1
ttcp-t: socket
ttcp-t: connect
1000+0 records in
1000+0 records out
1000000000 bytes (1.0 GB, 954 MiB) copied, 17.4342 s, 57.4 MB/s
ttcp-t: 1000000000 bytes in 17.43 real seconds = 56013.34 KB/sec +++
ttcp-t: 122330 I/O calls, msec/call = 0.15, calls/sec = 7016.56
ttcp-t: 0.0user 0.3sys 0:17real 2% 0i+0d 1518maxrss 0+2pf 1739+81146csw
```

说明:

这里的 TTCP 测试的，与陈硕 传输设计的方式是不同的。

![image-20210728103006492](https://i.loli.net/2021/07/28/AJbszq2OfF8yB3i.png)

这里ack 的阶段处理。是不存在的。
