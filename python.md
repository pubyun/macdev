# python开发环境的设置

## Python (可选)

虽然Mac OS X 自带了Python，但是我们可以选择使用Homebrew安装Python 2.7.x。因为：

* 使用Homebrew安装更新的python版本
* 同时安装2.7.x和3.x的python
* Homebrew会同时安装setuptools和pip等工具

安装python 2.7.x：

    brew install python --with-brewed-openssl

安装python 3.x：

    brew install python3 --with-brewed-openssl

## pip

我们使用pip来管理软件包：

    sudo easy_install pip

由于pip从pypi下载软件包，境外的pypi站点非常慢，导致安装缓慢或者下载失败。所幸清华大学和豆瓣都提供了pypi镜像，可以通过下面的配置文件来配置：

    $ vim ~/.pip/pip.conf
    ; http://www.pypi-mirrors.org/
    [global]
    use-mirrors=true
    mirrors=http://pypi.douban.com
    index-url=http://pypi.douban.com/simple

## virtualenv virtualenvwrapper

安装软件包：

    sudo pip install virtualenv virtualenvwrapper

创建virtualenv目录：

    mkdir ~/virtualenvs

在.zshrc或者.bash_profile里配置virtualenv:

    # virtualenvwrapper
    export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python
    export WORKON_HOME=~/virtualenvs
    [ -f /usr/local/bin/virtualenvwrapper.sh ] && source /usr/local/bin/virtualenvwrapper.sh
    [ -f /etc/bash_completion.d/virtualenvwrapper ] && source /etc/bash_completion.d/virtualenvwrapper
    export PIP_VIRTUALENV_BASE=$WORKON_HOME
    export PIP_RESPECT_VIRTUALENV=true


创建第一个virtualenv：

    mkvirtualenv --no-site-packages test

## PyCharm

PyCharm是python最好的集成开发工具，目前有专业版和社区版可供选择。


