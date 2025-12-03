---
title: 关于Nginx请求URL自动添加斜杠的端口问题
cid: 6
type: post
created: 1741186688
modified: 1741186688
slug: 6
---

最近在使用Nginx做了两层，第一层为用户访问的Nginx反向代理，监听端口为80，第二层为处理本地静态文件、并将json数据请求代理到apche，监听端口为8080。在测试的过程中，发现一个小问题，就是当请求的URL没有斜杠时，会自动默认301跳，转添加斜杠/，通过Location跳转，跳转时带上了后端nginx的端口.

配置项

```
# absolute_redirect on;
server_name_in_redirect off;
port_in_redirect off;
```
