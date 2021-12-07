# rabbitmq


```shell
# 启动
docker-compose up -d
# 进入cli
docker exec -it rabbitmq-38 /bin/bash

# 命令
rabbitmqctl add_user goclub <设置一个安全的密码> 
rabbitmqctl stop
rabbitmqctl start_app
```


```
# 连接地址
amqp://guest:guest@localhost:5672/
```
登录地址

[http://localhost:15672/](http://localhost:15672/)

登录后进入 http://localhost:15672/#/users 管理账号密码