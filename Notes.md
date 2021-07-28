elasticsearch开启远程访问
### Remote
修改elasticsearch的主配置文件elasticsearch.yml
找到Network区域

为es设置ip绑定，默认是127.0.0.1，也就是默认只能通过127.0.0.1 或者localhost才能访问
将 network.host: 192.168.0.1 修改为 network.host: 0.0.0.0 




下载选项中的 **Debian Linux** 和 **Linux Generic** 都可以使用，后者是 Linux  通用版本。

### mysql5.7 default my.cnf

### min install : [mysqld],[client]

```
# For advice on how to change settings please see
# http://dev.mysql.com/doc/refman/5.7/en/server-configuration-defaults.html

[mysqld]
#
# Remove leading # and set to the amount of RAM for the most important data
# cache in MySQL. Start at 70% of total RAM for dedicated server, else 10%.
# innodb_buffer_pool_size = 128M
#
# Remove leading # to turn on a very important data integrity option: logging
# changes to the binary log between backups.
# log_bin
#
# Remove leading # to set options mainly useful for reporting servers.
# The server defaults are faster for transactions and fast SELECTs.
# Adjust sizes as needed, experiment to find the optimal values.
# join_buffer_size = 128M
# sort_buffer_size = 2M
# read_rnd_buffer_size = 2M
datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock

# Disabling symbolic-links is recommended to prevent assorted security risks
symbolic-links=0

log-error=/var/log/mysqld.log
pid-file=/var/run/mysqld/mysqld.pid
validate_password=OFF

```
### create user default privellage 
USAGE => ALL ?

## Docker install MySQL

### volumes path edit
- /data/db/mysql5.7/my.cnf:/ect/my.cnf => - /data/db/mysql5.7/my.cnf:/etc/mysql/conf.d/my.cnf 

