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
    index-url=https://pypi.doubanio.com/simple

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


创建第一个python 2 的 virtualenv：

    mkvirtualenv test

创建第一个python 3 的 virtualenv：

    mkvirtualenv -p python3 test

## PyCharm

PyCharm是python最好的集成开发工具，目前有专业版和社区版可供选择。

### 安装pwntools
先更新 homebrew !!官方的巨慢无比

```
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile
```
安装

执行brew install pwntools等待一会就安装完成，会自动解决依赖关系。安装完后会在/usr/local/Cellar/(可能不一样)目录下生成pwntools文件夹，其中python的包在:


/usr/local/Cellar/pwntools/3.6.1/libexec/lib/python2.7/site-packages

/usr/local/Cellar/pwntools/3.6.1/libexec/lib/python2.7/site-packages
 
然后需要把路径添加到python的sys.path中，这里使用的方法是在默认包目录下创建文件mypkpath.pth然后把目录写进去:


$ cd /Library/Python/2.7/site-packages
$ sudo vim mypkpath.pth
$ cat mypkpath.pth
/usr/local/Cellar/pwntools/3.6.1/libexec/lib/python2.7/site-packages

$ cd /Library/Python/2.7/site-packages
$ sudo vim mypkpath.pth
$ cat mypkpath.pth
/usr/local/Cellar/pwntools/3.6.1/libexec/lib/python2.7/site-packages
 
测试

不报错就可以知道安装成功:


$ python
Python 2.7.10 (default, Feb  7 2017, 00:08:15)
[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.34)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> print disasm('b817000000'.decode('hex'), arch = 'amd64')
   0:   b8 17 00 00 00          mov    eax,0x17



$ python
Python 2.7.10 (default, Feb  7 2017, 00:08:15)
[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.34)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> print disasm('b817000000'.decode('hex'), arch = 'amd64')
   0:   b8 17 00 00 00          mov    eax,0x17
 

