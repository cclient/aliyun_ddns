### Env

解析设置 abc.com

|记录类型|主机记录|解析线路(isp)|记录值|MX优先级|TTL|状态|操作|
|-------|-----:|-----:|-----:|-----:|-----:|-----:|:----:|
| A    | blog  |  默认  |127.0.0.1    |--    |10 分钟|	正常    |修改暂停删除备注

DomainName=abc.com

RRKeyWord=blog

TypeKeyWord=A


### Deploy

#### image 

[https://hub.docker.com/r/cuidapeng/aliyun-ddns/](https://hub.docker.com/r/cuidapeng/aliyun-ddns/) for x86

[https://hub.docker.com/r/cuidapeng/arm32v7-aliyun-ddns/](https://hub.docker.com/r/cuidapeng/arm32v7-aliyun-ddns/) for arm like raspberry pi

#### run docker contain

`docker run -d --name aliyun-ddns -e ACCESS_KEY={access_key} -e ACCESS_SECRET={access_secret} -e DomainName=abc.com  -e RRKeyWord=blog  -e TypeKeyWord=A cuidapeng/arm32v7-aliyun-ddns`


### Add Cron

` */5 * * * * /usr/bin/docker restart aliyun-ddns`
