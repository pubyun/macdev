# 系统的安装

## 安装之前

重装之前，使用时光机器（Time Machine），将所有硬盘资料备份到移动硬盘上。这个也可以方便地作为系统快照，恢复之前某个时刻的机器的状态。

覆盖安装和全新安装（即抹盘安装），默认是覆盖安装。 你可以在安装界面使用磁盘工具将系统盘抹掉，这样安装以后就是一个完全干净的系统，但是你的数据和程序也将完全清除。你也可以选择覆盖安装，安装之前无需将系统盘抹掉，这样不会丢失程序和数据，但是可能引起冲突、不一致等问题。

安装时，请将语言选为English，不要使用中文界面。碰到问题的时候，使用英文关键词，在互联网查找、搜索，可以比中文关键字获得更加准确和丰富的信息。

## 网络安装还是本地安装

Mac OS X支持网络安装，直接使用command+R，就可以进入恢复模式，然后从互联网下载操作系统进行安装，整个过程自动、方便。安装的时候，注意只能使用wifi网络，并且仅支持WPA/WPA2加密方式，不支持WEP加密方式。

到目前为止，苹果在中国大陆使用CDN加速了App Store的软件下载，但是安装操作系统任然需要从境外服务器下载。Mavericks（10.9）安装镜像有5.3G的大小，即使你的网速有100Mbps或者更高，你也经常会发现网络安装的过程是一个痛苦的体验，往往看着安装进度条蜗牛一般前进，提示还有上百小时才能下载完毕。

建议预先下载安装镜像，制作安装盘，进行本地安装。这样时间进度可控，出现问题的风险小。以后进行重新安装和恢复的时候，再也不用重新从网络长时间等待下载。

## DNS服务器的选择

由于苹果的软件完全采用网络分发，下载服务器全球分步，选用不通的DNS会很大程度上影响软件的下载速度。推荐的一些DNS有：

114.114.114.114 南京信风
8.8.8.8         Google
199.91.73.222   V2EX

## 制作安装盘

### 分区

准备一个U盘或移动硬盘（大于等于6G），建议使用USB 3或者雷电高速接口。最好使用移动硬盘作为介质，速度比U盘快，同时可以将移动硬盘作为时光机器和恢复安装工具。

首先在磁盘工具内的"Options"里，选择 GUID，否则无法启动，然后在"Partision Layout"将移动硬盘分成三个分区：

* 分区名字Mavericks，大小8G，格式是Mac OS Extended (Journaled)

本地磁盘安装介质的制作，方便以后安装系统。

* 分区名字recovery，大小2G，格式是Mac OS Extended (Journaled)

恢复助手，用于对系统进行恢复。

* 分区名字data，剩余的磁盘空间，格式是Mac OS Extended (Journaled)

数据备份和时光机器的介质。

### 制作安装盘

* 从Mac App Store下载安装程序，或从百度网盘下载10.9.1的安装程序：

    http://pan.baidu.com/s/1ntM6qud

* 如果你是从百度网盘下载的安装程序

下载完成之后双击挂载

在命令行输入下面的命令，制作安装盘:

    sudo /Volumes/Установка\ OS X\ Mavericks/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/Mavericks --applicationpath /Volumes/Установка\ OS X\ Mavericks/Install\ OS\ X\ Mavericks.app --nointeraction

* 如果你从Mac App Store下载下来的软件

在命令行输入下面的命令，制作安装盘:

    sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/Mavericks --applicationpath /Applications/Install\ OS\ X\ Mavericks.app --nointeraction

* 安装盘制作完毕后，重启并按Option键，选择安装盘安装。 安装或者恢复之前，一般使用时光机器进行备份，然后用磁盘工具删掉之前的机器磁盘上的内容。

### 制作恢复盘

苹果提供 OS X Recovery Disk Assistant 工具，这个工具将在本地磁盘制作一个恢复分区。下载地址：

    http://support.apple.com/kb/dl1433


