### 关机与重启命令

#### 1.shutdown命令（推荐）
> shutdown [选项] 时间

```
-c: 取消一个关机命令
-h: 关机
-r: 重启
```
#### 2.其他关机命令（不推荐）
> halt、poweroff、init 0

#### 3.其他重启命令
> reboot、init 6

#### 4、系统运行级别
```
0     关机
1     单用户
2     不完全多用户，不含NFS服务
3     完全多用户
4     未分配
5     图形界面
6     重启
```
> cat /etc/inittab

```
# 修改系统默认运行级别
id:3:initdefault:
```
> runlevel

```
# 查询系统运行级别
```
#### 5.退出登录命令
> logout