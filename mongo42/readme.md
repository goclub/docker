# mongo

```shell
# 启动
docker-compose up -d
# 进入管理cli
docker exec -it mongo-42 mongo admin
# 创建管理员
db.createUser({pwd: "设置一个安全的管理员密码",  user: 'root', roles: [ { role: "root", db: "admin" } ] })
# 退出
exit

# 进入管理cli
docker exec -it mongo-42 mongo admin
# 认证登录管理员
db.auth('root', "输入刚才设置的管理员密码")
# 创建数据库
use goclub
# 创建用户
db.createUser({pwd: "设置一个安全的用户密码", user: 'goclub',  roles: [ { role: "readWrite", db: "goclub" } ] })
```

```
# 连接地址
mongodb://goclub:输入刚才设置的用户密码@localhost:27017/goclub?authSource=goclub&readPreference=primary&appname=MongoDB%20Compass&directConnection=true&ssl=false
```