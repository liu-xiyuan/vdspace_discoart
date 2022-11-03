# 环境配置

## 需具备技能

- 阿里云子账户操作服务器
- 重置系统、配置系统、配置源环境等高危险性操作
- Docker的基本操作
- Linux基本命令
- Jupyter Notebook
- screen命令

## 实际操作

### 项目简介

- jina-ai/**[discoart](https://github.com/jina-ai/discoart)**

本项目用于Disco Diffusion快速部署，让使用者开源专注于创作而不是代码、使用Docker进行部署，具有高可用性和可维护性。除了能够快速部署Jupyter notebook外，还可以快速构建服务于w/o、TLS、事后分析、API等更大的跨模式或多模式应用程序。这适用于自托管、Google Colab、系统集成、非 GUI 环境。

## 实际操作

在一台纯净的Ubuntu 20 TLS上，安装好CUDA、CNN（阿里云会在重置镜像时，自动安装）等GPU服务器基本环境。

PS:``nvida-smi``验证是否成功安装CUDA环境

### 安装Docker

基本工具安装

```
apt update
apt-get install ca-certificates curl gnupg lsb-release
```

安装证书

```
curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
```

写入软件源信息

```
sudo add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
```

安装Docker

```
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

启动docker

```
systemctl start docker
```

安装工具

```
apt-get -y install apt-transport-https ca-certificates curl software-properties-common
```

重启docker

```
service docker restart
```

查看docker版本，并运行Docker.hello-world验证是否安装成功

```
sudo docker version
docker run hello-world
```

### 部署

将jina-ai/**[discoart](https://github.com/jina-ai/discoart)** pull到本地

```
apt install -y screen
```

利用screen创建一个shell窗口

```
screen -S pull-disco
```

从南京大学源下载该镜像，并等待其拉取完毕

```
docker pull docker.nju.edu.cn/jinaai/discoart
```

拉取完成后退出并杀掉该窗口

```
exit
```

### 安装nvidia-container

将下面添加软件源的脚本放到任意位置

```
# nvidia-container-runtime-script.sh

sudo curl -s -L https://nvidia.github.io/nvidia-container-runtime/gpgkey | \
  sudo apt-key add -
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
sudo curl -s -L https://nvidia.github.io/nvidia-container-runtime/$distribution/nvidia-container-runtime.list | \
  sudo tee /etc/apt/sources.list.d/nvidia-container-runtime.list
sudo apt-get update
```

执行脚本

```
sudo sh nvidia-container-runtime-script.sh
```

安装

```
sudo apt-get install nvidia-container-runtime
```

### 运行Jupyter notebook

创建新的窗口用于后台运行discoart

```
screen -S discoart
```

运行

```
docker run -p 51000:8888 -v $(pwd):/home/jovyan/ -v $HOME/.cache:/root/.cache --gpus all jinaai/discoart
```

双GPU运行

```
docker run -p 51000:8888 -v $(pwd):/home/jovyan/ -v $HOME/.cache:/root/.cache --gpus '"device=0,2"' --shm-size 32g jinaai/discoart
```

现在你可以在`http://127.0.0.1:51000` 访问

在此步，请将生成的Token记录好

退出该新窗口``ctrl+a d``

# 联系方式

Email:AydenLi@qq.com

WeChat:AydenLiii
