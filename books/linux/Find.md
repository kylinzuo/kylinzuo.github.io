### 3、文件搜索命令
#### 文件搜索命令locate
> locate 文件名

```
在后台数据库中按文件名搜索，搜索速度更快

/var/lib/mlocate
#locate命令所搜索的后台数据库

updatedb
更新数据库

locate配置文件 /etc/updatedb.conf
PRUNE_BIND_MOUNTS = "yes"
# 开启搜索限制
PRUNEFS = 
# 搜索时，不搜索的文件系统
PRUNENAMES = 
# 搜索时，不搜索的文件类型
PRUNEPATHS = 
# 搜索时，不搜索的路径
```
#### 命令搜索命令whereis与which
#### 文件搜索命令find
#### 字符串搜索命令grep
#### find命令与grep命令的区别