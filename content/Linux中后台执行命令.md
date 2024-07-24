---
date: 2024-07-24T18:01:13+08:00
lastMod: 2024-07-24T18:05:54+08:00
title: Linux中后台执行命令
---

# 普通用法
nohup sh test.sh &

其中&表示后台运行，但ssh关闭后失效
nohup则让关闭ssh也执行

# 将标准输出和错误输出都打印到output.log

nohup ./test.sh > output.log 2>output.log &

简写
nohup ./test.sh > output.log 2>&1 &
