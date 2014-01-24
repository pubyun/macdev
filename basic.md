# 基本设置

## Alfred

Alfred是Mac平台上使用最频繁的效率工具，被誉为神兵利器。Alfred 2发布以后，在免费版的基础上加入了Powerpack模式，引入了工作流的概念，可以做出远比快速启动和自定义搜索更酷的事情。

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

打开一个终端窗口(Terminal)，运行命令：

    xcode-select --install

然后点击"Install"按钮，安装Xcode的命令行工具

## Homebrew

使用过Debian或者RedHat的操作系统的人，一定非常熟悉aptitude或yum包管理工具。在OS X平台下，同样有优秀的Homebrew软件包管理工具，而且这个工具是开源的，可以管理大量Apple没有提供，而你又经常会用到的开源软件包。Homebrew为Mac OS X提供了非常方便的软件安装方式，解决了包的依赖问题，不再需要烦人的sudo，一键式编译，无参数困扰。

由于Homebrew的安装方式可能变化，请到[官方网站](http://brew.sh)查看最新的方法和文档。

安装Homebrew:

    ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
    brew doctor

更新formulae和Homebrew:

    brew update

显示已经安装的软件列表:

    brew list

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

查看软件包信息:

    brew info wget

列出软件包的依赖关系:

    brew deps wget

出错以后的处理:

    brew update
    brew doctor

## homebrew-cask

通常OS X下二进制软件是通过App Store安装的，homebrew-cask是一个基于HomeBrew的软件安装程序，使用homebrew-cask可以在命令行下安装软件包，相对Mac App Store，还有一些优势：

* 安装软件体验一致、简洁、优雅、快速
* 对常用软件支持更全面，例如MPlayerX已经宣布不在更新Mac App Store上的版本
* 软件更新速度快。例如Alfred 2.0已经出了很久，但在Mac App Store上还是1.2版本，QQ也是这样的情况
* Mac App Store生态圈远不完善，审核流程过长，限制太多，维护成本过高让很多应用开发者被迫离开。

homebrew-cask和Homebrew的区别：

* Homebrew安装的是源文件包, 下载源文件、编译、安装，比如安装wget, gnupg, mutt等。
* homebrew-cask安装的是二进制软件包, 比如QQ，Chrome，evernote等。homebrew-cask安装软件时自动创建软连接到Application目录，这样在Launchpad中也能查看到安装的软件，方便启动软件。

### 安装homebrew-cask

    brew tap phinze/cask
    brew install brew-cask

### 常用命令

列出所有可以被安装的软件：

    brew cask search

查找所有和drop相关的应用:

    brew cask search drop

查看迅雷应用的信息:

    brew cask info thunder

卸载QQ:

    brew cask uninstall qq

查看已安装的软件

    brew cask list

更新Casks:

    brew update && brew upgrade brew-cask

关于软件更新，目前homebrew-cask并不提供命令直接更新已安装的软件，软件更新主要是通过软件自身的更新流程，不过也可以通过以下命令先删除软件，再重新安装。

    brew cask uninstall APP && brew cask install APP


### 一键装机？有了homebrew-cask就可以

    brew cask install alfred
    brew cask install qq
    brew cask install skype
    brew cask install thunder
    brew cask install mplayerx
    brew cask install evernote
    brew cask install skitch
    brew cask install dropbox
    brew cask install google-chrome
    brew cask install mou
    brew cask install iterm2
    brew cask install sublime-text

## zsh

喜欢强大的zsh，直接切换成zsh

    chsh -s /bin/zsh

## oh-my-zsh

## prezto（oh-my-zsh不要用？试试prezto）

https://github.com/sorin-ionescu/prezto

## tmux

## 浏览器

Google Chrome
firefox

## 编辑器

### Vim

https://github.com/perfectworks/vim

### Emacs
