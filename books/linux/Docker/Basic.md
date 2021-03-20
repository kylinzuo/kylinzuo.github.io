### Docker基础命令

#### 启动容器
> Docker run IMAGE [COMMAND] [ARG...]

```
Docker run --name=容器名称 -i -t IMAGE /bin/bash 
  -i --interative=true|false 默认是false
  -t --tty=true|false 默认是false（打开终端）
  --name 自定义容器名称

以守护形式允许容器
Ctrl+P Ctrl+Q

附加到运行中的容器
docker attach 容器名
```

#### 查看容器
> Docker ps [-a] [-l]

```
-a 所有容器
-l 最新创建的容器

查看容器状态
  Docker inspect [Name | Id]
```

#### 重新启动停止的容器
> Docker start [-i] 容器名

#### 删除停止的容器
> Docker rm 容器名


