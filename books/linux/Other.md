### 其他常用命令
挂载命令   
用户登录查看和用户交互命令

#### 1、查询与自动挂载
> mount

```
# 查询系统中已经挂载的设备
```
> mount -a

```
# 依据配置文件/etc/fstab的内容，自动挂载
```

#### 2、挂载命令格式
> mount [-t 文件系统] [-o 特殊选项] 设备文件名 挂载点

```
选项：
  -t 文件系统：加入文件系统类型来指定挂载的类型，可以ext3、ext4、iso9660等文件系统
  -o 特殊选项：可以指定挂载的额外选项
```
特殊选项说明：

参数 | 说明
:- | :-
atime/noatime | 更新访问时间/不更新访问时间。访问分区文件时，是否更新文件的访问时间，默认为更新
async/sync | 异步/同步，默认为同步
auto/noauto | 自动/手动，mount -a命令执行时，是否会自动安装/etc/fstab文件内容挂载，默认为自动
defaults | 定义默认值，相当于rw,suid,dev,exec,auto,nouser,async这七个选项
exec/noexec | 执行/不执行，设定是否允许在文件系统中执行可执行文件，默认是exec允许
remount | 重新挂载已经挂载的文件系统，一般用于指定修改特殊权限
rw/ro | 读写/只读，文件系统挂载时，是否具有读写权限，默认是rw
suid/nosuid | 具有/不具有suid权限，设定文件系统是否具有suid和sgid权限，默认是具有
user/nouser | 允许/不允许普通用户挂载，设定文件系统是否允许普通用户挂载，默认是不允许，只有root可以挂载分区
usrquota | 写入代表文件系统支持用户磁盘配额，默认不支持
grpquota | 写入代表文件系统支持组磁盘配额，默认不支持

#### 3、挂载光盘
> mkdir /mnt/cdrom/

```
# 建立挂载点
```
> mount -t iso9660 /dev/cdrom /mnt/cdrom

```
# 挂载光盘
```
> 简写：mount /dev/sr0 /mnt/cdrom

#### 4、卸载命令
> umount 设备文件名或挂载点   
umount /mnt/cdrom/

