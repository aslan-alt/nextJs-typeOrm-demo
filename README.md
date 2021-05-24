# 初始代码

### 启动数据库
```
mac 
docker run -v "$PWD/blog-data":/var/lib/postgresql/data -p 5432:5432 -e POSTGRES_USER=blog -e POSTGRES_HOST_AUTH_METHOD=trust -d postgres:12.2


docker run -v "blog-data":/var/lib/postgresql/data -p 5432:5432 -e POSTGRES_USER=blog -e POSTGRES_HOST_AUTH_METHOD=trust -d postgres:12.2
```
### 进入数据库
docker exec -it 容器id bash
psql -U blog 登陆psql
\l \c \dt

### 清空之前的开发环境
```
mac
docker kill 容器id
rm -rf blog-data
旧版需要
docker container prune
docker volume rm blog-data
```


#### 创建数据库
create database development_blog
#### 删除数据库
drop database development_blog

## 开发

```bash
yarn dev
# or
npm run dev
```

## 部署

```bash 
yarn build
yarn start
```

