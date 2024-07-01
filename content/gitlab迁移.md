---
title: gitlab迁移
date: 2024-07-01
---
# 背景
docker-compose部署, 容器名为gitlab14，每条命令前， 需添加 docker exec -it gitlab14

# 安装
以下文件拷贝到新机器上

docker-compose.yml 

启动后，拷贝

gitlab.rb

再重启
```
gitlab-ctl reconfigure
gitlab-ctl restart
```

#  备份

```
gitlab-backup create
itlab-ctl restart
```

#  还原
https://docs.gitlab.com/ee/administration/backup_restore/restore_gitlab.html

拷贝备份文件到新机器

执行还原命令
```
docker exec -it gitlab14 gitlab-ctl stop puma
docker exec -it gitlab14 gitlab-ctl stop sidekiq

# Verify that the processes are all down before continuing
docker exec -it gitlab14 gitlab-ctl status

docker exec -it gitlab14 gitlab-backup restore BACKUP=1719820488_2024_07_01_17.1.1_gitlab_backup.tar

docker restart gitlab14
```
