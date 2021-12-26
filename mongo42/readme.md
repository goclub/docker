# mongo

> 不建议在生产环境使用,因为MongoDB多文档事务需要在副本集运行,基于 docker 部署副本集 必须对 mongo和 docker有足够的经验
> 如果一旦要在生产环境使用切记修改 docker-compose.yml 中的 `MONGODB_INITIAL_PRIMARY_ROOT_PASSWORD` 和 `MONGODB_ROOT_PASSWORD`  `MONGODB_REPLICA_SET_KEY`

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
mongodb://goclub:goclub@localhost:27017/?authSource=goclub&connect=direct
```