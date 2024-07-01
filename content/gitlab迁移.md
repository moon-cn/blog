---
title: gitlab迁移
date: 2024-07-01
---
# 背景
docker-compose部署

# 安装
将 docker-compose.yml 拷贝到新机器上，启动

#  备份

```
docker exec gitlab14 gitlab-backup create
```

#  还原
```
docker exec gitlab14 gitlab-backup restore
```
