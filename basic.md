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

## Xcode Command Line Tools

Xcode是Apple的一个开发工具和库集合，Xcode Command Line Tools是Xcode的一部分。安装很多Unix软件都需要使用GCC编译器等开发工具，Xcode Command Line Tools就包含这些工具。

检查Xcode Command Line Tools是否已经安装：

    $ xcode-select -p
    /Library/Developer/CommandLineTools

打开一个终端窗口(Terminal)，运行命令：

    xcode-select --install

然后点击"Install"按钮，安装Xcode的命令行工具

## 软件包管理工具

使用过Debian或者RedHat的操作系统的人，一定非常熟悉aptitude或yum包管理工具。在OS X平台下，同样有优秀的软件包管理工具，可以管理大量Apple没有提供，而你又经常会用到的开源软件包。我们有两种选择——MacPorts和Homebrew。

用过FreeBSD的人应该不会对它的包管理系统port感到陌生，而MacPorts正是由FreeBSD的port移植而来的。Homebrew则是一个全新的包管理系统，用Ruby进行开发。这两种包管理系统的工作方式都是下载source code然后在本地编译。但是这两种包管理系统还是存在很大差异的，主要差异有以下三点：

* MacPorts的理念是尽量减少对系统现有库的依赖，而Homebrew则是尽量依赖系统现有库。
* MacPorts的Package都是安装到/opt/local，而Homebrew的Package都是安装到/usr/local。
* Macports使用rsync进行同步（现在也可以使用svn，详情点击[这里](https://trac.macports.org/wiki/howto/SyncingWithSVN)），而Homebrew使用git进行同步。

MacPorts会自己重新编译系统现有库，编译时间较长，好处是不怎么依赖系统。同时Package都被安装到了/opt/local中，不会与系统现有的软件发生冲突。而Homebrew则正好相反，Homebrew会尽量使用系统现有库，所以编译时间会显著减少，坏处是与系统紧密依赖。同时Package都被安装到了/usr/local，有可能与系统自带的软件发生冲突。

总体来说，Homebrew使用简单，编译时间短，比较适合新手使用。MacPorts编译时间长，命令还要带上sudo，易用性上没有Homebrew好，但是比较干净，适合有洁癖的人使用（比如说我(^_-)）。

还有最后一个问题，如果你使用了proxy或者firewall，MacPorts默认的rsync有可能会失效，请切换至svn方式进行同步。

### MacPorts

以下内容可能会随时间的推移而发生变化，请到[官方网站](https://www.macports.org/)查看最新文档（ RTFM ！！）

* 安装MacPorts:

1.安装Xcode和Xcode Command Line Tools

2.在终端中同意Xcode许可
    
    sudo xcodebuild －license

3.到[这里](https://www.macports.org/install.php)选择与你系统版本相符的pkg包，下载并安装

* 常用命令

寻求帮助:
    
    port help
这个命令可以指定动作，如:
    
    port help selfupdate

同步 ports tree:
    
    sudo port selfupdate
这个命令也会同时检测是否有新版本的MacPorts。

安装软件:
    
    sudo port install gcc

列出所有可用包:
    
    port list
当没有指定包名称时，会列出所有可用包，当指定了包名称时，会列出该包的所有可用版本。

查看已安装软件包:
    
    port installed

查看可升级软件包:
    
    port outdated

升级所有软件:
    
    sudo port upgrade outdated

搜索某个软件:
    
    port search gcc

查看软件包信息:
    
    port info gcc

清除垃圾:
    
    sudo port clean --all gcc
你也可以清除指定文件，详情自行port help clean。

卸载软件:
    
    sudo port uninstall gcc

移除已升级的软件包不活跃的版本:
    
    sudo port unistall inactive

列出软件包的依赖关系:
    
    port deps gcc

* 高级使用技巧（Port Variants）:

Port Variants为我们提供了一种自定义编译选项的方法（和Gentoo中的USE标签类似）。

获取可用的选项:
    
    port variants gcc

调用variants进行编译:
    
    sudo port －v install fetchmail ＋ssl

### Homebrew

Homebrew为Mac OS X提供了非常方便的软件安装方式，解决了包的依赖问题，不再需要烦人的sudo，一键式编译，无参数困扰。

由于Homebrew的安装方式可能变化，请到[官方网站](http://brew.sh)查看最新的方法和文档。

安装Homebrew:

    ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    brew doctor

更新formula和Homebrew:

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

### homebrew-cask

通常OS X下二进制软件是通过App Store安装的，homebrew-cask是一个基于HomeBrew的软件安装程序，使用homebrew-cask可以在命令行下安装软件包，相对Mac App Store，还有一些优势：

* 安装软件体验一致、简洁、优雅、快速
* 对常用软件支持更全面，例如MPlayerX已经宣布不在更新Mac App Store上的版本
* 软件更新速度快。例如Alfred 2.0已经出了很久，但在Mac App Store上还是1.2版本，QQ也是这样的情况
* Mac App Store生态圈远不完善，审核流程过长，限制太多，维护成本过高让很多应用开发者被迫离开。

homebrew-cask和Homebrew的区别：

* Homebrew安装的是源文件包, 下载源文件、编译、安装，比如安装wget, gnupg, mutt等。
* homebrew-cask安装的是二进制软件包, 比如QQ，Chrome，evernote等。homebrew-cask安装软件时自动创建软连接到Application目录，这样在Launchpad中也能查看到安装的软件，方便启动软件。

#### 安装homebrew-cask

    brew install caskroom/cask/brew-cask

#### 常用命令

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


#### 一键装机？有了homebrew-cask就可以

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

## iTerm2

Mac是一个具有精致图形界面的Unix平台，作为开发人员，经常会使用到终端(Terminal)或者称作控制台(Console)。系统自带的Terminal程序已经做得不错了，但是iTerm2的功能依然要更强大一些。

具体的安装和使用方法可以参见[官方网站](http://www.iterm2.com/)和搜索相关资料。

## Go2Shell

Go2Shell可以方便地实现在Finder当前目录中打开一个终端，如果你经常需要在Finder和终端下切换工作，那么Go2Shell是你的必备工具。

安装完毕之后进入Applications文件夹中按住command键拖动Go2Shell图标到Finder工具栏上，以后点击可开启终端到当前路径。

Go2Shell可以配合Iterm2使用，设置方式是在Termial執行下述命令

    open -a go2shell --args config

跳出Go2Shell Setup，选iTerm2

## zsh

喜欢强大的zsh，直接切换成zsh

    chsh -s /bin/zsh

## oh-my-zsh

## prezto（oh-my-zsh不要用？试试prezto）

https://github.com/sorin-ionescu/prezto

## tmux

## 浏览器

### Google Chrome

内置Intel HD 4000/HD 5000/Iris系列显卡的机器，比如2012 Mac Air, 2013 Mac pro 13等，在OS X操作系统上运行Chrome，会频繁发生操作系统死机的情况。这个问题在[2012.6.28就被Google确认](http://gizmodo.com/5922235/we-were-right-google-confirms-chrome-is-to-blame-for-crashing-macbooks)，是OS X内核的一个Bug，直到现在一直没有修正。

临时的解决办法是，关闭Chrome的硬件加速, 在Chrome的设置里，选择"Show advanced settings"，然后关闭选项"Use hardware acceleration when available"。

### Safari

### Firefox

## 编辑器

### Vim

https://github.com/perfectworks/vim

### Emacs
