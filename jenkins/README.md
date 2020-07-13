# Jenkins Docker

## 环境

- CentOS7
- Docker-ce 19.03.12
- Docker Compose 1.26.1
- Jenkins Docker Image jenkins/jenkins:lts


## 启动Jenkins容器

```
docker-compose up -d
```

或者

```
cd jenkins/

sh run.sh
```

## 注意事项

- Jenkins log文件没有权限

出现如下提示:
```
touch: cannot touch '/var/jenkins_home/copy_reference_file.log': Permission denied

Can not write to /var/jenkins_home/copy_reference_file.log. Wrong volume permissions?
```

需要修改下目录权限, 因为当映射本地数据卷时，/home/zzjz/jenkins目录的拥有者为root用户，而容器中jenkins user的uid为1000
执行如下命令即可：
```
chown -R 1000:1000 /home/zzjz/jenkins
```

- Jenkins容器采用宿主机的docker和docker-compose命令

> 在Jenkins容器启动时需要添加如下挂在卷,并且设置 user: root或者将jenkins用户添加到docker组中

```
user: root  # 表示在容器中以 root 用户运行
- /var/run/docker.sock:/var/run/docker.sock
- /usr/bin/docker:/usr/bin/docker
- /usr/local/bin/docker-compose:/usr/local/bin/docker-compose
```

## 外部链接

[Docker Jenkins](https://hub.docker.com/_/jenkins?tab=description)

[Docker Jenkins:LTS](https://hub.docker.com/r/jenkins/jenkins)

[Docker Jenkins Doc](https://github.com/jenkinsci/docker/blob/master/README.md)