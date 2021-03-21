### Docker Container

#### 启动容器
```
$ docker run IMAGE [COMMAND] [ARG...]

docker run --name=容器名称 -i -t [--rm] IMAGE bash 
  -i --interative=true|false 默认是false
  -t --tty=true|false 默认是false（打开终端）
  --name 自定义容器名称
  --rm 容器退出后随之将其删除
  -P --publish-all=true|false 默认是false 对容器暴露的所有端口进行映射
  -p --publish=[] 指定具体端口的映射
    docker run -p 80 -i -t ngnix bash
    docker run -p 8080:80 -i -t ngnix bash
    docker run -p 0.0.0.0:80 -i -t ngnix bash
    docker run -p 0.0.0.0:8080:80 -i -t ngnix bash

以守护形式允许容器
Ctrl+P Ctrl+Q

附加到运行中的容器
docker attach 容器名
```

#### 启动守护式容器
```
$ docker run -d IMAGE [COMMAND] [ARG...]
-d 以后台模式启动容器
```

#### 查看容器
```
$ docker ps [-a] [-l]
-a 所有容器
-l 最新创建的容器

查看容器状态
  docker inspect [Name | Id]
```

#### 重新启动停止的容器
```
$ docker start [-i] 容器名
```

#### 删除停止的容器
```
$ docker rm 容器名
```

#### 查看容器日志

```
$ docker logs [-f] [-t] [-tail] 容器名
-f --follows=true|false 默认为false
-t --timestamps=true|false 默认为false
--tail="all"
```

#### 查看容器内进程
```
$ docker top 容器名
```

#### 在运行中的容器内启动新的进程
```
$ docker exec [-d] [-i] [-t] 容器名 [COMMAND] [ARG...]
```

#### 停止守护式容器
```
$ docker stop 容器名
$ docker kill 容器名
```

#### Docker帮助文档
```
man docker-run
man docker-logs
man docker-top
man docker-exec
```