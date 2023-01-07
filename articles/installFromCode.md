---
title: 自行编译
date: 2022-12-26 22:01:36
categories:
    - 安装方式
---
# 自行编译安装
## 下载源码
1. `git clone https://github.com/Reknij/diosic`
2. `cd diosic`

运行上述命令将从`GitHub`下载源码并进入源码所在目录。

## 后端服务器
1. 运行`cd server`进入后端源代码并运行以下命令：
    ```
    cargo build --release
    ```
2. 根据你的编译平台将`diosic`或`diosic.exe`程序文件复制到你想要的目录中。

    例如在linux平台下编译后复制到根目录：
    ```
    cp ./target/release/diosic /diosic
    ```

## 前端网页
若想要*Diosic*网页，记得也编译前端。

1. 在`server`目录下运行`cd web`进入源代码所在目录并运行以下命令：
    ```
    npm install
    npm run build
    ```
2. 将`./dist`目录复制到后端`diosic`程序所在目录并改名为`webpage`。例如`diosic`程序在根目录下：
    ```
    mkdir /webpage
    cp -r dist/* /webpage 
    ```
    
# 运行
将参数传给`diosic`文件程序以启动：
```
/diosic -d /your_data_directory -l "your_library_name;your_library_directory"
```
其中参数含义如下：
- `-d` 为你的`data`目录，关于缓存以及数据文件放置的地方。
- `-l` 为你的媒体库名称以及目录。格式为`名称;目录`。例如`我的音乐;/music`

# 结果
打开浏览器输入你的ip地址加端口号`3177`即可打开`Diosic Web`：
```
http://127.0.0.1:3177
```