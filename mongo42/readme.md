# mongo

> 不要生产环境使用,因为MongoDB多文档事务需要在副本集运行
> 单机模拟的docker副本集用于生产环境是没意义的,因为生产环境的副本集的不同节点应该是不同的主机组成

```shell
# 启动
docker-compose up -d
# 进入管理cli
docker exec -it mongo42_mongodb-primary_1 mongo admin
# 认证登录管理员
db.auth('root', "root")
# 创建数据库
use goclub
# 创建用户
db.createUser({user: 'goclub', pwd: "goclub", roles: [ { role: "readWrite", db: "goclub" } ] })
```

```
# 本地开发阶段连接主副本地址 (注意为了本地便于测试开启了 connect=direct )
mongodb://goclub:goclub@localhost:27017/?authSource=goclub&readPreference=primary&directConnection=true&ssl=false
```
