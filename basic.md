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

使用过debian或者RedHat的操作系统的人，一定非常熟悉aptitude或yum包管理工具。在OS X平台下，同样有优秀的Homebrew软件包管理工具，而且这个工具是开源的，可以管理大量Apple没有提供，而你又经常会用到的软件包。

安装Homebrew:

    ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
    brew doctor

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

## homebrew-cask

通常 OS X下软件的安装是使用 App Store进行的，homebrew-cask是一个基于HomeBrew的软件安装程序，使用 homebrew-cask 可以在命令行下安装软件包， 相对 Mac App Store ，还有一些优势：

* 安装软件体验非常一致简洁优雅
* 对常用软件支持更全面，例如 MPlayerX 已经宣布不在更新 Mac App Store上 的版本
* 软件更新速度快，体验好。例如Alfred 2.0已经出了很久，但在 Mac App Store 上还是1.2版本，QQ也是这样的情况
* Mac App Store 生态圈远不完善，审核流程过长，限制太多，维护成本过高让很多应用开发者被迫离开。

安装homebrew-cask

    brew tap phinze/cask
    brew install brew-cask
    brew cask install google-chrome

常用命令

    brew cask search 列出所有可以被安装的软件
    brew cask search drop 查找所有和 drop 相关的应用
    brew cask info thunder 查看 迅雷 应用的信息，这货安装的可是最新版本的迅雷哦！
    brew cask uninstall qq 卸载 QQ

一键装机？有了homebrew-cask就可以

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


## tmux

## 浏览器

Google Chrome
firefox
