# wordpress-multiple-services-in-one
🛳️ 在单台计算机上管理多个 WordPress 实例，具有灵活的多端口配置。

## 先决条件

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

## 使用方法

1. Clone this repository to your local machine:

``` shell

git clone git@github.com:BruceWind/wordpress-multiple-services-in-one.git
## 下面是示例，您可以更改目标目录名称。
cp wordpress-multiple-services-in-on/ wordpress-multiple-services-in-one-service-1/
cp wordpress-multiple-services-in-on/ wordpress-multiple-services-in-one-service-2
#   进入每个复制的目录：
cd wordpress-multiple-services-in-one-service-1

## 使用 nano 或 vis 更改端口映射。
# vi docker-compose.yml
# 然后，将 8001:80 更改为您想要的任何端口。

#   启动每个服务的命令：
docker-compose up -d

# 完成后，您可以看到服务正在运行。
```

重要的是修改 docker-compose.yml 文件： 调整每个服务的所需 HTTP 端口映射。

### 访问每个 WordPress 实例：

在您的 Web 浏览器中打开并访问 http://localhost:<your-port>，其中 <your-port> 是您为每个 WordPress 服务指定的 HTTP 端口。


### 工作原理：

在启动 WordPress 实例后，只暴露一个 HTTP 端口。数据库容器不需要暴露到端口。这是因为 WordPress 通过内部 Docker 网络连接数据库。

因此，它不仅具有隔离性，而且安全。


### 占用多少内存？

根据我的测试，WordPress + MySQL 占用 300 到 500MB 的内存。对于现代计算机来说，这不是一个大问题。


## Contributing

欢迎贡献！如果您发现任何问题或想添加新功能，请提交拉取请求。