elasticsearch开启远程访问
### Remote
修改elasticsearch的主配置文件elasticsearch.yml

找到Network区域

为es设置ip绑定，默认是127.0.0.1，也就是默认只能通过127.0.0.1 或者localhost才能访问

将 network.host: 192.168.0.1 修改为 network.host: 0.0.0.0 




### min install : [mysqld],[client]

```
