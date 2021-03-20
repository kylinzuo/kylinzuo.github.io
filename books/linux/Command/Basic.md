### 命令基本格式
####命令提示符
>[root@localhost ~]#

```
root            当前登录用户
localhos        主机名
～              当前所在目录（家目录）
#               超级用户的提示符
                普通用户的提示符是$
```
#### 命令格式
> 命令 [选项] [参数]

```
注意： 个别命令使用不遵循此格式
      当有多个选项时，可以写在一起简化
      选项与完整选项 -a 等于 --all
```
#### 文件权限
> -rw-r--r--

```
第一个字符：文件类型（-文件 d目录 l软链接文件）
rw-      r--      r--
u所有者   g所属组   o其他人
r读 w写 x执行  
```
#### 查询目录中的内容： ls
> ls [选项] [文件或目录]

```
选项：
  -a 显示所有文件，包括隐藏文件
  -l 显示详细信息
  -d 查看目录属性
  -h 人性华显示文件大小
  -i 显示inode
```
### 3、文件搜索命令
### 4、帮助命令
### 5、压缩与解压缩命令
### 6、关机和重启命令
### 7、其他常用命令