# 备份和恢复

第一次使用Mac OS X下的时光机器(Time Machine)，就被苹果如此完美贴心的备份恢复方案打动。数据无价，电脑里留下了岁月的痕迹和凝结了我们的心血，数据备份的重要性是怎么强调都不为过的。Time Machine是对这些数据最好的保护。只要你已经使用Time Machine备份过，设想一下：

* 当你的Mac丢失或者硬件损坏了以后，你只要从苹果商店新买一台Mac，然后从Time Machine备份中恢复。你会看到一个和之前一模一样的系统，包括数据、设置、状态。
* 当你给自己奖赏了一台新Mac时候，可以使用Time Machine将所有东西迁移过去。
* 当你误删除一个文档，几个月以后再想起来，可以从Time Machine恢复。
* 当你对一个文档做了多次修改，引入了一个错误，希望恢复某次正确的一个版本的时候，Time Machine可以帮助你。

如果你熟悉git，那Time Machine简直就是一个操作系统级别的版本控制！

当我安装好一个新的Mac OS X系统以后，第一件事情，就是设置Time Machine。

现在云存储已经普及，容量也足够大，但是Time Machine还是有不可替代的优势：

* 云存储没有版本历史，不能对之前的数据恢复。删除了就是删除了，也不能恢复之前某个时刻版本的数据资料。
* 云存储有隐私泄露的问题，爱德华·斯诺登给我们好好上了一课。
* 云存储不能解决恢复问题，仅仅只能做最基本的文件存储，不能在一台新的Mac上恢复所有数据和配置

简单地说，云存储就是一个简单的Windows操作系统级别的拷贝备份，和Time Machine细颗粒度，多版本，包括数据、配置、状态的完整备份恢复方案相比，弱爆了。

基于上述理由，郑重提醒，在设置Time Machine的exclude目录的时候，千万不要将云存储映射的目录排除在外。否则这些你认为已经被云存储保护过的资料，就不能享受Time Machine的保护，而这些资料往往是你最重要的资料。

## 准备工作

Time Machine可以使用下面一些方式进行，我还是选择简单、可靠、廉价的第一种方案：

* 本地外接移动硬盘

基于速度考虑，建议使用USB 3或者雷电高速接口，硬盘的大小可以选择1T或者2T，这个硬盘将伴随着你，保护你一生的数据资料。移动硬盘的分区方案，参见[安装]部分说明(https://github.com/pubyun/macdev/blob/master/install.md)

* 使用Time Capsule

无线方案，使用方便。缺点是Time Capsule发热量大，速度相对于有线方案也较慢。

* 如果你有一台Linux服务器，可以安装netatalk软件

看上去是一个理想的方案，但是设置好备份以后，不知道由于什么原因出现过几次备份无效，导致需要完全重新备份，后来丢弃了这个方案。


## Time Machine的设置

Time Machine这么强大的功能，设置其实很简单，苹果官方网站有详细的[指南](http://support.apple.com/kb/HT1427?viewlocale=zh_CN)，我在这里就不再重复。

需要注意的是，Mac OS X会在运行中产生一些临时数据或者中间数据，这些数据往往占用空间较大，而没有保存价值，可以设置成exclude，常见的有：

    /Library/Application Support/
    /Library/Caches/
    /private/var/log/
    /private/var/vm/
    /private/var/tmp/
    ~/Downloads/
    ~/Library/Caches
    ~/Library/Application Support/MobileSync/
    ~/.Trash/
    ~/Documents/Virtual\ Machines.localized/
    ~/Library/Parallels

备份完毕以后，移动硬盘需要在Finder下umount才能拔出，否则有可能数据丢失。

