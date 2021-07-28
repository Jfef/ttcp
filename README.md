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

