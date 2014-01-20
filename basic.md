# 基本设置

## Alfred

Alfred是Mac平台上使用最频繁的效率工具，被誉为神兵利器。Alfred 2发布以后，在免费版的基础上加入了 Powerpack 模式，引入了工作流的概念，可以做出远比快速启动和自定义搜索更酷的事情。

免费版的Alfred已经可以满足我们的日常需要，极大提高我们的工作效率，常用的功能有：

* 快速查找程序和文件
* 快速搜索互联网
* 快速搜索联系人
* 计算器和字典
* 剪贴板和代码片段
* 强大的扩展功能和工作流

具体的安装和使用方法可以参见[官方网站](http://www.alfredapp.com/)和搜索相关资料。

## iTerm2

Mac是一个具有精致图形界面的Unix平台，作为开发人员，经常会使用到终端(Terminal)或者称作控制台(Console)。系统自带的Terminal程序已经做得不错了，但是iTerm2的功能依然要更强大一些。

具体的安装和使用方法可以参见[官方网站](http://www.iterm2.com/)和搜索相关资料。

## Xcode Command Line Tools

Xcode是Apple的一个开发工具和库集合，Xcode Command Line Tools是Xcode的一部分。安装很多Unix软件都需要使用GCC编译器等开发工具，Xcode Command Line Tools就包含这些工具。

检查Xcode Command Line Tools是否已经安装：

    $ xcode-select -p
    /Library/Developer/CommandLineTools

打开一个终端窗口（Terminal），运行命令：

    xcode-select --install

然后点击"Install"按钮，安装Xcode的命令行工具

## Homebrew

使用郭debian或者RedHat的操作系统的人，一定非常熟悉aptitude或yum包管理工具。在OS X平台下，同样有优秀的Homebrew软件包管理工具，而且这个工具是开源的，可以管理大量Apple没有提供，而你又经常会用到的软件包。

安装Homebrew:

    ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"

更新formulae和Homebrew:

    brew update

搜索某个软件:

    brew search wget

安装某个软件:

    brew install wget

查看需要升级的软件:

    brew outdated

升级所有的软件:

    brew upgrade

升级某个软件:

    brew upgrade wget

删除某个软件:

    brew uninstall wget --force

出错以后的处理:

    brew update
    brew doctor

