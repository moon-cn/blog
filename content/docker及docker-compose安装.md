---
title: docker及docker-compose安装
date: 2024-07-01
---

# 安装docker
## 官网安装链接
https://docs.docker.com/engine/install/centos/
## 网络有问题的情况

### 安装
```shell
sudo yum-config-manager     --add-repo     https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
### 启动
```shell
sudo systemctl start docker
```


# 安装 docker-compose
## 网络有问题的情况
### 安装
```shell
sudo curl -L "https://github.com/docker/compose/releases/download/v2.28.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
### 验证版本
```shell
docker-compose --version
```
