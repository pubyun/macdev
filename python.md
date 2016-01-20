# python开发环境的设置
## Configuration of the development environment of Python

## Python (可选)
## Python (optional)
虽然Mac OS X 自带了Python，但是我们可以选择使用Homebrew安装Python 2.7.x。因为：
Although Mac OS X comes with Python, we can use Homebrew to intall Python 2.7.x because

* 使用Homebrew安装更新的Python版本 
* Use Homebrew to install more recent version of Python
* 同时安装2.7.x和3.x的Python 
* Intall Python 2.7.x and 3.x at the same time
* Homebrew会同时安装setuptools和pip等工具 
* Homebrew will install tools like setuptools and pip

安装Python 2.7.x：To install Python 2.7.x

    brew install python --with-brewed-openssl

安装Python 3.x：To install Python 3.x

    brew install python3 --with-brewed-openssl

## pip

我们使用pip来管理软件包：We use pip to manage packages:

    sudo easy_install pip

由于pip从pypi下载软件包，境外的pypi站点非常慢，导致安装缓慢或者下载失败。所幸清华大学和豆瓣都提供了pypi镜像，可以通过下面的配置文件来配置：Scripts below are for Chinese users only to improve the download speed

    $ vim ~/.pip/pip.conf
    ; http://www.pypi-mirrors.org/
    [global]
    use-mirrors=true
    mirrors=http://pypi.douban.com
    index-url=http://pypi.douban.com/simple

## virtualenv virtualenvwrapper

安装软件包：To install packages: 

    sudo pip install virtualenv virtualenvwrapper

创建virtualenv目录：To create the virtualenv folder

    mkdir ~/virtualenvs

在.zshrc或者.bash_profile里配置virtualenv: To config virtualenv in .zshrc or .bash_profile

    # virtualenvwrapper
    export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python
    export WORKON_HOME=~/virtualenvs
    [ -f /usr/local/bin/virtualenvwrapper.sh ] && source /usr/local/bin/virtualenvwrapper.sh
    [ -f /etc/bash_completion.d/virtualenvwrapper ] && source /etc/bash_completion.d/virtualenvwrapper
    export PIP_VIRTUALENV_BASE=$WORKON_HOME
    export PIP_RESPECT_VIRTUALENV=true


创建第一个virtualenv：To create the first virtualenv:

    mkvirtualenv --no-site-packages test

## PyCharm

PyCharm是Python最好的集成开发工具，目前有专业版和社区版可供选择。
PyCharm is the best Python IDE so far. There are community and professional versions for you to choose.

