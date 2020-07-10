# Gitlab-Runner Docker


## 环境

- CentOS7
- Docker-ce 19.03.12
- Docker Compose 1.26.1
- Gitlab-runner Docker Image latest


## 启动Gitlab-Runner容器

```
docker-compose up -d
```


## 配置Gitlab-Runner连接上Gitlab

1. 注册gitlab-runner

```
docker exec -it gitlab-runner gitlab-runner register
```

2. Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com/) 输入gitlab的URL.

3. Please enter the gitlab-ci token for this runner 输入gitlab-ci token.

4. Please enter the gitlab-ci description for this runner

5. Please enter the gitlab-ci tags for this runner (comma separated)

6. Please enter the executor: docker+machine, docker-ssh+machine, docker, docker-ssh, parallels, shell, ssh, virtualbox, custom, kubernetes

这一步输入docker就行
```
docker
```

7.Please enter the default Docker image (e.g. ruby:2.6)
