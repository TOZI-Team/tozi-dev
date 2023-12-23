---
title: "pip换源"
date: "2023-12-23"
description: "通过简单、易用的技术框架创建QQ机器人"
authors :
  - "jun"
---
## 临时换源 
### 清华源 
```shell
pip3 install package-name -i https://pypi.tuna.tsinghua.edu.cn/simple 
```

### 阿里源 
```shell
pip3 install package-name -i https://mirrors.aliyun.com/pypi/simple/ 
```

### 腾讯源 
```shell
pip3 install package-name -i http://mirrors.cloud.tencent.com/pypi/simple 
```

### 豆瓣源 
```shell
pip3 install package-name -i http://pypi.douban.com/simple/ 
```

 
## 永久换源 
### 清华源 
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple 
### 阿里源 
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/ 
### 腾讯源 
pip config set global.index-url http://mirrors.cloud.tencent.com/pypi/simple 
### 豆瓣源 
pip config set global.index-url http://pypi.douban.com/simple/ 
 
 
## 换回默认源 
pip config unset global.index-url 
 