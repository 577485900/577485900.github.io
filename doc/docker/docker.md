#### Docker 架构
- Docker 镜像：Images
- Docker 容器：Container
- Docker 客户端：Client
- Docker 主机：Host
- Docker 仓库：Registry
- Docker Machine
#### Docker 安装
- Win10 系统
    - 开启Hyper-V
    - 开启CPU虚拟化
#### Docker 命令
- docker
- docker container --help
- docker --version
- docker version
- docker info
- docker run hello-world
- docker image ls
- docker container ls
- docker container ls --all
- docker container ls -aq
- 容器生命周期管理
    - Docker run：创建一个新的容器并运行一个命令
    ```
    docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
    ```
- Docker version：显示 Docker 版本信息
```
docker version [OPTIONS]
```
- Docker info：显示 Docker 系统信息
```
docker info [OPTIONS]
```
- Docker images：列出本地镜像
```
docker images [OPTIONS] [REPOSITORY[:TAG]]
```