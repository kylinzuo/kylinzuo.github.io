### 文件搜索命令
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
> whereis 命令名

```
# 搜索命令所在路径及帮助文档所在位置
选项：
  -b: 只查找可执行文件
  -m: 只查找帮助文件
```
> which 文件名

```
#搜索命令所在路径及别名
```
#### PATH环境变量
> echo $PATH

```
PATH环境变量：定义的是系统搜索命令的路径
```
#### 文件搜索命令find
> find [搜索范围] [搜索条件] [搜索的文件]

```
find / -name install.log
# 避免大范围搜索，会非常耗费系统资源
# find是在系统当中搜索符合条件的文件名。如果需要匹配，使用通配符匹配，通配符是完全匹配

linux中的通配符：
*     匹配任意内容
?     匹配任意一个字符
[]    匹配任意一个中括号内的字符

find /root -iname install.log
# -iname    不区分大小写

find /root -user root
# -user     按照所有者搜索

find /root -nouser
# -nouser   查找没有所有的者的文件

find /var/log/ -mtime +10
# 查找10天前修改的文件

-10     10天内修改文件
10      10天当天修改的文件
+10     10天前修改的文件

atime   文件访问时间
ctime   改变文件属性
mtime   修改文件内容

find . -size 25k
# 查找当前文件夹内大小是25KB的文件

-25k     小于25KB的文件
25k      等于25KB的文件
+25k     大于25KB的文件
注：注意区分大小写 k M

find . -inum 262422
# 查找当前文件夹内i节点是262422的文件

find /etc -size +20k -a -size -50k
# 查找/etc/目录下，大于20KB并且小于50KB的文件
-a and 逻辑与，两个条件都满足
-o or  逻辑或，两个条件满足一个即可

find /etc -size +20k -a -size -50k -exec ls -lh {} \;
# 查找/etc/目录下，大于20KB并且小于50KB的文件，并显示详细信息
# -exec/-ok 命令 {} \; 对搜索结果执行操作
```
#### 字符串搜索命令grep
> grep [选项] 字符串 文件名

```
# 在文件当中匹配符合条件的字符串
选项：
  -i    忽略大小写
  -v    排除指定字符串
```
#### find命令与grep命令的区别
```
find命令：在系统当中搜索符合条件的文件名，如果需要匹配，使用通配符匹配，通配符是完全匹配
grep命令：在文件当中搜索符合条件的字符串，如果需要匹配，使用正则表达式进行匹配，正则表达式是包含匹配
```