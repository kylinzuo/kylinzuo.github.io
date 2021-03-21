### Docker Image

#### 查找镜像
```
Docker hub
  https://registry.hub.docker.com/
  https://hub.daocloud.io/

$ docker search [OPTIONS] TERM
--automated=false Only show automated builds
--no-trunc=false Don't truncate output
-s --stars=0 Only display with at least X stars
```

#### 拉取镜像
```
$ docker pull [OPTIONS] NAME[:TAG]
-a --all-tags=false Download all tagged images in the repository
```

#### 使用--registry-mirror
```
1. 修改: /eth/default/docker
2. 添加: DOCKER_OPTS="--registry-mirror=https://MIRROR-ADDR"
```

#### 推送镜像
```
docker push NAME:[TAG]
```

#### 查看镜像
```
$ docker images [options] [repository]
-a --all=false 显示所有镜像
-f --filter=[] 筛选条件
--no-trunc=false 显示网站 Image ID
-q --quiet=false 只显示Image ID
```

#### 查看镜像详细信息
```
$ docker inspect [OPTIONS] Container|Image
-f --format=""
```

#### 删除镜像
```
$ docker rmi [OPTIONS] IMAGE
-f --force=false Force remove of the Image
--no-prune=false Do not delete untagged parents
```

#### 删除所有镜像
```
$ docker rmi $(docker image -q)
```

#### 构建镜像
```
通过容器
$ docker commit [OPTIONS] CONTAINER [Repository[:Tag]]
  -a --author="" Author
  -m --message="" Commit message
  -p --pause=true Pause container during commit

通过Dockerfile构建
$ docker build [OPTIONS] PATH|URL|-
  --force-rm=false
  --no-cache=false
  --pull=false
  -q --quiet=false
  --rm=true
  -t --tag=""
```