清空GIT提交历史
提交记录太乱，很多文件(或者二进制文件）导致存储很大，这时想清空GIT历史怎么做？

简单粗暴的方式是删除仓库，再重新创建仓库。
使用GIT命令，假设需清空master分支提交历史

```

# 检出一个新分支如temp，且不带提交历史
git checkout --orphan temp

# 删除master分支
git branch -D master

# 重命名当前分支为master
git branch -m master

# 添加提交
git add .
git commit -m 'init'


# 强制推送（有些仓库需开启允许）
git push -f origin master


```