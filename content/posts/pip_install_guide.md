---
title: "Python包管理工具PIP的使用指南"
date: 2024-06-23T14:00:00+08:00
tags: ["Python", "pip"]
series: ["Python入门"]
series_order: 2
authors :
  - "yms"
---
> **包管理器**，是现代项目管理的重要组成部分，许多现代编程语言也会推出统一的包管理器以提升开发者体验，如rust 的`cargo`，nodejs 的`npm`，arkts 的`ohpm`等等。
> *Python* 作为一门很“新”的语言，自然也提供包管理功能。

# Python包管理的前世今生
如果要提到Python的包管理，那么必定绕不开**PYPI**（Python Package Index，中文：Python 包索引）。其由 Tarek Ziade 在2003年发起，起初只是一个简单的仓库用来存储和分发 Python 软件包，但随着时间推移，PYPI 逐步完善，成为我们现在所看见的 PYPI.org。
![image](https://img2024.cnblogs.com/blog/3418689/202406/3418689-20240623134020925-500349057.png)
回归正题，Python 早期并没有包管理工具，开发者需要手动从PYPI上下载源代码，构建，最后放置到`site-packages`文件夹。这种情况持续到2004年，Jim Hugunin创建了`easy_install`工具，极大地改善了这个过程，当然其也有很多问题。

------------

2008年，Jason R. Coombs发起`pip`项目，其相较`easy_install`，依赖管理更加优秀，并且引入了虚拟环境的概念，解决了全局包冲突的问题。2014年，*Python Software Foundation*宣布将pip作为官方推荐的包管理器，并将其集成到Python的标准库中。这意味着所有新版本的Python都将自带pip，使得安装和管理包变得更加方便。

# 安装PIP
pip现已集成至部分版本的 Python 安装包中，你可以通过如下命令检查当前是否已安装 Python：
```shell
python -m pip --version
```
如果该命令执行出错，那么你可能需要考虑自行安装 pip。

------------


pip作为python的重要组件，其安装相对比较简单。您可以通过执行[get-pip.py]( https://bootstrap.pypa.io/get-pip.py "get-pip.py")文件，在任意Python环境中安装pip。当然，你也可以使用以下针对各个操作系统（发行版）的特定安装方法：
## ArchLinux(Pacman)
对于使用 Pacman 管理包的 Linux 发行版，你可以通过如下命令安装 pip：
```shell
sudo pacman -Syu python-pip
```
## Debian(Apt)
Debian 与其衍生发行版提供了 Python2 与 Python3 两个版本的pip，你可以通过如下命令分别安装它们：
```bash
sudo apt-get install python-pip # python2
sudo apt-get install python3-pip # python3
```
# 使用PIP
`pip`的使用场景有很多，这里就一个使用场景进行简单的演示：
- 管理项目依赖
## 管理项目依赖
### 从 默认的 PyPi 源安装
```
pip install <package-name>
```
例如，要安装一个名为 requests 的包，可以使用下面的命令：
```
pip install requests
```
默认安装最新版。要安装指定版本：
```
pip install requests==1.0.0
```
### 从指定地址（本地或Git仓库）安装
从本地安装
```
pip install /local/path/to/a/package
```
从 Git 仓库安装
```
pip install pip install git+https://github.com/user-name/repo-name.git
```
从依赖列表文件批量安装
假设文件名是 requirements.txt，
```
pip install -r requirements.txt
```
更多选项：

使用 `-t` 选项安装到指定路径
使用 `-e` 选项从随时更新变化的软件包源码安装(开发中的软件包)
安装依赖包的更多详情可参考官方文档，例如从本地索引源或其它镜像索引查找和安装包。

查看已安装的包信息
```
pip show <package-name>
```
例如，要查看 numpy 包的信息，可以使用下面的命令：
```
pip show numpy
```
这样，pip 就会显示 numpy 包的相关信息，例如包名、版本、依赖等。

### 升级依赖包
```
pip install --upgrade <package-name>
```
例如，要升级 numpy 包到最新版本，可以使用下面的命令：
pip install --upgrade numpy

### 删除依赖包
```
pip uninstall <package-name>
```
例如，要删除 numpy 包，可以使用下面的命令：
```
pip uninstall numpy
```
### 列出已安装的依赖包信息
```shell
pip list
```
可以使用一些参数来过滤包。例如，可以使用 `-o` 或 `--outdated` 参数来列出所有已过期的包，使用 `-u` 或 `--uptodate` 参数来列出所有已更新的包。

### 导出依赖包信息
```
pip freeze
```
输出到 requirements.txt 文件
```
pip freeze > requirements.txt
```
# 后记
关于pip的更多用法，你可以查阅pip的[官方文档](https://pip.pypa.io/en/stable/ "官方文档")。