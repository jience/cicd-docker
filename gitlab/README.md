# Gitlab Docker


## 环境

- CentOS7
- Docker-ce 19.03.12
- Docker Compose 1.26.1
- Gitlab Docker Image latest


## 启动Gitlab容器

```
docker-compose up -d
```

或者

```
cd gitlab/

./run.sh
```

## 配置Gitlab

- 修改外部访问地址

```
external_url 'http://主机IP'
```
***注意: 不要添加端口号***