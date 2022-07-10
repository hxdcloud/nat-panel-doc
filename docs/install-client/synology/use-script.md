---
sidebar_position: 1
---

# 通过一键脚本安装

### 进入命令行

群晖进入命令行请参考[官网教程](https://kb.synology.cn/zh-cn/DSM/tutorial/How_to_login_to_DSM_with_root_permission_via_SSH_Telnet)

### 下载一键脚本

```shell script
wget -N --no-check-certificate https://api.minio.hxdcloud.com/npc/npc_syno_install.sh && chmod +x npc_syno_install.sh && bash npc_syno_install.sh
```



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

### 下载并运行一键脚本

```shell script
wget -N --no-check-certificate https://api.minio.hxdcloud.com/npc/npc_install.sh && chmod +x npc_install.sh && bash npc_install.sh
```

![synology一键脚本菜单](img/synology-script.jpg)

+ 按照菜单提示，安装hxdcloud内网穿透客户端
+ 服务器地址和端口可以直接回车，后续会自动获取。若需要指定连接的服务器请参考[手动指定服务器](../specify)
+ 输入连接密钥完成安装

**若出现无法安装、无法连接等问题，请在脚本中选择查看实时日志，将日志内容发送给管理员**