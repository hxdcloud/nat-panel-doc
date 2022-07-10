---
sidebar_position: 3
---

# 通过docker安装

### 安装docker

如果您的linux设备支持安装docker(amd64,armv8架构)，可以使用以下命令一键安装docker
```shell script
curl -fsSL https://get.docker.com | bash -s docker
```

然后将docker添加到系统服务，并设置为开机启动

```shell script
systemctl enable docker
systemctl start docker
```

### 启动客户端

```shell script
docker run -d --net=host --name=hxdcloud-npc --restart=always hxdcloud/npc -vkey=替换成你的vkey
```

### 查看客户端日志

```shell script
docker logs -f hxdcloud-npc
```

### 删除客户端

```shell script
docker rm -f hxdcloud-npc
```