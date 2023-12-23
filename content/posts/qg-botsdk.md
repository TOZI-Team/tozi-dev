---
title: "使用QG-Botsdk创建你的QQ机器人"
date: "2023-12-23"
description: "通过简单、易用的技术框架创建QQ机器人"
authors :
  - "yms"
---

最近，腾讯宣布新版本QQ BOT-API正式支持群、频道与私信，且**支持个人开发者申请**。虽然腾讯提供了python SDK，但是整体使用异步技术，使用需要一定门槛，而本文介绍的`QG-botsdk`则很好的将丰富的功能与简单的技术要求相结合。

## 安装
QG-botsdk支持通过PYPI安装：
```shell
pip3 install qg-botsdk
```
当然，你也可以从Github获取最新版本：
```shell
git clone git@github.com:GLGDLY/qg_botsdk.git
cd qg_botsdk
python3 ./setup.py install
```

