# 安装Docker

1. 环境Linux

2. 安装参考官网https://docs.docker.com/engine/install/

3. 配置阿里云镜像仓库yum-config-manager --add repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

4. 验证安装：docker version

   ![image-20210807091728469](D:\Java学习笔记\Docker\image-20210807091728469.png)

5. 运行验证：docker run hello-world

   ![image-20210807091553873](D:\Java学习笔记\Docker\image-20210807091553873.png)

# Docker的常用命令

## 帮助命令

```shell
docker version        # 显示版本信息
docker info           # 显示docker的系统信息，包括镜像和容器
docker COMMAND --help # 帮助命令
```

帮助文档地址：https://docs.docker.com/engine/reference/commandline/info/

## 镜像命令

docker image # 查看所有本地的主机上的镜像

docker search 镜像名字 # 搜索镜像

docker pull 镜像名字 # 下载镜像

docker rmi

 # 删除镜像

