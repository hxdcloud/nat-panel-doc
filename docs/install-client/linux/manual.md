---
sidebar_position: 3
---

# 通过命令行手动安装

**请以root身份登录命令行！**

### 安装基础应用

安装基础组件`wget`、`curl`、`ca-certificates` *已安装可跳过*

在Ubuntu / Debian上安装

```shell script
apt-get -y install curl wget ca-certificates
```

在RHEL / CentOS / Fedora上安装

```shell script
yum -y install curl wget ca-certificates
```

### 下载客户端

不同的处理器架构，客户端文件是不同的。首先查看处理器架构，**若您知道您的处理器架构可跳过此步**。

#### 查看处理器架构

```shell
uname -m
```

![img.png](img/uname-m.png)

如图，我的处理器架构为x86_64，下载客户端时对应的类型为amd64。所有处理器架构对应客户端类型名称请参考下表：

| uname -m返回值 | 客户端对应类型  |
|-------------|----------|
| x86_64      | amd64    |
| amd64       | amd64    |
| armv8       | arm64    |
| aarch64     | arm64    |
| armv7       | arm_v7   |
| armv7l      | arm_v7   |
| armv6l      | arm_v6   |
| armv5tel    | arm_v5   |
| i386        | 386      |
| i686        | 386      |
| mips        | mips     |
| mipsle      | mipsle   |
| mips64      | mips64   |
| mips64le    | mips64le |

未在表格中列出的处理器架构暂无客户端，请联系管理员编译对应版本。

#### 下载对应客户端

这里我以处理器架构为x86_64为例，下载客户端为amd64的版本。**不同处理器架构的请根据上表替换为不同型号的客户端**。

```shell
mkdir -p /etc/hxdcloud # 创建文件夹存放客户端
curl -R -H 'Cache-Control: no-cache' -o /etc/hxdcloud/npc \
https://api.minio.hxdcloud.com/npc/linux_amd64_client # 下载客户端 请将amd64替换为你对应的处理器架构
```

#### 为客户端增加执行权限

```shell
chmod +x /etc/hxdcloud/npc
```

#### 执行安装命令

```shell
/etc/hxdcloud/npc install -vkey=替换成你的vkey
```

#### 启动客户端

```shell
/etc/hxdcloud/npc start
```
