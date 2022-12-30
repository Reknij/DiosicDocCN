---
title: Docker
date: 2022-12-26 22:01:36
categories:
    - 安装方式
---
# 通过Docker安装
## docker-compose
创建一个`docker-compose.yml` 文件并输入以下内容：
```docker
version: "3.9"
services:
  diosic:
    image: jinker25/diosic:latest
    user: 1000:1000
    ports:
      - "3177:3177"
    restart: unless-stopped
    environment:
      LIB_NAME_1: "My library"
    volumes:
      - "/your/data/folder:/data"
      - "/your/library/folder:/library"
```
通过 `docker-compose up -d` 启动容器. 确保`data`和`library`文件夹权限与你的`docker-compose.yml`用户权限相同。

## docker-cli
使用`docker-cli`来启动：
```bash
docker run -d \
    --name diosic \
    -v "/your/data/folder:/data" \
    -v "/your/library/folder:/library" \
    -p "3177:3177" \
    -e LIB_NAME_1=MyLibrary \
    jinker25/diosic:latest
```