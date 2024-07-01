---
title: gitlab迁移
date: 2024-07-01
---
# 背景
docker-compose部署

# 安装
以下文件拷贝到新机器上

docker-compose.yml 

启动后，拷贝

gitlab.rb

再重启


#  备份

```
docker exec gitlab14 gitlab-backup create
```

#  还原
拷贝备份文件到新机器

执行还原命令
```
docker exec gitlab14 gitlab-backup restore
```
